# PythMap1 - Advanced Network Port Scanner

PythMap1 is a fast, user-friendly port scanner written in Python. It uses **python-nmap** for reliable SYN scanning, performs banner grabbing, attempts service version detection, and runs basic Nmap vulnerability scripts on discovered open ports. Results are automatically saved in JSON format.

The tool is designed to work out-of-the-box: on first run it can create and activate its own virtual environment and automatically install the required dependencies (`python-nmap` and `scapy`).

**Author:** TheBitty  
**Requires root/admin privileges** for raw packet (SYN) scans.

## Features

- Fast SYN scanning with progress bar  
- Automatic virtual environment creation and dependency installation  
- Banner grabbing on common services  
- Basic service version detection from banners  
- Optional Nmap NSE vulnerability scanning (`--script vuln,exploit,auth,default,version`)  
- JSON report generation with timestamps, hostnames, banners, and vuln results  
- Clean console output and detailed file logging  

## Requirements

- Python 3.8+  
- Nmap must be installed and available in PATH  
- Root / Administrator privileges (required for SYN scans)  

## Installation & First Run

Just clone and run – everything else is handled automatically:

```bash
git clone https://github.com/1x0DF0/PythMap1.git
cd PythMap1
python pythmap1.py
```

On the **first execution** the script will:
1. Create a local `venv` folder (if it doesn’t exist)
2. Install `python-nmap` and `scapy` inside it
3. Restart itself using the virtual environment’s Python interpreter

Subsequent runs will be instant.

## Usage

Simply execute the script (with sudo on Linux/macOS or as Administrator on Windows):

```bash
sudo python pythmap1.py
```

You will be prompted interactively for:

1. Target IP address  
2. Port range (predefined options or custom)  

The scanner will then:
- Perform a fast SYN scan of the chosen range
- Grab banners from open ports
- Attempt to identify service versions
- Run basic vulnerability scripts on open ports
- Save a detailed JSON report in the `logs/` folder

## Example Output Files

```
logs/scan_192.168.1.1_2025-11-27_14-30-22.json
```

The JSON contains full metadata, open ports, detected services, banners, and any vulnerability script output.

## Disclaimer

This tool is intended for **authorized security testing and educational purposes only**.  
Scanning networks or systems without explicit permission is illegal in most jurisdictions.  
The author is not responsible for any misuse or damage caused by this program.

## License

MIT License – see the `LICENSE` file (if present) for details.

Happy scanning (responsibly)!
