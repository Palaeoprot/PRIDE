# PRIDE Data Downloader using Google Spreadsheets

## Overview
This script automates the download of data from PRIDE using lists stored in Google Spreadsheets. It extracts file metadata and downloads specified file types using `pridepy`. The Google Sheets API is used to manage download lists. The script is designed to run in Google Colab, and a Colab version is posted to GitHub.

## Requirements
Ensure you have the following dependencies installed:
- Python 3.x
- `pridepy`
- `pandas`
- `google-api-python-client`
- `tqdm`
- `json`

## Installation
Install the required dependencies using:
```bash
pip install --upgrade pridepy pandas google-api-python-client tqdm
```

## Usage
1. Open the Colab notebook version linked in the GitHub repository.
2. Configure the script parameters (e.g., spreadsheet ID, sheet name, file types).
3. Run the script in Google Colab.
4. The script will fetch project metadata from PRIDE and download the specified files.

## Configuration
Key parameters in the script:
- `spreadsheet_id`: The ID of the Google Spreadsheet containing project information.
- `sheet_name`: The sheet from which data is extracted.
- `repository`: The repository (default: `PRIDE`).
- `file_types`: Comma-separated file extensions to download (e.g., `mgf, fasta, txt, raw`).
- `protocol`: The download protocol (`aspera`, `ftp`, or `globus`).
- `folder_name`: The destination folder for downloaded files.

## License
This script is provided under an open-source license. Modify as needed for your research purposes.


