# snd-hda-codec-cs8409

A Linux kernel audio driver for the Cirrus Logic CS8409 HDA bridge chip, providing support for various Apple devices such as the iMac 27" 5K and MacBook Pro.

This repository includes modernization patches to ensure compatibility with **Linux Kernel 6.17** and later.

## Features
- Audio playback and capture support for CS8409.
- Dynamic jack detection (headphones vs. speakers).
- Modernized HDA operations and API usage for Kernel 6.17+.
- Cleaned up compiler warnings for a strict build environment.

## Installation

### Prerequisites
Make sure you have the Linux kernel headers and build essentials installed for your current kernel:

```bash
sudo apt-get update
sudo apt-get install build-essential linux-headers-$(uname -r)
```

### Build and Install

1. **Clone the repository:**
   ```bash
   git clone https://github.com/yourusername/snd-hda-codec-cs8409.git
   cd snd-hda-codec-cs8409
   ```

2. **Build the module:**
   ```bash
   make
   ```

3. **Install the module:**
   ```bash
   sudo make install
   ```

4. **Load the module:**
   ```bash
   sudo modprobe snd-hda-codec-cs8409
   ```
   *Note: You may need to reboot your system for the changes to take full effect and for the audio server to properly recognize the new hardware routing.*

## Verification
You can verify that the driver has loaded correctly by checking the kernel ring buffer:
```bash
dmesg | grep cs8409
```
You should see output indicating successful initialization and node configuration.

## Acknowledgments
A huge thank you to the original authors and contributors who made this driver possible:
- **Alexander Egorenkov** for the initial driver implementation and CS8409 TAS5764L support.
- The open-source community members (including milan475) who helped reverse-engineer and test the hardware quirks for Apple devices.

## License
This project is licensed under the GPL-2.0-or-later license, in accordance with the Linux Kernel module standards.