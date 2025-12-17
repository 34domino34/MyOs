# MyOs

**MyOs** is a from-scratch x86 operating system written in **16-bit / 32-bit assembly and C**, focused on low-level boot mechanics, extreme fault handling, and experimental graphics.

This project is currently in **Pre-Alpha** and is under heavy development. Expect breakage, undefined behavior, and intentional system abuse.

---

## ⚠️ Project Status

**Pre-Alpha**
- No stability guarantees
- Frequent breaking changes
- Not intended for daily use
- Intended for learning, experimentation, and pushing hardware limits

If it crashes, panics, or reboots your machine — that’s expected.

---

## ✨ Features

- Custom multi-stage bootloader
- BIOS + x86 real-mode / unreal-mode experimentation
- Watchdog timers and failure detection
- Advanced panic handlers and recovery logic
- Experimental graphics / framebuffer abuse
- Designed to run close to bare metal with minimal abstraction

---

## 🛠 Requirements

- x86-compatible CPU
- NASM
- C compiler (OpenWatcom / GCC depending on build stage)
- QEMU (recommended)
- OR real hardware (⚠️ at your own risk)

---

## 🚀 Running MyOs

### ▶️ Option 1: Run in QEMU (Recommended)

QEMU is the safest way to test MyOs.

#### Example (raw disk image):
qemu-system-i386 -drive format=raw,file=myos.img
▶️ Option 2: Boot from USB (Real Hardware)

⚠️ WARNING
Running MyOs on real hardware can:

Overwrite disks

Crash the system

Hard reset the machine

Corrupt data

Only use a spare USB. Never your main drive.

Steps:

Build or obtain the raw disk image (e.g. myos.img)

Identify your USB device:

lsblk


Write the image:

sudo dd if=myos.img of=/dev/sdX bs=1M status=progress
sync


Replace /dev/sdX with the correct device.

Boot from USB via BIOS/UEFI (Legacy/CSM mode)

▶️ Option 3: Install to HDD (NOT Recommended)

Only do this on test machines or virtual disks.

sudo dd if=myos.img of=/dev/sdX bs=1M status=progress
sync


This will overwrite the disk completely.

📜 License & Copyright

Copyright © 2025 Dominic Hopkins

All rights reserved.

This project is protected under copyright law.
Unauthorized copying, redistribution, or claiming this work as your own is prohibited.

A formal license may be added later as the project matures.

❗ Disclaimer

MyOs directly interacts with hardware at a low level.
You assume all risk when running it.

If your system crashes, reboots, or behaves strangely — that’s on you.
