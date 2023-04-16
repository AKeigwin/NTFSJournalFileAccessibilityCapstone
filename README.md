# Amy Keigwin's Capstone Project for Champlain College
Digital Forensics Major | May 2023

## NTFS Journal File Accessibility

### Requirements

  * Elastic Stack 8.x
  * FTK Imager or other acquisition software
  * UsnJrnl2CSV
  * Excel or other CSV editor

### Initial Setup

1. Use acquisition software to acquire $J data stream
  * root\$Extend\$UsnJrnl\$J
2. Use UsnJrnl2CSV to convert $J file to CSV
  1. Select `log2timeline`
  2. Use `|` separator
  3. Select $J file using `Browse $UsnJrnl` button
  4. Select `Start Parsing` button
3. Use CSV editor to convert deliminated text to columns and save file
4. Import CSV file to Elastic Stack
  * Machine Learning > Data Visualizer
  * _Note: Elastic Stack only processes CSV files 100MB or less. The workaround is to create multiple CSV files and merge the indices_
5. Change index on dashboards
  * _Note: you may need to edit the visualizations to change the indexes_
6. Use dashboards to search CSV data!
  
### To Use
1. Download `export.ndjson`
2. Import dashboards to Elastic Stack
  1. POST <kibana host>:<port>/api/kibana/dashboards/import
  2. POST <kibana host>:<port>/s/<space-id>/api/kibana/dashboards/import

OR 

  1. Go to Stack Management > Saved Objects
  2. Click the Import button
  3. Select the NDJSON file
