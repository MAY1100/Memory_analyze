# Forensic Analysis Automation Script

## Project Overview
This Bash script automates forensic analysis using various tools such as **Volatility, Binwalk, Bulk Extractor, and Foremost**. It extracts data from memory dumps, executable files, and disk images, performing various forensic investigations. The script is designed to run on **Kali Linux**.

## Features
- **Automated Installation**: Installs required forensic tools if missing.
- **Memory Analysis**: Uses **Volatility** to analyze memory dumps.
- **Data Carving**: Extracts data from files using **Binwalk, Bulk Extractor, and Foremost**.
- **String Extraction**: Identifies human-readable strings in **.exe** files for keyword-based analysis.
- **Result Compilation**: Summarizes findings and compresses them into a ZIP file.
- **Automated Report Generation**: Logs forensic analysis results.
- **File and Directory Management**: Organizes extracted data into appropriate directories.

## Prerequisites
Before running the script, ensure the following:
- You are using **Kali Linux**.
- You have **root privileges**.
- Required forensic tools are installed (**Binwalk, Bulk Extractor, Foremost, and Volatility**).

## Installation
Clone this repository and navigate into the directory:
```bash
 git clone https://github.com/yourusername/forensic-analysis-script.git
 cd forensic-analysis-script
```

## Usage
1. Grant execute permissions to the script:
```bash
chmod +x forensic_script.sh
```
2. Run the script as **root**:
```bash
sudo ./forensic_script.sh
```
3. Enter the **full path** of the file to analyze when prompted.

## Script Workflow
1. Checks for **root access**.
2. Prompts the user for a file to analyze.
3. Installs required forensic tools (if missing).
4. Runs **data carving** using **Binwalk, Bulk Extractor, and Foremost**.
5. Extracts **human-readable strings** from **.exe** files.
6. Runs **Volatility** for **memory analysis**.
7. Generates a **report** and **compresses** the results into a ZIP file.

## Output Files
The script stores forensic results in the following directories:
- **forensic_case/** → Main working directory
- **forensic_case/binwalk/** → Extracted data from Binwalk
- **forensic_case/bulk_extractor/** → Extracted data from Bulk Extractor
- **forensic_case/foremost/** → Extracted data from Foremost
- **forensic_case/volatility/** → Memory analysis results from Volatility
- **forensic_case/strings/** → Extracted strings from .exe files
- **forensic_case/results_report.txt** → Final forensic analysis report
- **forensic_case/forensic_YYYY-MM-DD_HH-MM-SS.zip** → Compressed results archive

## Example Output
```
You are root.. continuing..
Please enter a full path to the file you would like to investigate:
/path/to/memory_dump.raw
Creating a directory for the case...
Installing relevant forensic tools...
[ + ] All required apps installed [ + ]
Extracting data with binwalk...
Extracting data with bulk_extractor...
Extracting data with foremost...
PCAP file found at: /home/kali/Desktop/forensic_case/bulk_extractor
Extracting human-readable strings from .exe files...
Checking if Volatility is installed...
[ + ] Volatility is installed. Starting analysis...
Getting processes list from memory...
Getting network connections...
Making an attempt to extract registry information...
The memory information saved in: /forensic_case/volatility
All results saved in: forensic_case/results_report.txt
Results successfully compressed into: forensic_case/forensic_YYYY-MM-DD_HH-MM-SS.zip
```

## Credits
- Created by **May**
- Lecturer: **Erel**
- Class Code: **S5**
- Unit: **TMagen773632**

## License
This project is licensed under the MIT License. See the `LICENSE` file for details.

