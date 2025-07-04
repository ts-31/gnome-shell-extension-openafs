#  OpenAFS Client Manager — GNOME Shell Extension

> **GSoC 2025 Project** under the [OpenAFS](https://www.openafs.org/) organization

## 📌 Overview

This GNOME Shell extension aims to provide a **graphical interface** for managing the **OpenAFS** client on Linux desktops. OpenAFS is a powerful distributed file system widely adopted in academic and research settings, but its reliance on CLI tools can make it less approachable for everyday users.

This extension simplifies and enhances user interaction with OpenAFS by integrating a GUI directly into the GNOME Shell top bar.

---

## ✨ Features

- ✅ Start/Stop the OpenAFS client via systemd
- ✅ Acquire/manage Kerberos authentication tokens
- ✅ View token expiration and cell connectivity status
- 🛎️ (Stretch) Notifications for token expiry
- 🔁 (Stretch) Shortcuts to switch AFS cells

---

## 🔧 Technical Stack

- **GJS (GNOME JavaScript)** for writing the extension logic
- **GNOME Shell APIs** for UI and system integration
- **GLib.spawn_command_line_async** for commands like:
  - `systemctl start openafs-client`
  - `aklog` for token handling
- **GLib.spawn_async_with_pipes** for securely handling password prompts via `kinit`
- **St.Button**, **St.Label** for native GNOME-style UI elements
- **Promises and async operations** to keep UI non-blocking

---

## 📁 Project Structure

```text
gnome-shell-extension-openafs/
├── assets/
│   └── screenshot.png        # UI preview image
├── extension.js              # Core logic of the extension
├── metadata.json             # Extension metadata
├── stylesheet.css            # Optional styles
└── README.md                 # Project documentation
```

---

## 🚀 Installation & Testing Instructions

Follow these steps to install and test the extension locally:

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/ts-31/gnome-shell-extension-openafs.git
cd gnome-shell-extension-openafs
```

### 2️⃣ Create Extension Directory

GNOME extensions should be placed in a specific folder:

```bash
mkdir -p ~/.local/share/gnome-shell/extensions/gnome-shell-extension-openafs
cp * ~/.local/share/gnome-shell/extensions/gnome-shell-extension-openafs/
```


### 3️⃣ Restart GNOME Shell

- **X11 session**: Press `Alt + F2`, type `r`, and press Enter.(Recommended)
- **Wayland session**: Log out and log back in.

### 4️⃣ Enable the Extension

Use GNOME Extensions App (GUI) or terminal:

```bash
gnome-extensions enable gnome-shell-extension-openafs
```

### 5️⃣ Test the Extension

Click the **top bar icon** labeled “OpenAFS Status”.

Then from the terminal, toggle the client status:

```bash
sudo systemctl stop openafs-client
# → Click extension icon → Should show "Client: Not Running"

sudo systemctl start openafs-client
# → Click extension icon → Should show "Client: Running"
```

---

## 🧑‍💻 GSoC 2025 Info

- **Project**: GNOME Shell Extension for OpenAFS
- **Mentors**: Mike Meffie
- **Student**: [Tejas Sonawane](https://github.com/ts-31)
- **Organization**: [OpenAFS](https://www.openafs.org/)
- **Program**: [Google Summer of Code 2025](https://summerofcode.withgoogle.com/)

---

## 🤝 Contributing

This extension is in active development as part of GSoC 2025. Contributions, suggestions, and feedback are welcome via [issues](https://github.com/YOUR_USERNAME/gnome-shell-extension-openafs/issues) and pull requests once the base is complete.

---

### 🙌 Special Thanks

To the OpenAFS team and GNOME community for building incredible open infrastructure for decades.

---

> _"Bridging CLI power with GUI ease for OpenAFS users."_ — GSoC 2025 Student Developer


## 📸 Screenshots

### 🖼️ GNOME Top Bar Menu Preview

![Top bar UI](assets/screenshot.png)
