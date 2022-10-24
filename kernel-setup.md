# COP4610 - Project 2 Guide - Part 7 - Kernel Setup

## Authors

Brian Poblete

## Notes

- This guide was written in October 2022 with Ubuntu 22.04 Server edition in
mind
- It is definitely possible to use another distro and another version.
- But I would recommend using this same version for maximum compatibility.

## Modifying the Kernel

- Previously ~~on Avatar~~, we dynamically inserted the kernel modules into the
running kernel.
- Now, we need to add new system calls
  - System calls are a part of the kernel itself.
  - Adding new system calls requires re-compiling the entire kernel.

## Kernel Versions

- Your machine should be running kernel version `5.15` or newer.
  - If not, I recommend updating your current kernel version to the latest
    supported version for your distro.
- Verify your kernel version using the command `uname -r`
- We will be downloading the latest version of kernel 5.15 available
on [kernel.org](https://kernel.org/).
- We will also modify and install this kernel version.
- When there are two kernels on a machine, it will (typically) automatically
boot into the latest version.

## Download

- [5.15.74 is the latest version of 5.15 available as of October 23, 2022.](
https://cdn.kernel.org/pub/linux/kernel/v5.x/linux-5.15.74.tar.xz)

- You can visit this link in your browser or download it through the terminal
using something like `wget` or `curl`.

- Extract the tar.xz file
  - `tar xf /path/to/tar -C /usr/src`
  - -C tells tar where to extract the files

## Make your life a bit easier

- Because the kernel is outside of your $HOME directory, you will need sudo
access to do stuff with it (e.g., editing, saving, running, etc.).
- If you don't want to work in /usr/src, you can set up a symlink inside your
home directory to the kernel source directory
  - `ln -s /usr/src/linux-5.17.74 ~/test_kernel`
- If you don't want to set up a symlink but also don't want to have to prepend
sudo to every command you use, you can also give the user permission to access
the kernel folder.
  - `sudo chown user:user -R /usr/src/linux-5.15.74`

## By now you should have

- Checked your Linux kernel version.
- Downloaded the source code for kernel version 5.15.74 (or whatever is latest).
- Extracted the tar.xz file into the direcotry `/usr/src/`.
- (Optional) Set up a symlink ***OR***
- (Optional) Give the user ownership of kernel folder.
