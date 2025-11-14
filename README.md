# gcloud-for-cybersec

A complete guide for installing and using Google Cloud CLI (`gcloud`) for cybersecurity purposes, including multi-platform installation and understanding limitations.

## Why Use gcloud for CyberSec?

* ⚡ Faster **password/hash cracking** using tools like `john` & `hashcat`
* 🌐 Very stable **internet connection** → better recon and subdomain enumeration
* 💾 **Access to cloud storage & VM resources** (5 GB free storage, optional paid upgrades)
* 🐧 Clean Linux-like environment → ideal for real-world pentesting and red-team labs
* 📡 Freedom to run long scans without draining your device battery
* 🛡 Very useful for OSCP-style labs, TryHackMe, HackTheBox, and CTF challenges

## Installation

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

### Windows

Download installer: [Google Cloud SDK Windows Installer](https://cloud.google.com/sdk/docs/install#windows)

Run:

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

### Fix Component Errors (If Required)

```bash
~/google-cloud-sdk/install.sh --override-components
```

## Limitations / Risks

* 📦 **Free tier is limited**: Only 5 GB of Cloud Storage per month in certain regions.
* ⏳ **VM free-tier constraint**: Only small VM (e2-micro) is always free, limited to certain regions.
* 📉 **Network / egress costs**: Exceeding free-tier usage can incur charges.
* ⚠️ **Billing complexity**: Unexpected charges may occur if free-tier limits are exceeded.
* 🔒 **Permission / scope risks for pentesting**: Cloud accounts may have strict IAM policies.
* 🏷 **Limited free credit**: New users get $300 trial, after which costs apply for additional resources.

## Notes

* Use the SDK responsibly for cybersecurity learning and testing.
* Monitor billing / usage in Google Cloud Console.
* Free-tier quotas and resources vary by region.

---

Made by Aryan © 2025
