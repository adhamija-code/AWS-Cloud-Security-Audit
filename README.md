## 🛡️ Network Packet Sniffer & Intrusion Detector (Windows + Jupyter, PyShark)
This project is a lightweight **Intrusion Detection System (IDS)** built in **Python** using **PyShark** and **TShark**, designed specifically to work inside **Jupyter Notebooks on Windows**.

It captures live network traffic and detects:
- ⚠️ **Port scanning attempts** (e.g., from tools like `nmap`)
- 📄 Logs alerts to a file with timestamps
- ✅ Fully compatible with **Jupyter Notebook** (uses `tshark` subprocess to avoid async conflicts)

---

## 📦 Features

- 🔍 Real-time packet capture using **TShark**
- 🧠 Detects port scanning using **sliding time windows**
- 📝 Alerts are printed and logged to `pyshark_ids_jupyter_log.txt`
- 💻 Runs smoothly inside **Jupyter**, avoids `asyncio` issues
- 📁 Automatically deletes temporary PCAP files after analysis

---

## 🛠️ Requirements

- Python 3.7+
- [Wireshark](https://www.wireshark.org/download.html) with `TShark` installed
- `Npcap` (comes with Wireshark)
- Python packages:

  pip install pyshark nest_asyncio colorama

⚙️ How It Works
1. List available interfaces

**list_interfaces()**

This shows interface UUIDs like:

**[0] \Device\NPF_{UUID1}
[1] \Device\NPF_{UUID2}**

2. Run the sniffer

**run_pyshark_sniffer(r"\Device\NPF_{YOUR_INTERFACE_UUID}", packet_count=100)**
Replace YOUR_INTERFACE_UUID with your actual interface (usually Wi-Fi or Ethernet).

## 📁 Log Output Example

[2025-05-28 18:02:15] ALERT: Port scan detected from 192.168.1.25 on multiple ports
Saved to pyshark_ids_jupyter_log.txt.
