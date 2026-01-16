# gcloud-for-cybersec

A complete guide for installing and using Google Cloud CLI (`gcloud`) for cybersecurity purposes, including multi-platform installation, connecting via Cloud Shell CLI, and understanding limitations.

## Why Use gcloud for CyberSec?

* ⚡ Faster **password/hash cracking** using tools like `john` & `hashcat`
* 🌐 Very stable **internet connection** → better recon and subdomain enumeration
* 💾 **Access to cloud storage & VM resources** (5 GB free storage on Always Free, optional paid upgrades)
* 🐧 Clean Linux-like environment → ideal for real-world pentesting and red-team labs
* 📡 Freedom to run long scans (Nmap, ffuf, gobuster, nuclei) without draining your device battery
* 🛡 Very useful for OSCP-style labs, TryHackMe, HackTheBox, and CTF challenges

## Platform-Specific Installation

### Linux (Ubuntu / Debian / Kali / PopOS)

```bash
sudo apt update && sudo apt upgrade -y
sudo apt install curl -y
curl -O https://dl.google.com/dl/cloudsdk/channels/rapid/downloads/google-cloud-cli-*.tar.gz
tar -xf google-cloud-cli-*.tar.gz
sudo ./google-cloud-sdk/install.sh
gcloud init
```

### macOS

```bash
brew install --cask google-cloud-sdk
exec -l $SHELL
gcloud init
```
### Browser : 

https://shell.cloud.google.com/

### Windows

Download installer: [Google Cloud SDK Windows Installer](https://cloud.google.com/sdk/docs/install#windows)

Then run:

```bash
gcloud init
```

### Termux (Android)

```bash
pkg update && pkg upgrade -y
pkg install curl openssh -y
curl https://sdk.cloud.google.com | bash

# Add gcloud to PATH
echo 'export PATH=$PATH:$HOME/google-cloud-sdk/bin' >> ~/.bashrc
source ~/.bashrc

gcloud init --console-only
```
### Android play store :

https://play.google.com/store/apps/details?id=com.google.android.apps.cloudconsole

### Connecting via Cloud Shell CLI

```bash
gcloud alpha cloud-shell ssh
```

### Fix Component Errors (If Required)

```bash
~/google-cloud-sdk/install.sh --override-components
```

## Limitations / Risks

* 📦 **Free tier is limited**: Only 5 GB of Cloud Storage per month.
* ⏳ **VM free-tier constraint**: Only a small VM (e2-micro) is always free, in specific regions.
* 📉 **Egress / network costs**: Exceeding free-tier usage can incur charges.
* ⚠️ **Billing complexity**: Unexpected charges can occur if free-tier limits are exceeded.
* 🔒 **Permission / scope risks for pentesting**: Cloud accounts may have strict IAM policies.
* 🏷 **Limited free credit**: New users get $300 trial, after which paid resources apply.

## Notes

* Use the SDK responsibly for cybersecurity learning and testing.
* Monitor billing / usage in Google Cloud Console.
* Free-tier quotas vary by region.

---

Made by Aryan © 2025
