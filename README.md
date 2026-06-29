# NTBKRNL: Monolithic 64-Bit UEFI Kernel

NTBKRNL (New Technology Boot Kernel) is a minimalist, native 64-bit operating system kernel developed for x86_64 hardware platforms running on modern UEFI environments. 

Following a strict **Header-Only** design architecture, the project eliminates compilation bloat and external linkage overhead. This allows the system to initialize directly through the firmware's Long Mode execution environment with zero legacy dependencies.

## 🚀 Key Technical Features

* **High-Density Implementation:** Integrates a VESA VBE Linear Framebuffer graphics driver, physical E820 RAM memory mapping, a basic task manager, and a hardware-level diagnostic error screen into a single lightweight codebase.
* **Cache Alignment Optimization:** All core execution structures match the CPU's 64-byte L1/L2 cache lines. By enforcing `static inline` execution layouts, the kernel reduces call stack overhead and controls stack fragmentation.
* **Direct I/O Hardware Interaction:** Bypasses traditional OS abstraction layers. The system implements a direct peripheral communication model: it can handle hardware events asynchronously via an `INTK` (Interrupt Kernel) entry point, or perform raw read/write operations directly on the hardware buses with minimal latency.
* **Linear Ramdisk Processing:** Rejects complex archive headers like ZIP that require scanning backward for central directories. NTBKRNL utilizes flat, linear memory data mapping for fast, predictable sequential file indexing.

## ⚖️ License
See NTBPL... 
This project is licensed under the **NTB Public License (NTBPL)**. You are free to copy, modify, distribute, or commercialize this software.RE, ITS USE, OR ANY INAPPROPRIATE OPERATIONS PERFORMED WITH THE CODE.
