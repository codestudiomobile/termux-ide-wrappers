# CodeStudio Termux IDE Wrappers

Intelligent multi-language execution wrappers and compilation abstractions configured for CodeStudio Mobile IDE. These components translate standard low-level compiler outputs into lightweight runtimes, automating file validation and housekeeping.

## 📦 What's Inside?
* **`ccr.sh` (C/C++ Compile & Run)**: Detects compiler invocations, builds files with Clang/Clang++ directly within secure application directories, executes compiled assets safely, and deletes the transient binary footprint post-execution.
* **`cscr.sh` (C# Compile & Run)**: Direct code routing engine utilizing `mcs` (Mono C# Compiler) to compile asset code layers, invoke execution frameworks smoothly, and clear localized `.exe` build footprint remnants cleanly.

---

## 🚀 Quick Setup & Installation

Import the development compiler tools directly into your running environment folder paths:

### 1. Install CodeStudio C/C++ Wrappers
```bash
curl -fsSL [https://raw.githubusercontent.com/codestudiomobile/termux-ide-wrappers/main/ccr.sh](https://raw.githubusercontent.com/codestudiomobile/termux-ide-wrappers/main/ccr.sh) -o $PREFIX/bin/ccr
chmod +x $PREFIX/bin/ccr

```

### 2. Install CodeStudio C# Wrappers

```bash
curl -fsSL [https://raw.githubusercontent.com/codestudiomobile/termux-ide-wrappers/main/cscr.sh](https://raw.githubusercontent.com/codestudiomobile/termux-ide-wrappers/main/cscr.sh) -o $PREFIX/bin/cscr
chmod +x $PREFIX/bin/cscr

```

### 3. Register Shell Execution Hooks

To bind these script routines seamlessly with standard shortcut aliases, make sure your `$PREFIX/etc/bash.bashrc` file includes these bindings:

```bash
alias csmide-compile='ccr'
alias ccr-gcc='ccr -mode gcc'
alias ccr-gpp='ccr -mode g++'
alias cscr-mono='cscr'

```

---

## 💡 How to Use

### 🛠️ Working with C / C++ Source Projects

You can invoke the smart automation wrapper using standard flags or fallback modes. The workspace processes target assets natively, handles user prompts, and drops binary builds when finished to conserve storage:

```bash
# Standard automatic invocation (uses system clock for temporary binary tag)
ccr main.cpp

# Specific compilation output invocation
ccr main.cpp -o custom_build

```

### ⚡ Working with C# Source Projects

Process raw configuration scripts or logic trees built via C# directly through standard target execution setups:

```bash
cscr Program.cs

```

```
