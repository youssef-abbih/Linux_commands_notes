
# Comprehensive Guide to the `df` Command in Linux

The `df` (disk filesystem) command in Linux is used to display information about filesystem disk space usage. It provides insights into total, used, and available disk space for each mounted filesystem, making it useful for system monitoring and capacity planning.

## Table of Contents
1. [Basic Syntax](#basic-syntax)
2. [Understanding the Output](#understanding-the-output)
3. [Common Options](#common-options)
4. [Practical Use Cases](#practical-use-cases)

---

## 1. Basic Syntax

The basic syntax of `df` is:
```bash
df [options] [file...]
```
- **options**: Flags to customize the output format or behavior.
- **file**: Optional, specifies a particular filesystem or directory to check.

> If no file or directory is specified, `df` displays usage information for all mounted filesystems.

## 2. Understanding the Output

When you execute `df`, the output includes several columns:
```
Filesystem     1K-blocks     Used Available Use% Mounted on
/dev/sda1       10240000  5120000   5120000  50% /
tmpfs            1024000        0   1024000   0% /dev/shm
```

- **Filesystem**: The name of the filesystem or device.
- **1K-blocks**: Total size of the filesystem (in 1K blocks by default).
- **Used**: Space used on the filesystem.
- **Available**: Space available on the filesystem.
- **Use%**: Percentage of space used on the filesystem.
- **Mounted on**: The directory where the filesystem is mounted.

## 3. Common Options

- **-h**: Display output in human-readable format (e.g., MB, GB).
  ```bash
  df -h
  ```
- **-T**: Show the filesystem type along with disk usage.
  ```bash
  df -T
  ```
- **-i**: Display inode usage instead of block usage.
  ```bash
  df -i
  ```
- **-x [type]**: Exclude filesystems of a specific type (e.g., tmpfs).
  ```bash
  df -x tmpfs
  ```
- **--total**: Display a total line summarizing disk usage across all filesystems.
  ```bash
  df --total
  ```

## 4. Practical Use Cases

- **Monitor Disk Space**: Use `df -h` to check available space and ensure filesystems do not reach capacity.
- **Filesystem Type Verification**: Use `df -T` to verify filesystem types, especially on multi-filesystem setups.
- **Inode Usage Monitoring**: Check inode usage with `df -i` to monitor systems with a high volume of small files.
- **Exclude Temporary Filesystems**: Exclude specific filesystem types (e.g., tmpfs) from the output to focus on relevant storage.

---

The `df` command is a valuable tool for monitoring disk space on Linux systems. By using options to customize the display format and focus on specific filesystems, `df` helps users and administrators manage disk usage effectively.

For further details, refer to `man df` or online resources for advanced usage examples.
