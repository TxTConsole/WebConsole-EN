<img width="1916" height="945" alt="изображение" src="https://github.com/user-attachments/assets/e35fc8a3-f1f6-4b43-b178-18dd477aaeca" />

## 🚀 **What is WebConsole?**

**WebConsole** is a powerful web-based administration panel for Minecraft servers running on **Paper**, **Spigot**, or **Purpur**. It allows you to fully manage your server through a browser from your computer.

Say goodbye to SSH or RDP just to run a simple command or check the console. With WebConsole, everything is accessible through a modern neon-glass interface with real-time updates.

**[Download Plugin SpigotMC](https://www.spigotmc.org/resources/webconsole.133712/)**
**[Russian Version Plugin](https://github.com/TxTConsole/WebConsole-RU)**

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
# ==========================
# WebConsole Configuration
# Version -> v1.1-SNAPSHOT
# Discord -> @txt.console
# ==========================
    
# Web control panel settings.
server:
  # Port where the panel will be accessible (e.g., http://server-ip:8080)
  port: 8080
  # IP binding. 0.0.0.0 allows external connections.
  host: "0.0.0.0"

# Default language for the panel (ru / en).
# - Changes the language of ALL panel strings on first visit.
# - Changes the console welcome message on server startup.
# - If an admin selects a different language in the panel itself, it is saved
#   personally for them (persists across restarts) and won't be overridden by this value.
lang: en

security:
  # Duration of authorized session in hours
  session-timeout-hours: 24

  # Brute-force protection
  max-failed-attempts: 5
  # Command executed by the server when login attempt limit is exceeded
  # Variables: %ip%, %username%
  punishment-command: "ban-ip %ip% Exceeded WebConsole login attempts"
  # IP lock duration in the web panel (in minutes)
  lockout-minutes: 30

  # ==========================================================
  # Panel user list.
  #
  # Each user has their own password and set of permissions.
  # Format:
  #    <username>:
  #      password: "<password>"
  #      permissions:
  #        <permission>: <true/false>
  #
  # If a user does NOT have a permissions block specified, they get EVERYTHING
  # (full administrator access).
  #
  # Available permissions:
  # -----------------
  # console            -> "Server Console" section and command execution
  # players            -> "Online Players" section
  # files              -> "Files" section
  # plugins            -> "Plugins" section (search and install plugins)
  # logs               -> "Action Logs" section
  # server_settings    -> "Server Settings" in the settings tab
  # sanctions          -> punishments: ban / mute / kick / unban / unmute
  # ops                -> granting and revoking operator status
  # whitelist          -> whitelist management
  # file_edit          -> creating and editing files (including uploading).
  #                       IMPORTANT: even with this permission, you cannot create or
  #                       upload files inside plugins/ folder without the
  #                       plugins permission below.
  # file_delete_download-> deleting and downloading files
  # mod_folder         -> access to WebConsole plugin folder via "Files".
  #                       WITHOUT it, you cannot enter the folder, or download/delete
  #                       the plugin's own jar file.
  # wc_reload          -> command /wc reload (reloading WebConsole panel).
  #                       By default, this permission equals mod_folder: if the
  #                       administrator has no access to the plugin folder, command
  #                       is forbidden. If access exists, reload can be configured separately.
  # server_control     -> restarting and stopping the server
  # logs_manage        -> deleting and downloading server logs.
  #                       WITHOUT this permission, the user CANNOT enter
  #                       logs and crash-reports folders even with access
  #                       to "Files", or open log archives.
  #
  # Old format (username: "password") also works — such a user
  # gets all permissions automatically (full access).
  # ==========================================================
  users:
    admin:
      password: "admin_password_here"
      permissions:
        console: true
        players: true
        files: true
        plugins: true
        logs: true
        server_settings: true
        sanctions: true
        ops: true
        whitelist: true
        file_edit: true
        file_delete_download: true
        mod_folder: true
        server_control: true
        logs_manage: true
        wc_reload: true
    moderator:
      password: "mod_secret_123"
      permissions:
        console: true
        players: true
        files: true
        plugins: false
        logs: true
        server_settings: false
        sanctions: true
        ops: false
        whitelist: false
        file_edit: true
        file_delete_download: false
        mod_folder: false
        server_control: false
        logs_manage: false
        wc_reload: false
    developer:
      password: "dev_pass_2026"
      permissions:
        console: true
        players: false
        files: true
        plugins: true
        logs: false
        server_settings: true
        sanctions: false
        ops: false
        whitelist: false
        file_edit: true
        file_delete_download: true
        mod_folder: true
        server_control: false
        logs_manage: true
        wc_reload: true

# ============================================================
# Moderation System (Ban / Mute / Kick)
# ============================================================
# If a known moderation plugin is installed (e.g. LiteBans), it is
# detected automatically and Ban/Mute buttons are activated.
#
# If using a custom plugin — set commands below and set
# enabled: true. Reload our plugin after editing this file.
# Variables: %player% %reason% %duration% (empty duration = permanent)
# Auto-detected plugins: LiteBans, AdvancedBan, LightBans.
# If you use one of these, you can leave command empty for auto-matching.
moderation:
  ban:
    enabled: false
    command: ""
    # Example for LiteBans/AdvancedBan/LightBans (empty = auto-detect):
    # command: "litebans:ban %player% %duration% %reason%"
    # Unban command. Variable: %player%
    unban-command: ""
    # command: "litebans:unban %player%"
  mute:
    enabled: false
    command: ""
    # command: "litebans:mute %player% %duration% %reason%"
    # Unmute command. Variable: %player%
    unmute-command: ""
    # command: "litebans:unmute %player%"
  kick:
    # Kick uses native Minecraft commands, so it is always available.
    enabled: true
    command: "kick %player% %reason%"

# ============================================================
# PLUGINS Section (Plugin search/installation feature)
# ============================================================
# Modrinth works without a key. CurseForge requires a free
# API key: register at https://console.curseforge.com
# and specify the key below (or enter it in panel settings).
plugins:
  curseforge-api-key: ""
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

<img width="1916" height="945" alt="изображение" src="https://github.com/user-attachments/assets/e35fc8a3-f1f6-4b43-b178-18dd477aaeca" />
<img width="1917" height="942" alt="изображение" src="https://github.com/user-attachments/assets/aa96855c-6b79-4bc2-ae8f-fa73cf89c412" />
<img width="1917" height="944" alt="изображение" src="https://github.com/user-attachments/assets/ca1cb820-90b0-4b92-b840-2d920a8d3a33" />
<img width="1915" height="944" alt="изображение" src="https://github.com/user-attachments/assets/01fd5bd4-4d6b-43f6-8f4e-7db0e21d4d38" />
<img width="1916" height="946" alt="изображение" src="https://github.com/user-attachments/assets/6cfdc606-4938-458a-ab98-4b5add4bf86e" />
<img width="1918" height="944" alt="изображение" src="https://github.com/user-attachments/assets/96b42f19-6893-47a7-9c6f-383366de595f" />
<img width="1916" height="943" alt="изображение" src="https://github.com/user-attachments/assets/14951d72-fad7-4307-a3a2-91b49d240ff8" />

---

## 🧩 **Requirements**

- **Server:** Version 1.21+ (also works on Spigot, Purpur, Paper)
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
- Star the repository on GitHub
- Share with other server administrators

---

**Thank you for using WebConsole!**  
*— Manage your Minecraft server like never before.*
