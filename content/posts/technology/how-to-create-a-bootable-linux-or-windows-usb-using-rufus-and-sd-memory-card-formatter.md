---
title: "How to Create a Bootable Linux or Windows USB Using Rufus and SD Memory Card Formatter"
date: 2024-02-03
lastmod: 2025-06-24
draft: false
description: "Learn step-by-step how to create a bootable USB for Linux or Windows using Rufus and SD Memory Card Formatter. Simple guide for beginners to install OS from USB drive."
categories: ["Technology"]
tags: ["bootable usb", "create bootable drive", "install windows from usb", "linux usb", "make linux usb", "rufus guide", "rufus tutorial", "sd formatter", "windows usb"]
author: "Jonayed Hossan Gazi"
showToc: true
---

#### **Introduction**

Want to install Linux or Windows using a USB drive? The easiest and fastest way is to make your USB bootable. In this guide, we’ll walk you through creating a bootable USB stick using **Rufus** and **SD Memory Card Formatter** — two simple tools that work great together on Windows.

Whether you’re upgrading an old PC or trying Linux for the first time, this tutorial is all you need.

* * *

### **What You’ll Need**

  * A **USB Flash Drive** (at least 8GB recommended)

  * A **Windows PC**

  * **Rufus** (Free USB boot utility)

  * **SD Memory Card Formatter** (Free formatting tool from SD Association)

  * A Linux or Windows **ISO file** (you can download these from the official OS websites)




* * *

### **Why Use SD Memory Card Formatter?**

Sometimes USB drives get corrupted, show wrong capacity, or fail to boot. SD Memory Card Formatter **resets the drive properly** and fixes low-level formatting issues that Windows’ built-in formatter can’t. It’s perfect for preparing your USB before using Rufus.

* * *

## 🧰 Step-by-Step Guide

* * *

### ✅ **Step 1: Download Required Tools**

  * **Rufus:**  
<https://rufus.ie/>  
Download the portable or installer version.

  * **SD Memory Card Formatter:**  
https://www.sdcard.org/downloads/formatter/  
Install the version for Windows.

  * **Your OS ISO File:**

    * **Windows ISO:** <https://www.microsoft.com/software-download/windows10>

    * **Linux ISO:** [Ubuntu](https://ubuntu.com/download), Debian, etc.




* * *

### ✅ **Step 2: Format USB Drive with SD Memory Card Formatter**

  1. Insert your USB flash drive into your PC.

  2. Open **SD Memory Card Formatter**.

  3. Make sure your USB is selected in the “Drive” dropdown.

  4. Keep formatting options as default:

     * Format Type: **Quick**

     * Format Size Adjustment: **On**

  5. Click **Format** , confirm the warning, and wait.




✔️ This step ensures your USB is clean and ready.

* * *

### ✅ **Step 3: Create Bootable USB with Rufus**

  1. Open **Rufus** (no install needed if using portable).

  2. Select your USB drive under **Device**.

  3. Under **Boot selection** , click **SELECT** and choose your ISO file.

  4. Partition scheme:

     * Use **MBR** for BIOS or older PCs.

     * Use **GPT** for UEFI systems (newer computers).

  5. File system:

     * **FAT32** (works for Linux and most use cases)

     * **NTFS** (only if the ISO is larger than 4GB or for Windows)

  6. Volume Label: You can name it something like “UbuntuUSB” or “Win10Boot”.

  7. Click **START**.

  8. If prompted to download additional files or choose writing method, go with defaults (e.g., ISO mode for Windows).




🕒 Wait for it to finish (usually 2-10 minutes depending on USB speed).

* * *

### ✅ **Step 4: Boot from the USB Drive**

Once the bootable USB is ready:

  1. Insert it into the target PC.

  2. Reboot the system.

  3. Press the BIOS/boot key (usually **F12** , **F2** , **Del** , or **Esc**) when starting the PC.

  4. Select the USB from the boot menu.

  5. Start your installation process.




* * *

### ⚠️ **Tips and Troubleshooting**

  * **USB Not Detected?**  
Try formatting it again using SD Formatter and redoing the Rufus steps.

  * **ISO Corrupt?**  
Make sure your ISO is downloaded completely and verified with checksum if possible.

  * **“No bootable device found”?**  
Double-check the partition scheme and try switching between MBR/GPT.




* * *

### 🔚 **Conclusion**

Creating a bootable USB drive is essential for reinstalling or testing operating systems. With **SD Memory Card Formatter** and **Rufus** , the process becomes reliable and beginner-friendly.

Now you can install **Linux** , **Windows** , or any OS from your USB — fast, free, and clean.