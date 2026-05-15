# Chroot Ubuntu on Android 📱🐧

A personal step-by-step setup process for running a fully functional Ubuntu environment inside Android using `chroot`.

This repository documents my own workflow for:

- Installing Ubuntu Base on Android
- Running Ubuntu with `chroot`
- Fixing networking and package management
- Hosting websites with Nginx + HTTPS
- Dynamic DNS with DuckDNS + Inadyn
- Creating additional Nginx sites easily

It is not really a “project” — more like my own notes and setup guide 🙂

---

## ⚠️ Requirements

Before starting, make sure you have:

- An Android device with:
  - Root access
  - USB debugging enabled
  - Root debugging enabled
- `adb` installed on your laptop/PC
- Internet connection
- Basic Linux terminal knowledge

---

# 📚 Guide Index

## 1. Ubuntu Installation
File: [`01_ubuntu.md`](./01_ubuntu.md)

What it covers:

- Downloading Ubuntu Base
- Extracting filesystem on Android
- Creating startup script
- Setting up chroot environment
- Fixing DNS/networking
- Making `apt` work properly

---

## 2. Nginx + HTTPS Setup
File: [`02_nginx.md`](./02_nginx.md)

What it covers:

- Installing Python, tmux, nginx
- Running background services with tmux
- Reverse proxy with Nginx
- HTTPS setup using Certbot
- DuckDNS integration
- Fixing permission issues

---

## 3. Dynamic DNS with Inadyn
File: [`03_inadyn.md`](./03_inadyn.md)

What it covers:

- Installing Inadyn
- Configuring DuckDNS updates
- IPv6 DDNS support
- Background daemon setup
- Logging and troubleshooting

---

## 4. Hosting Additional Websites
File: [`04_new_nginx_site.md`](./04_new_nginx_site.md)

What it covers:

- Creating new Nginx site configs
- Enabling websites
- SSL certificate expansion
- Hosting multiple domains

---

# ✨ Why I Made This

Most Android Linux/chroot tutorials online are either:

- incomplete
- outdated
- scattered across forums
- or missing networking fixes

So I decided to document my exact process from start to finish while setting everything up myself.

If this helps someone else turn an old Android phone into a tiny Linux server, even better 🚀

---

# 🛠️ What You Can Do With This

Once configured, your Android device can become:

- A small web server
- A static website host
- A personal cloud server
- A development environment
- A lightweight always-on Linux machine
- A self-hosted experiment box

---

# 📌 Notes

- These guides were written from my own setup experience.
- Commands may need slight adjustments depending on your Android version/device.
- Running services as root inside chroot environments can have security implications.
- Use at your own risk.

---

# ❤️ Credits

Ubuntu Base:
https://cdimage.ubuntu.com/ubuntu-base/releases/

DuckDNS:
https://www.duckdns.org/

Nginx:
https://nginx.org/

Certbot:
https://certbot.eff.org/

---

# 📜 License

MIT — do whatever you want with it.

