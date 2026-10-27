# Network Device Monitor

A Python-based network monitoring tool that automates device connectivity checks, identifies unreachable devices, and logs network status to support troubleshooting.

## Overview

Network Device Monitor is a command-line application built with Python to monitor the availability of devices on a network.

The application uses ICMP ping requests to check configured IP addresses at regular intervals, reports whether devices are reachable, and records results with timestamps for later analysis.

This project demonstrates Python automation, networking fundamentals, configuration management, and error handling.

## Features

- **Automated Connectivity Checks:** Periodically checks multiple network devices using ICMP ping requests.
- **Device Status Monitoring:** Displays ONLINE or OFFLINE status for each configured device.
- **Configurable Monitoring:** Uses a JSON configuration file to manage IP addresses and monitoring intervals.
- **Status Logging:** Records connectivity results with timestamps in a log file.
- **Error Handling:** Handles ping timeouts and command execution errors.
- **Cross-Platform Support:** Supports ping commands on macOS, Linux, and Windows.

## Technologies Used

- Python 3
- TCP/IP Networking
- ICMP Ping
- JSON
- Python Standard Library (`subprocess`, `platform`, `logging`, `datetime`, `time`)

## Project Structure

```text
network-device-monitor/
├── main.py
├── monitor.py
├── devices.json
├── README.md
└── .gitignore
```

The application automatically creates `network.log` when logging connectivity results.

## Installation

**1. Clone the repository**

```bash
git clone https://github.com/Ashrith100/Network-Device-Monitor-.git
```

**2. Navigate to the project directory**

```bash
cd Network-Device-Monitor-
```

**3. Run the application**

```bash
python3 main.py
```

No third-party Python packages are required.

## Configuration

Edit `devices.json` to specify the devices to monitor:

```json
{
  "interval": 30,
  "devices": [
    {
      "name": "Google DNS",
      "ip": "8.8.8.8"
    },
    {
      "name": "Cloudflare DNS",
      "ip": "1.1.1.1"
    },
    {
      "name": "Local Router",
      "ip": "192.168.1.1"
    }
  ]
}
```

The `interval` parameter controls how frequently the application checks device connectivity, in seconds.

## Example Output

```text
Network Device Monitor Started
Press Ctrl+C to stop.

Scan: 2026-10-26 21:00:00
---------------------------------------------
Google DNS           8.8.8.8          ONLINE
Cloudflare DNS       1.1.1.1          ONLINE
Local Router         192.168.1.1      OFFLINE
---------------------------------------------
```

Actual results depend on network connectivity and whether devices respond to ICMP requests.

## How It Works

1. Loads device information and monitoring settings from `devices.json`.
2. Executes a ping request for each configured IP address.
3. Evaluates the command's return code to determine reachability.
4. Displays the results in the terminal.
5. Records connectivity status and timestamps in `network.log`.
6. Repeats the process at the configured interval until stopped.

## Future Improvements

- Track device response times and latency.
- Detect status changes and generate outage alerts.
- Calculate device uptime and downtime statistics.
- Export monitoring results to CSV.
- Build a web dashboard for network visualization.

## Author

**Ashrith Kanala**

[GitHub](https://github.com/Ashrith100) | [LinkedIn](https://www.linkedin.com/in/ashrith-kanala)
