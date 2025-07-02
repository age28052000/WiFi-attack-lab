# WiFi Deauth + Handshake Capture + WPA2 Bruteforce

This repository documents and contains scripts and captures for a WiFi attack performed with the following steps:

1. Installing and testing a new external WiFi antenna to optimize signal strength.
2. Deauthentication attack (deauth) to force client reconnection and capture the handshake.
3. Brute forcing the captured handshake to crack the WPA2 password.

## Requirements

- An external WiFi card capable of monitor mode and packet injection.
- Tools: `airdump-ng`, `aircrack-ng`, `hcxdumptool` for capture and cracking.
- Optional: `Wireshark` to visualize the captured handshake.

## Usage

1. Installing and testung external WiFi antenna
We will use our antenna in a Kali Linux enviroment, installed over a VMWare machine. First of all we have to add the usb external device to our machine, sometimes it doesnt appear, for this we will go to the settings of the machine
then we go add and usb external...

2. Deauth attack and capturing the handshake
For this step, we will need to analyze the network devices first of all, to know which network is the one we will try to attack. We can check 2 things, first of all if it has WPS active, and we could realise attacks with reven.
And second of all which one is the best one to attack, for this we will use sudo airodump <interface>
We see all the networks in range, and after we know which one we want to use we will start the deauth attack. We can do this attack with air... -a <BSSID> -<MAC of the device>

3. Cracking WPA2 password
We need the file .cap generated in the previous step, and also we will need the dictionary to try brute force, we can use SecList, rockyou, or a custom dictionary using tools as crunch.
