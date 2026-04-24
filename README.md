# SOC Analyst Lab

This repository documents my hands-on journey into Security Operations Center (SOC) roles. It includes environment setup, network analysis, and incident response simulations.

---

## Project 1: Environment Provisioning & Troubleshooting
**Goal:** Build a stable Kali Linux 2025.4 environment on VMware for security testing.

### The Challenge: The "Invisible Cursor" Bug
Upon first boot, the mouse cursor was functional but invisible within the Kali desktop environment. This made navigation nearly impossible and stalled the lab setup.

### The Solution
I performed the following troubleshooting steps to resolve the graphical conflict:
1. **Hardware Upgrade:** Updated the VM Hardware Compatibility to **Workstation 17.x** to support modern Linux kernel display drivers.
2. **Graphics Tweak:** Disabled **3D Acceleration** in VMware settings to resolve conflicts between the host GPU and the guest OS.
3. **Software Configuration:** Used the terminal (`sudo apt`) to install `open-vm-tools-desktop` to ensure better integration between Windows and Kali.

### Verification
I verified the stability of the environment by installing and running `fastfetch` to benchmark system resources.

<img width="359" height="359" alt="Showing Cursor(fastfetch)" src="https://github.com/user-attachments/assets/0d1e4e3c-dc92-4166-ad55-a45fee6be0b3" />
<img width="590" height="533" alt="Accelerate 3D graphucs" src="https://github.com/user-attachments/assets/6ff50c9d-22a7-4ae8-8e24-fdd09c240f96" />
