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
