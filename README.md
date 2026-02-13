README.md (FULL FILE)
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
2. Create service directory
sudo mkdir -p /opt/dummy-service
sudo cp dummy.sh /opt/dummy-service/
sudo chmod +x /opt/dummy-service/dummy.sh
3. Create log file
sudo touch /var/log/dummy-service.log
sudo chmod 644 /var/log/dummy-service.log
4. Install systemd service
sudo cp dummy.service /etc/systemd/system/dummy.service
sudo systemctl daemon-reload
Service Management Commands
Start the service
sudo systemctl start dummy
Stop the service
sudo systemctl stop dummy
Enable service at boot
sudo systemctl enable dummy
Disable service at boot
sudo systemctl disable dummy
Check service status
sudo systemctl status dummy
Viewing Logs
Live logs via journalctl
sudo journalctl -u dummy -f
View log file directly
tail -f /var/log/dummy-service.log
Auto-Restart Testing

Kill the service process manually:

ps aux | grep dummy.sh
sudo kill -9 <PID>

Check status again:

sudo systemctl status dummy

The service should restart automatically, proving systemd fault recovery is working.

Skills Demonstrated

Linux system administration

systemd service creation

Process supervision and recovery

Logging and monitoring

Production-style service management

Reference

Project inspiration and requirements from:
https://roadmap.sh/projects/dummy-systemd-service
