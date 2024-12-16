import org.apache.poi.ss.usermodel.*;
import org.apache.poi.xssf.usermodel.XSSFWorkbook;
import java.io.*;
import java.util.HashMap;

public class ExcelComparator {

    public static void main(String[] args) throws Exception {
        String primaryExcelPath = "path_to_first_excel.xlsx";
        String secondaryExcelPath = "path_to_second_excel.xlsx";
        String outputExcelPath = "path_to_output_excel.xlsx";
        
        HashMap<String, String> primaryData = readExcelData(primaryExcelPath);
        HashMap<String, String> secondaryData = readExcelData(secondaryExcelPath);
        
        Workbook workbook = new XSSFWorkbook();
        Sheet outputSheet = workbook.createSheet("Comparison");
        createHeaderRow(outputSheet);
        
        int rowNum = 1;
        for (String vendorName : primaryData.keySet()) {
            Row row = outputSheet.createRow(rowNum++);
            Cell vendorCell = row.createCell(0);
            vendorCell.setCellValue(vendorName);
            
            Cell vendorId1Cell = row.createCell(1);
            vendorId1Cell.setCellValue(primaryData.get(vendorName));
            
            String secondaryVendorId = secondaryData.get(vendorName);
            Cell vendorId2Cell = row.createCell(2);
            vendorId2Cell.setCellValue(secondaryVendorId != null ? secondaryVendorId : "Not Found");
            
            Cell comparisonCell = row.createCell(3);
            if (secondaryVendorId == null) {
                comparisonCell.setCellValue("Not Present");
            } else if (primaryData.get(vendorName).equals(secondaryVendorId)) {
                comparisonCell.setCellValue("Matching");
            } else {
                comparisonCell.setCellValue("Different");
            }
        }
        
        try (FileOutputStream outputStream = new FileOutputStream(outputExcelPath)) {
            workbook.write(outputStream);
        }
        workbook.close();
        
        System.out.println("Comparison file generated: " + outputExcelPath);
    }
    
    private static HashMap<String, String> readExcelData(String filePath) throws Exception {
        HashMap<String, String> dataMap = new HashMap<>();
        FileInputStream fis = new FileInputStream(filePath);
        Workbook workbook = new XSSFWorkbook(fis);
        Sheet sheet = workbook.getSheetAt(0);
        for (Row row : sheet) {
            String vendorName = row.getCell(0).getStringCellValue();
            String vendorId = row.getCell(1).getStringCellValue();
            dataMap.put(vendorName, vendorId);
        }
        workbook.close();
        fis.close();
        return dataMap;
    }
    
    private static void createHeaderRow(Sheet sheet) {
        Row headerRow = sheet.createRow(0);
        headerRow.createCell(0).setCellValue("Vendor Name");
        headerRow.createCell(1).setCellValue("VendorId (First Excel)");
        headerRow.createCell(2).setCellValue("VendorId (Second Excel)");
        headerRow.createCell(3).setCellValue("Comparison");
    }
}

<dependency>
    <groupId>org.apache.poi</groupId>
    <artifactId>poi-ooxml</artifactId>
    <version>5.2.2</version>
</dependency>

{
  "query": "DO $$ DECLARE v_return_code INTEGER; v_return_msg VARCHAR; BEGIN CALL VBUILD.PROC_NNI_BACKLOG_RPT(1, 101, 201, '2024-01-01', '2024-01-31', 'Texas', 'Houston', v_return_code, v_return_msg); RAISE NOTICE 'Return Code: %, Return Msg: %', v_return_code, v_return_msg; END $$;"
}


