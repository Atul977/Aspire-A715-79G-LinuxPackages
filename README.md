🧩 Tuxedo Hardware Control for Acer & Clevo Laptops (Arch Linux)

> [!CAUTION]
> **ARCH LINUX ONLY:** This repository provides prebuilt `.pkg.tar.zst` binaries specifically for Arch Linux. These packages will **NOT** work on Ubuntu, Fedora, Debian, or any non-Arch distribution.

This project hosts a custom Arch Linux binary repository that enables control over:
* 🎨 **RGB Keyboard Backlighting**
* 🌬️ **Fan Speed Curves**
* ⚡ **Power & Performance Profiles**

---

### 💻 Supported Devices
Specifically optimized and patched for:
* **Acer Aspire A715-79G Series**
* **Acer ALG Series**
* Any laptop using **Clevo internal hardware** that requires `tuxedo-drivers`.

**🧪 Tested Build Environment:**
* **CPU:** Intel Core i5-13420H
* **GPU:** NVIDIA RTX 3050 (6GB)
* **OS:** Arch Linux

---

### 📦 Included Packages
| Package | Description |
| :--- | :--- |
| `tuxedo-drivers-dkms` | 🔧 Patched DKMS kernel drivers for Acer compatibility. |
| `tailord` | ⚙️ Native Rust-based hardware control daemon. |
| `tailor-gui` | 🖥️ Modern GTK4 GUI for fan & RGB control. |

---

### 🚀 Installation

#### 1. Add the Custom Repository
Edit your `pacman.conf` file:

```bash
sudo nano /etc/pacman.conf
```

Add the following lines at the very end of the file:

```bash
[tuxedo-repo]
SigLevel = Optional TrustAll
Server = https://raw.githubusercontent.com/atul977/Aspire-A715-79G-LinuxPackages/gh-pages/
```

2. Install the Packages

Sync your package databases and install the drivers and GUI:

```bash
sudo pacman -Syy
sudo pacman -S tuxedo-drivers-dkms tailord tailor-gui
```

3. Enable the Hardware Daemon

Start and enable the service so it runs automatically on boot:

```bash
sudo systemctl enable --now tailord.service
```

🔄 Automated Updates

This repository is maintained using a Smart Build System powered by GitHub Actions:

    🕛 Upstream Monitoring: Checks the official upstream repositories every midnight.

    🧠 Conditional Builds: Packages are rebuilt only when new commits or updates are detected.

    🩹 Automatic Patching: Required patch.diff files for Acer hardware compatibility are automatically applied during each build.


🛑 Disclaimer

    This project is not affiliated with TUXEDO Computers or Acer.

    Use at your own risk — kernel drivers modify low-level hardware behavior.

    Intended only for Clevo-based laptops running Arch Linux.
