# Cybersecurity Testing Lab Environment Setup

This repository documents the Phase 1 setup for an isolated cybersecurity testing laboratory using VirtualBox and Kali Linux.

## Phase 1: Essential Lab Setup

### Step 1: Tooling Installation
* **Archiving Utility:** Installed 7-Zip from `7-zip.org` for secure extraction of compressed virtual machine images.
* **Virtualization Software:** Installed Oracle VM VirtualBox from `virtualbox.org`.

---

### Step 2: Network Segmentation & Configuration
To ensure an isolated and controlled testing environment, a dedicated NAT Network was implemented with custom subnet properties:

* **Network Type:** NAT Network
* **Network Name:** `NatNetwork`
* **Network Subnet:** `10.0.0.0/24`

---

### Step 3: Kali Linux Virtual Machine Deployment
* **Image Import:** Downloaded the pre-configured Kali Linux Virtual Machine (VM) from `kali.org` and imported it into VirtualBox.
* **Network Interface Configuration:**
  * **Attached To:** NAT Network (`NatNetwork`)
  * **IP Assignment:** Static
  * **IP Address:** `10.0.0.2/24`
  * **Default Gateway:** `10.0.0.1`
  * **Primary DNS:** `8.8.8.8`
* **Interoperability & Integration:**
  * **Shared Clipboard:** Bidirectional / Enabled
  * **Drag and Drop:** Bidirectional / Enabled
  * **Shared Folders:** Linked host path `/downloads` to guest OS for secure file transfers.

---

### Step 4: System State Preservation
* **Base Snapshot Created:** Generated a clean state snapshot immediately following configuration. This allows quick rollback to a known-good clean state during security testing activities.
