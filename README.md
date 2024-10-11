#!/bin/bash

# Function to extract the first word inside angle brackets in each sentence
extract_bracket_values() {
  local csv_file=$1
  local column_index=$2  # Assuming the F column is 6th, so the index is 6
  declare -A counts

  # Read the CSV file line by line
  while IFS=',' read -r -a line; do
    # Extract the content of the F column (adjust column index if necessary)
    sentences=${line[$((column_index - 1))]}

    # Process each sentence in the cell (assuming sentences are split by newlines or semicolons)
    echo "$sentences" | while IFS= read -r sentence; do
      # Check if there are angle brackets in the sentence
      if [[ "$sentence" =~ "<" && "$sentence" =~ ">" ]]; then
        # Extract the first value inside the angle brackets <>
        value=$(echo "$sentence" | grep -oP '<\K[^>]+')

        if [ ! -z "$value" ]; then
          # Increment the count for the extracted value
          counts["$value"]=$((counts["$value"] + 1))
        fi
      fi
    done
  done < "$csv_file"

  # Output the count of each unique value found
  for value in "${!counts[@]}"; do
    echo "$value = ${counts[$value]}"
  done
}

# Main script logic
if [ $# -ne 1 ]; then
  echo "Usage: $0 <csv_file>"
  exit 1
fi

csv_file=$1

# Assuming the F column is the 6th column in the CSV (adjust this if needed)
column_index=6

# Run the bracket value extraction function
extract_bracket_values "$csv_file" "$column_index"


code for first 10 lines
#!/bin/bash

# Function to extract the first word inside angle brackets in each sentence
extract_bracket_values() {
  local csv_file=$1
  local column_index=$2  # Assuming the F column is 6th, so the index is 6
  local max_rows=10      # Limit the number of rows to process
  local current_row=0    # Initialize row counter
  declare -A counts

  # Read the CSV file line by line
  while IFS=',' read -r -a line; do
    # Increment the row counter
    ((current_row++))

    # Stop processing after 10 rows
    if [ $current_row -gt $max_rows ]; then
      break
    fi

    # Extract the content of the F column (adjust column index if necessary)
    sentences=${line[$((column_index - 1))]}

    # Process each sentence in the cell (assuming sentences are split by newlines or semicolons)
    echo "$sentences" | while IFS= read -r sentence; do
      # Check if there are angle brackets in the sentence
      if [[ "$sentence" =~ "<" && "$sentence" =~ ">" ]]; then
        # Extract the first value inside the angle brackets <>
        value=$(echo "$sentence" | grep -oP '<\K[^>]+')

        if [ ! -z "$value" ]; then
          # Increment the count for the extracted value
          counts["$value"]=$((counts["$value"] + 1))
        fi
      fi
    done
  done < "$csv_file"

  # Output the count of each unique value found
  for value in "${!counts[@]}"; do
    echo "$value = ${counts[$value]}"
  done
}

# Main script logic
if [ $# -ne 1 ]; then
  echo "Usage: $0 <csv_file>"
  exit 1
fi

csv_file=$1

# Assuming the F column is the 6th column in the CSV (adjust this if needed)
column_index=6

# Run the bracket value extraction function
extract_bracket_values "$csv_file" "$column_index"



code with progress 

#!/bin/bash

# Function to extract the first word inside angle brackets in each sentence
extract_bracket_values() {
  local csv_file=$1
  local column_index=$2  # Assuming the F column is 6th, so the index is 6
  local max_rows=10      # Limit the number of rows to process
  local current_row=0    # Initialize row counter
  declare -A counts

  # Read the CSV file line by line
  while IFS=',' read -r -a line; do
    # Increment the row counter
    ((current_row++))

    # Stop processing after 10 rows
    if [ $current_row -gt $max_rows ]; then
      break
    fi

    # Extract the content of the F column (adjust column index if necessary)
    sentences=${line[$((column_index - 1))]}

    # Process each sentence in the cell (assuming sentences are split by newlines or semicolons)
    echo "$sentences" | while IFS= read -r sentence; do
      # Print the current sentence being processed
      echo "Processing row $current_row: $sentence"

      # Check if there are angle brackets in the sentence
      if [[ "$sentence" =~ "<" && "$sentence" =~ ">" ]]; then
        # Extract the first value inside the angle brackets <>
        value=$(echo "$sentence" | grep -oP '<\K[^>]+')

        if [ ! -z "$value" ]; then
          # Increment the count for the extracted value
          counts["$value"]=$((counts["$value"] + 1))
        fi
      fi
    done

    # Print progress
    echo "Completed processing row $current_row"
  done < "$csv_file"

  # Output the count of each unique value found
  echo "Final counts of values:"
  for value in "${!counts[@]}"; do
    echo "$value = ${counts[$value]}"
  done
}

# Main script logic
if [ $# -ne 1 ]; then
  echo "Usage: $0 <csv_file>"
  exit 1
fi

csv_file=$1

# Assuming the F column is the 6th column in the CSV (adjust this if needed)
column_index=6

# Run the bracket value extraction function
extract_bracket_values "$csv_file" "$column_index"


java code 

import org.apache.poi.ss.usermodel.*;
import org.apache.poi.xssf.usermodel.XSSFWorkbook;

import java.io.File;
import java.io.FileInputStream;
import java.io.IOException;
import java.util.HashMap;
import java.util.Map;

public class ExcelBracketCounter {

    public static void main(String[] args) {
        // Change this to the path of your .xlsx file
        String filePath = "path/to/your/file.xlsx";

        // Create a map to store the counts of values
        Map<String, Integer> countMap = new HashMap<>();

        // Read the Excel file
        try (FileInputStream fis = new FileInputStream(new File(filePath));
             Workbook workbook = new XSSFWorkbook(fis)) {

            Sheet sheet = workbook.getSheetAt(0); // Assuming data is in the first sheet
            int rowCount = sheet.getPhysicalNumberOfRows();

            for (int i = 0; i < rowCount; i++) {
                Row row = sheet.getRow(i);
                if (row != null) {
                    // Get the cell value (assuming only one column)
                    Cell cell = row.getCell(0);
                    if (cell != null) {
                        String sentences = cell.getStringCellValue();
                        String[] individualSentences = sentences.split("\\n"); // Split sentences by new line

                        for (String sentence : individualSentences) {
                            // Print the current sentence being processed
                            System.out.println("Processing row " + (i + 1) + ": " + sentence);

                            // Check for angle brackets and extract the first value
                            if (sentence.contains("<")) {
                                int startIndex = sentence.indexOf('<') + 1;
                                int endIndex = sentence.indexOf('>', startIndex);
                                if (endIndex > startIndex) {
                                    String value = sentence.substring(startIndex, endIndex);
                                    
                                    // Increment the count for this value
                                    countMap.put(value, countMap.getOrDefault(value, 0) + 1);
                                }
                            }
                        }
                    }
                }
                // Print progress
                System.out.println("Completed processing row " + (i + 1));
            }

            // Output the counts
            System.out.println("Final counts of values:");
            for (Map.Entry<String, Integer> entry : countMap.entrySet()) {
                System.out.println(entry.getKey() + " = " + entry.getValue());
            }
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}


dependencies to add 

<dependencies>
    <dependency>
        <groupId>org.apache.poi</groupId>
        <artifactId>poi-ooxml</artifactId>
        <version>5.2.3</version> <!-- Check for the latest version -->
    </dependency>
    <dependency>
        <groupId>org.apache.poi</groupId>
        <artifactId>poi</artifactId>
        <version>5.2.3</version>
    </dependency>
    <dependency>
        <groupId>org.apache.xmlbeans</groupId>
        <artifactId>xmlbeans</artifactId>
        <version>5.0.2</version>
    </dependency>
</dependencies>
