<img width="1237" height="962" alt="image" src="https://github.com/user-attachments/assets/e399efa1-29f9-4a22-849a-f5e4f97f90f3" />

## 🚀 **What is WebConsole?**

**WebConsole** is a powerful web-based administration panel for Minecraft servers running on **Paper**, **Spigot**, or **Purpur**. It allows you to fully manage your server through a browser from your computer.

Say goodbye to SSH or RDP just to run a simple command or check the console. With WebConsole, everything is accessible through a modern neon-glass interface with real-time updates.

**[Download Plugin SpigotMC](https://www.spigotmc.org/resources/webconsole.133712/)**
**[Russian Version Plugin](https://github.com/TxTConsole/WebConsole-RU)**
**[Download Plugin SpigotRU](https://spigotmc.ru/resources/webconsole.5257/)**

---

## ✨ **Key Features**

### 🖥️ **Real-Time Console**
- Live console output with colored log levels (INFO, WARN, ERROR)
- Search and filter logs by level or keywords
- Instant command execution
- Command history and command directory (button «?» — copy and paste command into console)
- Auto-scroll and log download

### 👥 **Player Management**
- View online players with ping and playtime
- Kick, ban, mute players directly from the interface
- Ban by IP address option
- View and manage punished players (unban, unmute)
- Whitelist and Operator (OP) management

### 📁 **File Manager (BETA)**
- Browse, edit, and delete server files directly in the browser
- Syntax highlighting for YAML, JSON, properties, Java, and other formats (powered by CodeMirror)
- Upload files via drag-and-drop or file picker
- Create new files and folders
- Download any file from the server
- Convenient path navigation

> ⚠️ **Note:** The file manager is in beta testing. Bugs and issues may occur. Please report any problems you find.

### 🧩 **Plugin Manager (BETA)**
- Search for plugins directly through Modrinth
- Automatic compatibility checking with your server version
- One-click plugin installation
- Reinstall or delete existing plugins
- Shows author, download count, and rating

> ⚠️ **Note:** The plugin manager is in beta testing. Issues may occur during installation or search. It is recommended to make backups before installing new plugins.

### ⚙️ **Server Settings**
- Visual editing of `server.properties` (port, max players, view distance, etc.)
- Toggle settings: online-mode, PvP, flight, command blocks
- Whitelist management with instant application
- Operator (OP) list management
- Difficulty selector (Peaceful, Easy, Normal, Hard)

> ⚠️ **Important:** After changing server settings, a server restart is required for changes to take effect.

### 🔐 **Security**
- Authentication with multiple user support
- Session tokens with configurable timeout
- API protection with Bearer tokens

### 🎨 **Modern Interface**
- Neon-glass design with animated background
- Fully customizable accent color and log colors
- Responsive interface optimized for PC use
- Tooltips with helpful information on every element

### 🌍 **Multi-Language Support (BETA)**
- **Russian**
- **English**

> ⚠️ **Note:** Language support is in beta testing. Translation errors or incorrect text display may occur. If you notice an error, please report it to the author.

### 🔊 **Customizable Notifications**
- Desktop-style pop-up notifications
- Sound alerts (upload your own audio file)
- Choose notification position (top/bottom, left/right)
- Test notification button

---

## 🔧 **Installation**

1. Download the latest `WebConsole.jar`
2. Place it in your server's `plugins/` folder
3. Restart your server
4. Open your browser on your computer and go to `http://your-server-ip:8080`
5. Log in with default credentials:
   - Username: `admin`
   - Password: `admin123`
6. **Be sure to change the password** in `plugins/WebConsole/config.yml`

---

## 📋 **Configuration (`config.yml`)**

```yaml
# ==========================================
# WebConsole Configuration v1.0.0
# ==========================================

server:
  # Port for the web interface
  # Server restart required after changing
  port: 8080

security:
  # Enable authentication (true/false)
  # If false, access will be open without a password (not recommended!)
  enabled: true

  # Session timeout in hours (for those who check "Remember me")
  # Re-authentication required after timeout
  session-timeout-hours: 24

  # User list (username: "password")
  # You can add any number of users
  users:
    admin: "admin123"
    moderator: "mod123"
    # user: "password" - example of adding a new user

  # Allow command execution from web console (true/false)
  # If false, the command input will be disabled
  allow-commands: true

console:
  # Maximum number of lines stored in memory
  # Higher values consume more RAM
  max-history-limit: 500

  # Time format in logs
  time-format: "HH:mm:ss"

# System messages
messages:
  server-started: "WebConsole started on port"
  access-denied: "You do not have permission to execute this command"
```

---

## 💡 **Why WebConsole?**

- **No external dependencies** — runs on built-in Java HTTP server
- **Works out of the box** — zero configuration
- **Security** — token-based authentication with session timeout
- **Lightweight** — minimal impact on server performance
- **Open Source** — hosted on GitHub under GPL-3.0 license

---

## 📸 **Screenshots**

<img width="1237" height="960" alt="image" src="https://github.com/user-attachments/assets/67886a7f-e894-432a-81c4-8e817257c797" />
<img width="1237" height="964" alt="image" src="https://github.com/user-attachments/assets/e30de701-79e7-456c-ba26-20d320cabd63" />
<img width="1237" height="965" alt="image" src="https://github.com/user-attachments/assets/c90b72ae-d223-4aae-bccd-f18d7b6e70b8" />
<img width="1237" height="964" alt="image" src="https://github.com/user-attachments/assets/032b6810-b18b-4a25-a872-51d215053851" />
<img width="1238" height="963" alt="image" src="https://github.com/user-attachments/assets/160c8259-98f5-4fae-87b1-1cfd6f36f9b8" />
<img width="1237" height="964" alt="image" src="https://github.com/user-attachments/assets/72356ab8-1048-4a5b-bb98-30952dae7cba" />
<img width="1237" height="963" alt="image" src="https://github.com/user-attachments/assets/29fa1f4f-2f60-4cf6-bc25-5f5395c5fe7c" />
<img width="1237" height="962" alt="image" src="https://github.com/user-attachments/assets/fb2f9977-3aea-4df2-a67a-72e188602ca8" />



---

## 🧩 **Requirements**

- **Server:** Paper 1.21.4 (also works on Spigot, Purpur)
- **Java:** 21
- **Browser:** Any modern browser (Chrome, Firefox, Edge)

---

## 🔗 **Links**

- **Source Code EN:** [GitHub Repository](https://github.com/TxTConsole/WebConsole-EN)
- **Source Code RU:** [GitHub Repository](https://github.com/TxTConsole/WebConsole-RU)
- **Report Issues / Suggestions:** Discord — @txt.console

---

## 📜 **License**

This project is licensed under the **GNU General Public License v3.0**.

You may:
- Use the plugin on any server
- Modify the source code
- Distribute modified versions

You must:
- Keep the same license
- Provide access to the source code
- Credit the original author

---

## 🍀 **Additional information**

- **Author:** TxT | </> Console
- **Design:** Custom neon-glass theme
- **Libraries Used:**
  - CodeMirror — syntax highlighting editor
  - Gson — JSON parsing
  - Java-WebSocket — WebSocket server
  - Apache Commons FileUpload — file upload handling
  - Modrinth API — plugin search and installation

---

## ❓ **Frequently Asked Questions**

**Q: Can I use this on a public server?**  
A: Yes, but be sure to change the default password and use HTTPS if possible.

**Q: Does it work with BungeeCord / Velocity?**  
A: Currently designed for Purpur/Spigot/Paper servers only. Proxy support may come in future updates.

**Q: How do I restart the server?**  
A: Click the "Restart" button in the top bar. The server will save all data and restart.

---

## 🐛 **Reporting Issues**

If you find a bug or have a suggestion:

1. Check if a similar issue already exists on GitHub
2. If you don't find similar suggestions or issues — write to Discord: **@txt.console**

---

## ⭐ **Support the Project**

If you find WebConsole useful, you can:
- Leave a review on SpigotMC
- Leave a review on SpigotRU
- Star the repository on GitHub
- Share with other server administrators

---

**Thank you for using WebConsole!**  
*— Manage your Minecraft server like never before.*
