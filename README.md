# Rust Installation Guide for Windows (Without C++ Build Tools)

This guide will walk you through installing Rust on Windows using MSYS2 and the GNU toolchain. Follow the steps below to get started.

## Prerequisites

1. **Download Rust Installer**: Get the Rust installation executable from [Rust's official website](https://www.rust-lang.org/tools/install).
2. **Download MSYS2**: Download the MSYS2 installer from [MSYS2's official website](https://www.msys2.org/).

## Installation Steps

### Step 1: Install MSYS2

1. Run the MSYS2 installer and follow the on-screen instructions to complete the installation.
2. Open the MSYS2 shell (you can find it in the Start Menu).

### Step 2: Update the MSYS2 System

1. In the MSYS2 shell, run the following command to update the system:
   ```sh
   pacman -Syu
   ```

### Step 3: Install the MinGW Toolchain

1. In the MSYS2 shell, install the MinGW toolchain by running:
   ```sh
   pacman -S mingw-w64-x86_64-toolchain
   ```

### Step 4: Install Base Development Tools

1. Install the base development tools by running:
   ```sh
   pacman -S base-devel
   ```

### Step 5: Install Rust

1. Close the MSYS2 shell and open the Rust installation executable.
2. During the installation process:
   - Choose "Customize installation."
   - Select "Manually configure the installation."
   - Set the target to `x86_64-pc-windows-gnu`.

3. Proceed with the installation by following the prompts.

### Step 6: Post-Installation

1. Navigate to the `.cargo` folder in your user directory.
2.Once you're in the .cargo folder, create a new file named .config. Then, open it with your preferred text editor.
3.Once the file is open, paste the lines i provide into it.

```
[target.x86_64-pc-windows-gnu]
linker="C:\\msys2\\mingw64\\bin\\gcc.exe"
ar=C:\\msys2\\mingw64\\bin\\ar.exe

```
### Step 7: Test 
After that, you'll want to test the configuration by creating a .rust file (you can name it anything you like), and write some Rust code in it.

Once you've written your Rust code, compile it by running rustc <filename>.rust in your command prompt or terminal. If there are no errors, you can run the compiled executable by typing ./<filename>.


