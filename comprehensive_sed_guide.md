
# Comprehensive Guide to the `sed` Command in Linux

The `sed` command, short for *stream editor*, is a powerful text processing tool in Linux. It allows users to perform complex text manipulations directly from the command line or within shell scripts. This guide covers essential `sed` features with practical examples.

## Table of Contents
1. [Basic Syntax](#basic-syntax)
2. [Printing Lines](#printing-lines)
3. [Addressing Lines and Ranges](#addressing-lines-and-ranges)
4. [Deleting Text](#deleting-text)
5. [Substitution and Replacement](#substitution-and-replacement)
6. [Using Regular Expressions](#using-regular-expressions)
7. [Advanced Commands](#advanced-commands)
8. [Saving Output to a File](#saving-output-to-a-file)
9. [Practical Use Cases](#practical-use-cases)

---

## 1. Basic Syntax

The basic syntax of `sed` is:
```bash
sed [options] 'command' file
```
- **[options]**: Common options include `-n` to suppress automatic printing.
- **command**: The command to apply, such as `p` (print) or `s` (substitute).
- **file**: The file to process.

## 2. Printing Lines

`sed` can print specific lines of a file:
- **Example**: Print line 3 of `file.txt`:
  ```bash
  sed -n '3p' file.txt
  ```
- **Multiple lines**: Print lines 3 to 5:
  ```bash
  sed -n '3,5p' file.txt
  ```

## 3. Addressing Lines and Ranges

### Using Line Numbers
- **Example**: Print the first 5 lines:
  ```bash
  sed -n '1,5p' file.txt
  ```

### Step Intervals
- **Example**: Print every 2nd line, starting from line 1:
  ```bash
  sed -n '1~2p' file.txt
  ```
  > Note: `1~2` is a GNU `sed` extension and may not work on *BSD `sed` versions.

## 4. Deleting Text

Use the `d` command to delete lines:
- **Example**: Delete line 2:
  ```bash
  sed '2d' file.txt
  ```
- **Range**: Delete lines 3 to 5:
  ```bash
  sed '3,5d' file.txt
  ```

## 5. Substitution and Replacement

The `s` command substitutes patterns.
- **Basic Syntax**:
  ```bash
  sed 's/old/new/' file.txt
  ```
- **Global Replacement**: Add `g` to replace all occurrences per line:
  ```bash
  sed 's/old/new/g' file.txt
  ```
- **Example**: Replace "apple" with "orange":
  ```bash
  sed 's/apple/orange/g' file.txt
  ```

## 6. Using Regular Expressions

`sed` supports regular expressions for flexible text matching:
- **Example**: Replace lines starting with "Error":
  ```bash
  sed 's/^Error/Warning/' file.txt
  ```
- **Regex**: Match any word character:
  ```bash
  sed 's/\w+/[REPLACED]/g' file.txt
  ```

## 7. Advanced Commands

### Inserting and Appending Text
- **Insert (`i`)**: Insert text before a line.
  ```bash
  sed '3i\New line above line 3' file.txt
  ```
- **Append (`a`)**: Append text after a line.
  ```bash
  sed '3a\New line below line 3' file.txt
  ```

### Replacing Entire Lines
- Replace line 4 with new text:
  ```bash
  sed '4c\This is the new line 4' file.txt
  ```

## 8. Saving Output to a File

To save `sed` output to a new file, redirect output:
```bash
sed 's/old/new/g' file.txt > output.txt
```
Or, use `-i` (in-place) to modify the file directly:
```bash
sed -i 's/old/new/g' file.txt
```

## 9. Practical Use Cases

- **Quick Text Edits**: Making fast changes in large files.
- **Configuration Management**: Automated configuration changes.
- **Log Management**: Parsing and modifying log files.
- **Data Processing**: Reformatting and cleaning text data.

---

`sed` is a highly versatile tool in text processing, with advanced features like address ranges, regular expressions, and direct file modification, making it invaluable for shell scripting and data manipulation tasks.

For further examples and details, refer to [DigitalOcean's Guide on `sed`](https://www.digitalocean.com/community/tutorials/the-basics-of-using-the-sed-stream-editor-to-manipulate-text-in-linux).
