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
