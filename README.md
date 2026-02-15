# TDMS to Excel Converter (LabVIEW)

This LabVIEW project automates the process of **reading data from TDMS files** and exporting selected columns into Excel, based on configurable settings in an `.ini` file.

---

## Features

- **TDMS Data Reading**: Automatically loads and parses **all `.tdms` files in the selected folder**.  
- **Configurable Columns**: Reads a `.ini` configuration file specifying which columns to extract according to a pattern.  
- **Flexible Parsing**: Supports extracting a specific number of characters from file names.  
- **Batch Processing**: Automatically processes **all TDMS files in a folder**, one by one.  
- **Customizable via INI File**: Easily modify which columns to extract, patterns to match, and parsing rules without changing the LabVIEW VI.

---

## How It Works

1. **Configuration**  
   - The `.ini` file defines:
     - Root directory
     - Which columns to extract based on a naming **pattern**
     - How many characters to parse from TDMS file names
2. **TDMS Parsing**  
   - The LabVIEW VI reads **all TDMS files in the selected folder**.  
   - Filters columns according to the `.ini` settings.  
   - Parses relevant portions of file names as defined in the configuration.  
3. **Excel Export**  
   - Selected columns are written into an Excel workbook.  
4. **Batch Processing**  
   - All TDMS files in the folder are processed automatically, maintaining consistent formatting.  
---


## Usage

1. **Prepare your data**  
   - Place all `.tdms` files you want to process in a single folder.  
   - Ensure the `.ini` configuration file is in the same directory (or provide its path in the VI).  

2. **Open the LabVIEW VI**  
   - Launch LabVIEW and open the TDMS-to-Excel VI.  

3. **Select the folder**  
   - Choose the folder containing the `.tdms` files.  

4. **Run the VI**  
   - The VI will automatically:
     - Read **all TDMS files** in the selected folder.  
     - Extract columns based on the `.ini` configuration.  
     - Parse file names according to the specified rules.  
     - Export the extracted data to an Excel workbook.  

5. **Review the output**  
   - Open the generated Excel file(s) and verify that all required columns and data were correctly exported.  

---

RootPath = ""

SavePath = ""


[Parameters]

Param1  = "TS033.TV018."

#Param1 = "xxxxxxxxxxxx"

[FilenameParser]
ProductBegin = 52
ProductLength = 3
TBBegin = 13
TBLength = 8
StatusBegin = 0
StatusLength = 0

[LitraParser]
LitraInfoBegin = 45
LitraInfoLength = 8
LeakageBegin = 50
LeakageLength = 7
