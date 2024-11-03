
# Comprehensive Guide to the `resolvectl` Command in Linux

The `resolvectl` command, part of `systemd-resolved`, is used to manage and query DNS settings on Linux systems. It provides detailed information about DNS configuration, status, and can resolve domain names, IP addresses, and other network-related queries.

## Table of Contents
1. [Basic Syntax](#basic-syntax)
2. [Checking DNS Configuration](#checking-dns-configuration)
3. [Resolving Domain Names and IPs](#resolving-domain-names-and-ips)
4. [Viewing Link (Network Interface) Information](#viewing-link-network-interface-information)
5. [Flushing DNS Cache](#flushing-dns-cache)
6. [Setting DNS Servers](#setting-dns-servers)
7. [Practical Use Cases](#practical-use-cases)

---

## 1. Basic Syntax

The basic syntax of `resolvectl` is:
```bash
resolvectl [command] [options]
```
- **command**: The specific action to perform, such as `status`, `query`, or `flush-caches`.
- **options**: Additional parameters or arguments related to the command.

## 2. Checking DNS Configuration

To check the current DNS configuration, use the `status` command.

- **Example**: View DNS configuration status:
  ```bash
  resolvectl status
  ```
  This command provides detailed information about DNS servers, search domains, and network interfaces.

## 3. Resolving Domain Names and IPs

The `query` command allows you to resolve domain names to IP addresses or vice versa.

- **Example**: Resolve a domain name to an IP address:
  ```bash
  resolvectl query example.com
  ```

- **Reverse Lookup**: Resolve an IP address to a domain name:
  ```bash
  resolvectl query 93.184.216.34
  ```

## 4. Viewing Link (Network Interface) Information

To view DNS information for a specific network interface, use `resolvectl` with the link ID or interface name.

- **Example**: View DNS details for `eth0`:
  ```bash
  resolvectl status eth0
  ```

## 5. Flushing DNS Cache

Use the `flush-caches` command to clear the DNS cache, which can help resolve issues with stale or incorrect DNS entries.

- **Example**: Flush the DNS cache:
  ```bash
  resolvectl flush-caches
  ```

## 6. Setting DNS Servers

`resolvectl` can also set DNS servers for a specific network interface.

- **Example**: Set a custom DNS server (e.g., Google DNS) for the `eth0` interface:
  ```bash
  resolvectl dns eth0 8.8.8.8 8.8.4.4
  ```

- **Search Domains**: To set search domains for the interface:
  ```bash
  resolvectl domain eth0 example.com
  ```

## 7. Practical Use Cases

- **DNS Troubleshooting**: Diagnose DNS issues by querying domains and inspecting interface settings.
- **Network Configuration**: Set custom DNS servers for specific network interfaces.
- **Cache Management**: Flush DNS cache to resolve issues with outdated DNS entries.
- **Reverse Lookup**: Identify domain names from IP addresses.

---

The `resolvectl` command provides comprehensive DNS management and querying capabilities for `systemd`-based Linux systems. With options for viewing, setting, and clearing DNS data, it’s a valuable tool for network administration and troubleshooting.

For more details, refer to the `man resolvectl` page or consult systemd-resolved documentation for additional examples and options.
