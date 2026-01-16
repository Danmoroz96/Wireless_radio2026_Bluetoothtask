# Wireless_radio2026_Bluetoothtask
This technical analysis explores the characteristics of Bluetooth Low Energy (BLE) devices based on measurements captured in indoor environments.

Technical Analysis
Relationship Between RSSI and DistanceThe Received Signal Strength Indicator (RSSI) measured in dBm (decibels per milliwatt) is a logarithmic representation of signal power.
Signal Decay: Radio waves decrease in energy exponentially with distance. A strong signal of -65 dBm correlates to a close proximity of roughly 2 meters.
Distance Formula: Estimated distance (d) can be calculated using the Log-Distance Path Loss Model:

![Screenshot 2026-01-16 130649](https://github.com/user-attachments/assets/7df27daf-13ff-4052-9fe9-27f9584eeadc)

where P is the Tx power at 1 meter (typically -59 to -65 dBm) and n is the environmental path loss exponent.

The following data was aggregated from multiple scans in a mixed indoor environment:

![Screenshot 2026-01-16 131114](https://github.com/user-attachments/assets/b16f9f36-c3b4-4836-b234-be918b50e4d8)

Inconsistencies: Beyond 5–6 meters, RSSI becomes highly unstable due to multi-path fading and signal reflections off walls. 
A measurement of -100 dBm is near the "noise floor," making the 112m distance estimate highly unreliable.

Environmental Interference
Physical Obstructions: Walls or human bodies can cause an immediate 6–10 dBm drop in signal.

Noise: The 2.4 GHz band is shared with Wi-Fi and microwaves, which can lead to packet loss and fluctuating RSSI readings.

Security and Privacy Considerations
BLE is the backbone of modern wearables (Apple Watch, Fitbit) and proximity systems. However, its open nature presents risks:

Passive Scanning Risks: Untrusted devices can passively "sniff" advertisement packets to obtain device identifiers, proximity, and even specific health data from unencrypted medical sensors.

Device Tracking: If a device uses a static public MAC address, it can be persistently tracked by fixed scanners in public spaces (e.g., malls or airports).

MAC Randomization: Modern devices use Resolvable Private Addresses (RPA) to change their ID frequently, though older or cheaper IoT devices may still reveal a permanent hardware address.

Final thoughts:
Bluetooth Low Energy (BLE) has become the de facto standard for short-range, power-efficient communication. Unlike "Classic" Bluetooth, BLE is designed to remain in a "sleep" state, waking up only to transmit small bursts of data, which allows devices to run for months or years on a single coin-cell battery.

Wearables: Smartwatches and fitness trackers use BLE to sync biometric data (heart rate, steps) to a smartphone while preserving battery life.

IoT Sensors: In industrial or home automation, BLE sensors monitor temperature, humidity, or motion and report back to a central gateway.

Proximity Beacons: Retailers and museums use "Non-Connectable" beacons to push location-based notifications to visitors' phones when they are within a specific range.

BLE security is a trade-off between convenience and protection. For low-risk devices like heart-rate monitors, the "Just Works" pairing is acceptable. However, for high-risk applications like smart locks or medical insulin pumps, robust Out-of-Band (OOB) pairing or Passkey Entry is mandatory to prevent unauthorized access or data breaches.

CONCLUSION:

The experiment highlights that while BLE is highly effective for low-power "zone-level" proximity (under 4m), it is unsuitable for precise ranging without advanced filtering.

