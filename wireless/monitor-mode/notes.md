# Monitor Mode Notes

## What is Monitor Mode?
Monitor mode allows a wireless adapter to capture all wireless traffic
in range, not just traffic directed at your device. Essential for
wireless reconnaissance and packet capture.

## Key Commands

### Check your wireless interface
```bash
iwconfig
```

### Kill interfering processes
```bash
sudo airmon-ng check kill
```

### Start monitor mode
```bash
sudo airmon-ng start wlan0
```

### Verify monitor mode is active
```bash
iwconfig
# Look for wlan0mon with Mode:Monitor
```

### Stop monitor mode
```bash
sudo airmon-ng stop wlan0mon
sudo service NetworkManager restart
```

## Lessons Learned
- Always run airmon-ng check kill before starting monitor mode
- wlan0 becomes wlan0mon when monitor mode is active
- Always stop monitor mode and restart NetworkManager when done

## Resources
- Aircrack-ng documentation: https://www.aircrack-ng.org/documentation.html
## Session Log
- 2026-05-21 — Created repo, set up folder structure, wrote monitor mode notes
## airodump-ng Basic Capture
### Command
```bash
sudo airodump-ng wlan0mon
```
### Key columns
- BSSID: Router MAC address
- PWR: Signal strength (closer to 0 = stronger)
- CH: WiFi channel
- ENC: Encryption type (WPA2, WPA3, OPN)
- ESSID: Network name

### Security observations
- OPN networks have zero encryption — all traffic visible
- Hidden SSIDs (length: 0) are still detected
- IoT devices often have weak or no security
- WPA3 is more secure than WPA2
