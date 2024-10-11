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
