This Standard Operating Procedure (SOP) outlines the process for installing **CentOS Stream 9** on a VMware virtual machine.

**1. Prerequisites**

- **Virtualization Software:** VMware Workstation Pro/Player installed.
- **CentOS ISO:** Download the **x86_64 ISO** from the official [CentOS Download page](https://www.centos.org/download/).
- **Minimum Resources:** 2 vCPUs, 2 GB RAM (4 GB recommended), and 20 GB free disk space. [[1](https://www.centos.org/download/), [2](https://www.youtube.com/watch?v=77Rf3KvlqAc&t=1), [3](https://www.youtube.com/watch?v=oyAojEzVK-4&t=164), [4](https://www.youtube.com/watch?v=b6uNbpxZV-8&t=1), [5](https://www.youtube.com/watch?v=F0q-NFOi5ws), [6](https://www.progressiverobot.com/2026/04/21/how-to-set-up-a-centos-stream-9-template-in-vmware/), [7](https://community.broadcom.com/vmware-cloud-foundation/discussion/trying-to-install-centos-stream-9-freezes)]

**2. Virtual Machine Creation** []

1. Open VMware and select **Create a New Virtual Machine**.
2. Choose the **Typical (recommended)** configuration.
3. Select **I will install the operating system later** to ensure full control over the interactive installation.
4. Set the Guest OS to **Linux** and version to **Red Hat Enterprise Linux 9 64-bit** (CentOS Stream 9 is built from RHEL 9).
5. Name the VM (e.g., `CentOS-Stream-9`) and specify a storage location.
6. Set the **Maximum disk size** to at least **20 GB**; selecting **Store virtual disk as a single file** can improve performance.
7. Click **Customize Hardware** to set RAM to **2 GB+** and Processors to **2**. [, [2](https://www.scribd.com/document/903571536/Linux-CentOS-Installation), [5](https://community.broadcom.com/vmware-cloud-foundation/discussion/trying-to-install-centos-stream-9-freezes), [6](https://www.youtube.com/watch?v=Ip0RCEkRyXU&t=1)]

**3. Installation Process**

1. **Mount ISO:** In VM Settings, go to **CD/DVD (SATA)**, select **Use ISO image file**, and browse to your downloaded CentOS ISO. Ensure **Connect at power on** is checked.
2. **Power On:** Start the VM and select **Install CentOS Stream 9** from the boot menu.
3. **Language:** Choose your preferred language (e.g., English) and click **Continue**.
4. **Installation Summary:**
    - **Installation Destination:** Select the virtual disk and click **Done** (Automatic partitioning is standard for basic setups).
    - **Software Selection:** Choose **Server with GUI** for a desktop experience or **Minimal Install** for a lightweight server.
    - **Network & Hostname:** Ensure the Ethernet adapter is **ON** and set a hostname.
    - **Root Password:** Set a secure password for the root account.
    - **User Creation:** Create a standard user and check **Make this user administrator** if needed.
5. Click **Begin Installation**. Once complete, click **Reboot System**. [[1](https://www.youtube.com/watch?v=Ip0RCEkRyXU&t=1), [3](https://techdocs.broadcom.com/us/en/vmware-cis/vsphere/guest-operating-system-installation-guide/1-0/linux-operating-systems/centos/centos-stream.html), [5](https://kitemetric.com/blogs/mastering-centos-stream-9-installation-a-comprehensive-guide), [6](https://thiago-marsal.medium.com/how-to-install-linux-centos-stream-9-using-virtualbox-46d603c40a32)]

**4. Post-Installation & Optimization**

- **Eject ISO:** If the VM boots back into the installer, shut it down and disconnect the ISO from the CD/DVD settings.
- **Install VMware Tools:** Run `sudo dnf install open-vm-tools` (or `open-vm-tools-desktop` for GUI) to enable better screen resolution and clipboard sharing.
- **Update System:** Immediately run `sudo dnf update -y` to apply the latest security patches. [[1](https://www.youtube.com/watch?v=PoGHCpRrYB4&t=5), [2](https://www.youtube.com/watch?v=Ip0RCEkRyXU&t=1), [3](https://www.progressiverobot.com/2026/04/21/how-to-set-up-centos-stream-9-with-kvm-virtualization/)]