# How to set up and use LogLens
 
This guide shows you how to get LogLens on your computer, run it on the included sample file and then run it on your own CSV log file. Previous experience with CSV and terminal is assumed.
 
## Things you need
 
- Python 3.10 or newer. No other software or packages are required.
- A CSV log file with the column headers `timestamp`, `level`, and `message`.

LogLens runs entirely on your computer and does not upload or store your logs. No network connection is needed.
 
To check your Python version, run:
 
```bash
python --version
```
 
On some computers, the Python command is `python3` or `py` instead of `python`. If so, use that command in every step of this guide.
 
## Getting the program
1. On the repository's GitHub page, click **Code**, then **Download ZIP**.
2. Extract the ZIP file.
3. Open a terminal in the extracted folder. This is the repository root, the folder that contains `loglens.py`.
 
## Running LogLens
 
Try LogLens on the included sample file, `data/sample_logs.csv`:
 
```bash
python loglens.py --file data/sample_logs.csv --level ERROR
```
 
Expected output:
 
```text
Records matching ERROR: 2
```
 
If you see this, LogLens is working.
 
To check your own file, replace the path with the location of your file. You don't need to copy it into the project folder.
 
```bash
python loglens.py --file <path-to-your-csv> --level ERROR
```
##### Options:
- `--file` (required): the path to your CSV log file.
- `--level` (optional): `INFO`, `WARN`, or `ERROR`, in uppercase. Leaving it out will result in counting all records.

LogLens only reads your file. It never changes it. To see all options, run:
 
```bash
python loglens.py --help
```
 
## Problems and fixes
 
- **`File not found: <path>`**: LogLens can't find the file. Check the path, and make sure you are running the command from the repository root.
- **`Cannot read file: <path>`**: you don't have permission to read the file. Check the file's permissions, or use a copy you are allowed to read.
- **`CSV must contain timestamp, level, and message columns`**: the first line of your file doesn't have the right headers. Rename them to `timestamp`, `level`, and `message`.

If none of these help, open a GitHub issue in this repository with the command you ran and the error you got. Don't post your real log file - include a small example with any private data removed.