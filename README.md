# Dummy systemd Service

This project demonstrates how to create, configure, and manage a custom **systemd service** on Linux.  
The service runs a dummy background script that continuously logs a message every 10 seconds and is managed entirely using `systemctl`.

This project is based on the roadmap.sh systemd practice task:
https://roadmap.sh/projects/dummy-systemd-service

---

## Project Objective

The goal of this project is to gain hands-on experience with:

- Creating a long-running background process
- Writing a custom systemd service unit
- Managing services using systemctl
- Enabling services at boot
- Monitoring service status and logs
- Debugging and auto-restarting failed services

---

## How It Works

- `dummy.sh` runs in an infinite loop
- Every 10 seconds, it writes a log entry to `/var/log/dummy-service.log`
- `dummy.service` manages the script as a systemd service
- systemd automatically restarts the service if it fails

---

## Installation & Setup

### 1. Clone the repository

```bash
git clone https://github.com/your-username/dummy-systemd-service.git
cd dummy-systemd-service
