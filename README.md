<div align="center">

```
 ██████╗ ██╗   ██╗ ██████╗ ██╗   ██╗ █████╗ ██████╗ ██╗   ██╗██████╗ 
██╔══██╗╚██╗ ██╔╝██╔════╝ ██║   ██║██╔══██╗██╔══██╗██║   ██║╚════██╗
██████╔╝ ╚████╔╝ ██║  ███╗██║   ██║███████║██████╔╝██║   ██║ █████╔╝
██╔═══╝   ╚██╔╝  ██║   ██║██║   ██║██╔══██║██╔══██╗╚██╗ ██╔╝ ╚═══██╗
██║        ██║   ╚██████╔╝╚██████╔╝██║  ██║██║  ██║ ╚████╔╝ ██████╔╝
╚═╝        ╚═╝    ╚═════╝  ╚═════╝ ╚═╝  ╚═╝╚═╝  ╚═╝  ╚═══╝  ╚═════╝ 
```

### 🛡️ Advanced Python Code Protection Tool

*Obfuscation + Bytecode Encryption — Built for Termux & Linux*

---

[![Python](https://img.shields.io/badge/Python-3.8%2B-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![Platform](https://img.shields.io/badge/Platform-Termux%20%7C%20Linux-black?style=for-the-badge&logo=android&logoColor=white)](https://termux.dev/)
[![License](https://img.shields.io/badge/License-MIT-cyan?style=for-the-badge)](LICENSE)
[![Version](https://img.shields.io/badge/Version-2.0.0-brightgreen?style=for-the-badge)](https://github.com/RindaMdz/PyGuardV2/releases)
[![Status](https://img.shields.io/badge/Status-Active-success?style=for-the-badge)]()
[![Dev](https://img.shields.io/badge/Dev-RindaMdz-blue?style=for-the-badge&logo=github)](https://github.com/RindaMdz)

</div>

---

## 📖 About PyGuardV2

**PyGuardV2** is a Python-based CLI tool designed to protect your `.py` scripts from unauthorized reading and reverse engineering. By combining **advanced obfuscation** and **bytecode encryption** (marshal + zlib + base85), PyGuardV2 transforms your source code into an encrypted payload that still executes perfectly — without altering any functionality.

Built specifically to run smoothly on **Termux (Android)** as well as other Linux environments, featuring a clean, animated, and user-friendly CLI interface.

---

## ✨ Features

| Feature | Description |
|---------|-------------|
| 🔐 **Bytecode Encryption** | Source compiled to bytecode → marshal → zlib (level 9) → base85 |
| 🎭 **Payload Obfuscation** | Payload embedded in a self-contained loader, unreadable to humans |
| ✅ **Auto Verification** | Output is syntax-verified before saving, guaranteed error-free |
| 🎨 **Stylish CLI UI** | ASCII art banner, spinner, progress bar, and typing effect in cyan theme |
| 📱 **Termux Ready** | No compilation needed — only Python standard library + colorama |
| ⚡ **Minimal Dependencies** | Relies primarily on Python built-in libraries (`zlib`, `base64`, `marshal`, `ast`) |
| 🔄 **Fully Executable Output** | Protected files run exactly the same as the original |

---

## 🛠️ Tech Stack

<div align="center">

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![Termux](https://img.shields.io/badge/Termux-000000?style=flat-square&logo=android&logoColor=white)
![zlib](https://img.shields.io/badge/zlib-Compression-orange?style=flat-square)
![base64](https://img.shields.io/badge/base85-Encoding-purple?style=flat-square)
![marshal](https://img.shields.io/badge/marshal-Bytecode-red?style=flat-square)

</div>

**Libraries used:**
- `zlib` — level 9 compression (Python built-in)
- `base64` — base85 encoding (Python built-in)
- `marshal` — bytecode serialization (Python built-in)
- `ast` — syntax validation (Python built-in)
- `colorama` — terminal colors *(the only external dependency)*

---

## 📦 Installation & Usage on Termux

### Step 1 — Update & Install Python

Open Termux and run:

```bash
pkg update && pkg upgrade -y
pkg install python -y
```

### Step 2 — Install Dependencies

PyGuardV2 only requires one external library:

```bash
pip install colorama
```

### Step 3 — Download PyGuardV2

**Option A — Clone via Git:**
```bash
pkg install git -y
git clone https://github.com/RindaMdz/PyGuardV2.git
cd PyGuardV2
```

**Option B — Manual download:**

Download `PyGuardV2.py` and move it to your working directory in Termux.

### Step 4 — Run PyGuardV2

```bash
python PyGuardV2.py
```

### Step 5 — Follow the Interactive Prompts

PyGuardV2 will guide you step by step:

```
  [1]  Select the file to protect:

  ▶  Input Python file (.py) : myscript.py

  [2]  Choose output filename:

  ▶  Output file name [myscript_protected.py] : 

  Start protection? (y/n)
  y
```

### Step 6 — Run the Protected File

```bash
python myscript_protected.py
```

The file will run **exactly the same** as the original. ✅

---

## 🔬 How It Works

```
Source Code (.py)
       │
       ▼
  [1] Syntax Validation (ast.parse)
       │
       ▼
  [2] Compile to Code Object (compile())
       │
       ▼
  [3] Bytecode Serialization (marshal.dumps)
       │
       ▼
  [4] Compression (zlib.compress, level=9)
       │
       ▼
  [5] Encoding (base64.b85encode)
       │
       ▼
  [6] Embed into Loader
       │
       ▼
  Protected Output (.py)  ──►  Still fully executable!
```

**At runtime**, the loader will:
1. Decode base85 → decompress zlib → unmarshal to code object
2. Execute the code object in the correct module namespace

---

## ⚠️ Important Notes

> **PyGuardV2 is designed to protect your own code.**
> Do not use this tool for any purpose that violates copyright or applicable laws.

- Bytecode-based protection is not full cryptographic encryption — there are inherent limits to its protection
- Protected files require the **same Python version** to execute (bytecode is version-sensitive)
- It is strongly recommended to keep a backup of the original file before protecting it

---

## 📁 Project Structure

```
PyGuardV2/
├── PyGuardV2.py       # Main script
├── README.md          # This documentation
└── LICENSE            # MIT License
```

---

## 📜 License

Distributed under the **MIT License**. See the `LICENSE` file for full details.

---

<div align="center">

Made with ❤️ by **RindaMdz**

[![GitHub](https://img.shields.io/badge/GitHub-RindaMdz-181717?style=for-the-badge&logo=github)](https://github.com/RindaMdz)

*"Protect your work. Own your code."*

</div>
