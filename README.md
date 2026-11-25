# LogLens

LogLens is a command-line Python script that counts the records in a CSV log file by log level.

Note: This documentation is for computing students and new technical interns who are comfortable with CSV files and using a terminal, but have not used LogLens before.


## About LogLens

LogLens reads a CSV log file and prints how many records match a log level, or the total number of records. It runs locally and does not modify, upload, or store your data. It does not repair your logs or diagnose system failures - it only counts records.

## Requirements

- No network connection is needed after downloading the ZIP with program files.
- Python 3.10 or newer. No other software or packages are required.
- A CSV file with the column headers `timestamp`, `level`, and `message`.


## Usage

LogLens needs no installation. You run the script directly with Python from the repository root (the folder that contains `loglens.py`):

```bash
python loglens.py --file <path-to-your-csv> --level <LEVEL>
```

`--file` is the path to your CSV log file. `--level` is optional and accepts `INFO`, `WARN`, or `ERROR`; if you leave it out, LogLens counts all records in the file.

For step-by-step setup, a sample file to test with, the full list of options, and troubleshooting, see the [installation guide](docs/INSTALL.md).

## Getting help

If something goes wrong, check the "Problems and fixes" section of the [installation guide](docs/INSTALL.md).

Still stuck? Open a GitHub issue in this repository with the command you ran and the error you got. Don't post your real log file: include a small example with any private data removed.