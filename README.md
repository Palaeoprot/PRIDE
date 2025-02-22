# PRIDE Data Downloader using Google Spreadsheets

## Overview
This script automates the download of proteomics data from PRIDE using lists stored in Google Spreadsheets. It extracts file metadata and downloads specified file types using `pridepy`. The Google Sheets API is used to manage download lists, and the script is designed to run in Google Colab with automatic file categorization and smart handling of different file types.

## Features
- Automatic categorization of files (RAW/PEAK/RESULT/FASTA/OTHER)
- Interactive file type selection with progress tracking
- Smart handling of large text files (configurable size limits)
- Category-based directory organization
- Multiple download protocols with automatic retry
- Comprehensive logging and error handling

## Requirements
Ensure you have the following dependencies installed:
* Python 3.x
* `pridepy`
* `pandas`
* `google-api-python-client`
* `tqdm`
* `json`

## Installation
Install the required dependencies using:

```bash
pip install --upgrade pridepy pandas google-api-python-client tqdm
```

## Usage
1. Open the Colab notebook version linked in this repository
2. Configure the script parameters (e.g., spreadsheet ID, sheet name, file types)
3. Run the script in Google Colab
4. Follow the interactive prompts to select and download file types

## Configuration
Key parameters in the script:
* `spreadsheet_id`: The ID of the Google Spreadsheet containing project information
* `sheet_name`: The sheet from which data is extracted
* `repository`: The repository (default: `PRIDE`)
* `file_types`: Comma-separated file extensions to download (e.g., `mgf, fasta, txt, raw`)
* `protocol`: The download protocol (`aspera`, `ftp`, or `globus`)
* `folder_name`: The destination folder for downloaded files
* `download_large_text_files`: Boolean to control downloading of text files > 1MB
* `shared_drive_base_dir_str`: Base directory path in Google Drive

## File Organization
Files are automatically organized into categories:
```
shared_drive_base_dir/
└── folder_name/
    └── PRIDE_ID/
        ├── RAW/
        │   └── raw_files...
        ├── PEAK/
        │   └── peak_files...
        ├── RESULT/
        │   └── result_files...
        ├── FASTA/
        │   └── fasta_files...
        └── OTHER/
            └── documentation_files...
```

## Error Handling
The script includes comprehensive error handling for:
- Google Sheets API errors
- File download failures with protocol fallback
- JSON parsing errors
- Directory creation issues
- Size limit violations
- Invalid file type selections

## Contributing
Contributions are welcome! Please feel free to submit a Pull Request.

## License
This script is provided under an open-source license. Modify as needed for your research purposes.
