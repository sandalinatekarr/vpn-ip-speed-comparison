# VPN Privacy Lab Report – Speed & IP Comparison

## 1. Objective

The experiment aimed to:

1. Connect to a free VPN and verify tunneling.
2. Record IP addresses and geolocation before and after connecting.
3. Run speed tests in both scenarios.
4. Compare performance metrics (download speed, latency) and privacy changes.
5. Provide screenshot evidence.

---

## 2. Test Environment

- **Date:** 15 Aug 2025
- **Operating System:** macOS 10.15.7 (Catalina)
- **Device:** MacBook (Intel-based)
- **VPN Service:** ProtonVPN (Free Tier)
- **VPN Protocol:** WireGuard
- **VPN Server (Connected State):** Los Angeles, California, USA
- **ISP (Disconnected State):** Bharti Airtel Ltd., India
- **Testing Websites:**
  - [WhatIsMyIPAddress.com](https://whatismyipaddress.com)
  - [Fast.com](https://fast.com)
  - [Example.com](https://example.com) for HTTPS encryption check

---

## 3. Methodology

### Step 1 – Baseline (VPN Disconnected)
1. Verified public IP and geolocation using WhatIsMyIPAddress.com.
2. Ran speed test using Fast.com.
3. Saved screenshots of results.

### Step 2 – VPN Connection
1. Launched ProtonVPN, selected a free server in the USA.
2. Verified VPN connection (green shield indicator).
3. Checked new public IP and geolocation.
4. Ran speed test again.
5. Saved screenshots of results.

### Step 3 – Analysis
- Compared IP changes, geolocation masking, and speed differences.
- Noted encryption status (HTTPS padlock check).
- Recorded any usability differences (latency, captchas, blocked sites).

---

## 4. Results

| State        | IPv4 Address            | IPv6 Address                                         | ISP                  | Country   | City         | Location Accuracy           | Download Speed (Mbps)  | Notes |
|--------------|------------------------|------------------------------------------------------|----------------------|-----------|-------------|-----------------------------|------------------------|-------|
| **Connected**    | 146.70.174.68           | Not detected                                        | M247 Europe SRL      | USA       | Los Angeles | VPN detected                | ~0.19 Mbps              | Very slow due to VPN server distance |
| **Disconnected** | 110.226.180.85          | 2401:4900:1c20:2d3b:85bf:6e92:b281:cba9              | Bharti Airtel Ltd.   | India     | Delhi       | Location may be exposed     | Not displayed           | Direct ISP connection |

---

## 5. Observations

- **IP Masking:** VPN replaced the Indian ISP IP with a US-based IP.
- **IPv6 Handling:** VPN did not assign IPv6; only IPv4 was active while connected.
- **Speed Impact:** Download speed dropped significantly while on VPN (likely due to server distance and free-tier bandwidth limits).
- **Encryption:** HTTPS padlock confirmed end-to-end TLS encryption in both cases; VPN added an extra encrypted tunnel.
- **Latency:** Noticeable delay when browsing with VPN connected to a distant server.
- **Usability:** No DNS leaks observed; however, certain sites may show captchas when on VPN.

---

## 6. Screenshot Evidence

### VPN Connected
1. **VPN Interface** – [`vpn_connected_ui.png`](vpn_connected_ui.png)  
2. **Speed Test** – [`vpn_connected_speed.png`](vpn_connected_speed.png)  
3. **IP Information** – [`vpn_connected_ip.png`](vpn_connected_ip.png)  

### VPN Disconnected
4. **VPN Interface** – [`vpn_disconnected_ui.png`](vpn_disconnected_ui.png)  
5. **Speed Test** – [`vpn_disconnected_speed.png`](vpn_disconnected_speed.png)  
6. **IP Information** – [`vpn_disconnected_ip.png`](vpn_disconnected_ip.png)  

---

## 7. Conclusions

- **Privacy Gain:** VPN effectively masked original IP and geolocation.
- **Performance Trade-off:** VPN caused a significant speed reduction when connected to a distant server.
- **Security Improvement:** All traffic between device and VPN server was encrypted, reducing exposure on untrusted networks.
- **Limitations:** Free VPN servers may be congested and slower; IPv6 was not supported in this test.

---

## 8. Recommendations

- Use **geographically closer VPN servers** to improve speed.
- For higher performance, consider paid plans or modern protocols like WireGuard.
- Always verify **DNS leak protection** and **kill switch** features.
- Remember: VPN is not full anonymity — combine with browser privacy practices.

---
