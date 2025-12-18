# Alpega Group INET Trading Bot

## Overview

The **Alpega Group INET Trading Bot** is an automated trading assistant designed to interact with the Alpega Group INET platform via a web interface. The bot runs in a **headless Chromium** environment using **Playwright**, is built with **Node.js**, and is intended to be deployed on a **VPS**. A lightweight **Web GUI** is provided for configuration, monitoring, and operational control.

---

## Key Features

* Automated interaction with the Alpega Group INET web platform
* Headless browser automation using Chromium
* Robust and reliable Playwright-based workflows
* Web-based GUI for configuration and monitoring
* Designed for 24/7 execution on a VPS
* Configurable trading rules and execution intervals
* Logging and basic error handling

---

## Technology Stack

* **Runtime:** Node.js (LTS recommended)
* **Automation:** Playwright
* **Browser:** Chromium (headless)
* **Frontend (GUI):** HTML / CSS / JavaScript
* **Backend:** Node.js (Express or similar)
* **Deployment:** Linux VPS

---

## Prerequisites

Before installing the bot, ensure the following are available:

* Node.js (v22+ recommended)
* npm or yarn
* A Linux-based VPS (Ubuntu 20.04+ recommended)
* Access credentials for the Alpega Group INET platform
* Stable internet connection

---

## Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/your-org/alpega-inet-trading-bot.git
   cd alpega-inet-trading-bot
   ```

2. Install dependencies:

   ```bash
   npm install
   ```

3. Install Playwright browsers:

   ```bash
   npx playwright install chromium
   ```

---

## Configuration

All runtime configuration is stored in environment variables or a configuration file.

Example `.env` file:

```env
INET_USERNAME=your_username
INET_PASSWORD=your_password
INET_BASE_URL=
BOT_INTERVAL=
HEADLESS=true
```

> **Important:** Never commit credentials or sensitive data to version control.

---

## Usage

Start the bot in production mode:

```bash
npm run start
```

Start the bot in development mode:

```bash
npm run dev
```

The bot will:

1. Launch a headless Chromium instance
2. Log in to the INET platform
3. Execute predefined trading actions
4. Repeat according to the configured interval

---

## Web GUI

The Web GUI provides:

* Bot status (running / stopped)
* Execution logs
* Basic configuration management
* Manual start / stop controls

Once the application is running, access the GUI at:

```
http://<VPS_IP>:<PORT>
```

---

## Deployment on VPS

Recommended setup:

* Ubuntu Server
* PM2 for process management
* Nginx as a reverse proxy (optional)

Example PM2 command:

```bash
pm2 start ecosystem.config.js
pm2 save
pm2 startup
```

Ensure the VPS has sufficient memory for headless Chromium execution.

---

## Logging and Monitoring

* Application logs are written to the `logs/` directory
* Errors and browser crashes are automatically captured
* PM2 integration is recommended for uptime monitoring

---

## Security Considerations

* Use strong passwords and, if possible, IP restrictions
* Store credentials securely using environment variables
* Regularly update dependencies
* Restrict access to the Web GUI (VPN, firewall, or authentication)

---

## Disclaimer

This software is provided "as is", without warranty of any kind. The authors are not responsible for any financial losses, account restrictions, or legal consequences resulting from the use of this bot. Ensure that automation complies with Alpega Group’s terms of service and applicable laws.

---

## License

This project is licensed under the MIT License, unless stated otherwise.