SELECT DISTINCT
    (SELECT last_name || COALESCE(',' || first_name, '') 
     FROM nni_employee 
     WHERE employee_id = h.level4_id) AS execDirector,

    (SELECT last_name || COALESCE(',' || first_name, '') 
     FROM nni_employee 
     WHERE employee_id = h.level5_id) AS director,

    (SELECT last_name || COALESCE(',' || first_name, '') 
     FROM nni_employee 
     WHERE employee_id = h.level6_id) AS nimgr,

    (SELECT ins.last_name || COALESCE(',' || ins.first_name, '') 
     FROM nni_employee ins 
     WHERE ins.employee_id = nctr.nni_instal_supv) AS instalSupv,

    (SELECT ts.last_name || COALESCE(',' || ts.first_name, '') 
     FROM nni_employee ts 
     WHERE ts.employee_id = nctr.nni_test_supv) AS testSupv,

    (SELECT lt.last_name || COALESCE(',' || lt.first_name, '') 
     FROM nni_employee lt 
     WHERE lt.employee_id = nctr.nni_lead_tech) AS leadTechnician,

    COALESCE(e.emp_last_name, '') || COALESCE(', ' || e.emp_first_name, '') AS fieldEngr,
    nctl.state AS state,
    nctl.city AS city,
    rs.status AS jobType,
    nct.ccr_id AS corNum,
    nct.teo_num AS teoNum,
    nctn.job_summary AS jobSummary,
    nct.project_id AS projectId,
    nctl.company AS company,
    nctl.plant AS plant,
    nctl.sub_plant AS subPlant,
    nct.clli_code AS clliCode,

    vbuild.fun_metrics_status(nct.teo_num) AS metricStatus,

    -- Milestone Date Queries
    (SELECT est_milestone_date 
     FROM nni_teo_milestone_dates rlconst1 
     WHERE rlconst1.milestone_abbr = 'RLCONS' 
       AND rlconst1.teo_num = nct.teo_num 
     FETCH FIRST 1 ROW ONLY) AS originalReleaseConstDate,

    (SELECT act_milestone_date 
     FROM nni_teo_milestone_dates rlconst2 
     WHERE rlconst2.milestone_abbr = 'RLCONS' 
       AND rlconst2.teo_num = nct.teo_num 
     FETCH FIRST 1 ROW ONLY) AS actualReleaseConstDate,

    -- STRING_AGG replacement for LISTAGG
    (SELECT STRING_AGG(associated_job_type, ';') 
     FROM nni_associated_job_details 
     WHERE teo_num = nct.teo_num) AS highProfileType,

    nct.fttc_flag AS fttcJobFlag

FROM nni_ccp_teo nct

INNER JOIN vbuild.ref_status rs 
    ON CAST(rs.status_id AS VARCHAR(20)) = nct.project_type 
    AND rs.entity = 'NNI Group'

INNER JOIN teo_barcoding b 
    ON nct.teo_num = b.teo_num 
    AND b.barcode_required_ind = 'YES'

LEFT JOIN nni_teo_milestone_dates eqpRdy 
    ON nct.teo_num = eqpRdy.teo_num 
    AND eqpRdy.milestone_abbr = 'EQPRDY'

LEFT JOIN nni_teo_milestone_dates excepcom 
    ON nct.teo_num = excepcom.teo_num 
    AND excepcom.milestone_abbr = 'EXCEPCOM'

LEFT JOIN vbuild.nni_cor_teo_routing nctr 
    ON nctr.teo_num = nct.teo_num

LEFT JOIN vbuild.nni_reports_to_hierarchy h 
    ON h.nni_emp_id = nctr.nni_instal_supv

LEFT JOIN nni_employee e 
    ON e.employee_id = nct.field_engr

LEFT JOIN vbuild.nni_ccp_teo_location nctl 
    ON nctl.nni_ccp_location_id = nct.nni_ccp_location_id

LEFT JOIN vbuild.nni_ccp_teo_notes nctn 
    ON nct.nni_ccp_teo_id = nctn.nni_ccp_teo_id

WHERE 1=1
  AND ((eqpRdy.est_milestone_date BETWEEN '2023-12-08' AND '2024-12-13' 
        AND eqpRdy.act_milestone_date IS NULL) 
       OR (eqpRdy.act_milestone_date IS NOT NULL 
           AND excepcom.est_milestone_date BETWEEN '2023-12-08' AND '2024-12-13' 
           AND excepcom.act_milestone_date IS NULL))
ORDER BY 1, 2, 3, 4, 5;
