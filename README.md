# Debian 12 Bookworm Server Installation – Step-by-Step

**Description:**  
A complete step-by-step guide for installing and configuring a Debian 12 Bookworm server. This repository includes installation instructions, best practices and essential configurations to help you set up a secure, stable, and optimized Debian 12 server environment.

---

## 📘 Introduction
This guide provides a detailed walkthrough of installing **Debian 12 Bookworm Server**.  
It covers the entire installation procedure, system configuration, disk partitioning, user setup, and post-installation server preparation.

Whether you're installing a home server or preparing a production environment, this documentation ensures a clean, secure, and optimized Debian installation.

---

## 📑 Table of Contents

- [Introduction](#-introduction)
- [Full Step-by-Step Installation Process](#-full-step-by-step-installation-process)
  - [1. Choose Installation Method](#1-choose-installation-method)
  - [2. Select Language](#2-select-language)
  - [3. Select Location (Country)](#3-select-location-country)
  - [4. Configure Locales](#4-configure-locales)
  - [5. Configure Keyboard](#5-configure-keyboard)
  - [6. Configure Hostname](#6-configure-hostname)
  - [7. Configure Domain Name](#7-configure-domain-name)
  - [8. Set Up a Root Password](#8-set-up-a-root-password)
  - [9. Create a User Account](#9-create-a-user-account)
  - [10. Select Username](#10-select-username)
  - [11. Set User Password](#11-set-user-password)
  - [12. Partition Disks](#12-partition-disks)
  - [13. Install the Base System](#13-install-the-base-system)
  - [14. Configure the Package Manager](#14-configure-the-package-manager)
  - [15. Configure a Network Mirror](#15-configure-a-network-mirror)
  - [16. Configure an HTTP Proxy](#16-configure-an-http-proxy)
  - [17. Participate in Survey](#17-participate-in-survey)
  - [18. Software Selection](#18-software-selection)
  - [19. Install GRUB](#19-install-grub)
  - [20. Finish Installation](#20-finish-installation)
- [Post-Installation Configuration](#-post-installation-configuration)
  - [21. Connect to the Server After Reboot](#21-connect-to-the-server-after-reboot)
  - [22. Modify the APT Sources List](#22-modify-the-apt-sources-list)
  - [23. Update and Upgrade](#23-update-and-upgrade)
  - [24. Install sudo command](#24-install-sudo-command)
  - [25. Add your user to sudo group](#25-add-your-user-to-sudo-group)
- [Summary](#-summary)

---

## 🧩 Full Step-by-Step Installation Process

### **1. Choose Installation Method**
Select one of the Debian installer options:
- **Graphical Install** (recommended for beginners)  
- **Command-Line Install** (for advanced users)

![Choose Installation mMethod](images/choose_installation_method.png)

---

### **2. Select Language**
Choose the main language that Debian will use during installation.

![Select Language](images/select_language.png)

---

### **3. Select Location (Country)**
Pick your geographical location.  
Example in this guide: **Cameroon**

![Select Location](images/select_location.png)

---

### **4. Configure Locales**
Select the locale to define the language and regional settings.

![Configure Locales](images/configures_locales.png)

---

### **5. Configure Keyboard**
Choose the correct keyboard layout (e.g., English (US), French, etc.).

![Configure Keyboard](images/configure_keyboard.png)

---

### **6. Configure Hostname**
Enter a hostname for the machine (example: `horner`).

![Configure Hostname](images/configure_hostname.png)

---

### **7. Configure Domain Name**
If you do not have a domain name, **leave this field empty**.

![Configure Domain Name](images/configure_domain_name.png)

---

### **8. Set Up a Root Password**
Set a strong password for the root account.  
This password gives full administrative access.

![Set Up a Root Password](images/setup_root_password.png)

---

### **9. Create a User Account**
Enter the full name of the new regular user.

![Create User Account](images/create_user_account.png)

---

### **10. Select Username**
Choose the username associated with the user account.

![Select Username](images/select_username.png)

---

### **11. Set User Password**
Create a secure password for this user.

![Set User Password](images/setup_an_user_password.png)

---

### **12. Partition Disks**
Select your preferred partitioning option:
For beginners, **Guided – use entire disk** is recommended.

![Partition Diks](images/partition_disks_1.png)

![Partition Diks](images/partition_disks_2.png)

![Partition Diks](images/partition_disks_3.png)

![Partition Diks](images/partition_disks_4.png)

![Partition Diks](images/partition_disks_5.png)

---

### **13. Install the Base System**
The installer automatically sets up the minimal Debian system.

![Install Base System](images/install_the_base_system.png)

---

### **14. Configure the Package Manager**
Select default options unless specific network settings are required.

![Configure Package Manager](images/configure_package_manager.png)

---

### **15. Configure a Network Mirror**
Choose a Debian mirror near your region for faster downloads.

![Network Mirror](images/network_mirror_1.png)

![Network Mirror](images/network_mirror_2.png)

![Network Mirror](images/network_mirror_3.png)

---

### **16. Configure an HTTP Proxy**
Skip this step unless your network requires a proxy.

![HTTP Proxy](images/HTTP_Proxy.png)

![Configure Package Manager](images/package_manager_loading.png)

---

### **17. Participate in Survey**
Choose **No** when asked to participate in the popularity contest.

![Participate in  Survey](images/participate_survey.png)

---

### **18. Software Selection**
Select only:
- **Web Server**
- **SSH Server**
- **Standard system utilities**

Do **not** install a GUI for a clean server setup.

![Software Selection](images/software_selection.png)

---

### **19. Install GRUB**
Install GRUB on the main hard drive (usually `/dev/sda` or `/dev/nvme0n1`).

![Install Grub](images/install_grub_1.png)

![Install Grub](images/install_grub_2.png)

---

### **20. Finish Installation**
Complete the installation and reboot the system.

![Finish Installation](images/finish_installation.png)

---

## 🔐 Post-Installation Configuration

### **21. Connect to the Server After Reboot**
Log in using your newly created user account.

![Server Start](images/server_started.png)

![Connect to Server](images/connexion_to_server_1.png)

![Connect to Server](images/connexion_to_server_2.png)

---

### **22. Modify the APT Sources List**
Switch to root:

```sh
su -
```

Open the file:
```sh
nano /etc/apt/sources.list
```
![Modify APT sources list](images/access_sources_list.png)

Replace its content with the following:

```sh
# Debian 12 Bookworm Main Repositories
deb http://deb.debian.org/debian bookworm main non-free-firmware
deb-src http://deb.debian.org/debian bookworm main non-free-firmware

# Debian 12 Bookworm Security Updates
deb http://security.debian.org/debian-security bookworm-security main non-free-firmware
deb-src http://security.debian.org/debian-security bookworm-security main non-free-firmware

# Debian 12 Bookworm Updates
deb http://deb.debian.org/debian bookworm-updates main non-free-firmware
deb-src http://deb.debian.org/debian bookworm-updates main non-free-firmware
```

![Modify APT sources list](images/apt_source_list.png)

---

### **23. Update and Upgrade**
Run:
```sh
apt update
```
```sh
apt upgrade -y
```

![Update and Upgrade](images/update_upgrade.png)

---

### **24. Install sudo command**
```sh
apt install sudo -y
```

![install sudo](images/install_sudo.png)

---

### **25. Add your user to sudo group**
```sh
sudo usermod -aG sudo <username>
```
My username is taptue. 

![Add user to sudo group](images/add_user_sudo_group.png)

Log out and log back in to apply the changes.

![Disconnect and Reconnect](images/disconnect_and_reconnect.png)

![Sudo Test](images/sudo_test.png)

---

# ✔ Summary

This repository includes:  
- Step-by-step Debian 12 Bookworm server installation  
- Disk partitioning and base system setup  
- User account creation and root/sudo configuration  
- APT sources list modification and package updates  
- Software selection and GRUB installation  
- Post-installation configuration instructions  
- Screenshots for every installation step