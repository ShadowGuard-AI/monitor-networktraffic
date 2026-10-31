![Banner](banner.png)

# monitor-networktraffic
Monitor network traffic for unusual patterns by counting packets per source and destination IP pair, and warning once per pair when that count passes a threshold. Uses `scapy` to capture and analyze packets. Packet counts per pair are the only measure: the tool does not measure data transfer rates or byte counts. - Focused on System monitoring and alerts

## Install
`git clone https://github.com/ShadowStrikeHQ/monitor-networktraffic`

## Usage
`python main.py [params]`

A threshold that is not positive is refused at startup with exit 1. If packet capture fails, the run reports the real number of packets captured and exits 1.

## Parameters
- `-h, --help`: Show help message and exit
- `-i, --interface`: Network interface to monitor (e.g., eth0, wlan0). If not specified, scapy's default interface will be used.
- `-f, --filter`: BPF filter (e.g., 'tcp port 80', 'host 192.168.1.1').
- `-t, --threshold`: Threshold for packet count to flag a connection as suspicious (default: 1000).
- `-n, --number`: Number of packets to capture. If 0, capture indefinitely.
- `-d, --destination`: Monitor traffic to a specific IP address.
- `--log-level`: Set the logging level.
- `--pcap`: Enable saving captured packets to a pcap file.

## License
Copyright (c) ShadowStrikeHQ
