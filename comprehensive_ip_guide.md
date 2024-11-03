
# Comprehensive Guide to the `ip` Command in Linux

The `ip` command in Linux is used to manage network interfaces, routing tables, and network configurations. It is a powerful replacement for older networking tools like `ifconfig` and `route`.

## Table of Contents
1. [Basic Syntax](#basic-syntax)
2. [Viewing IP Address Information](#viewing-ip-address-information)
3. [Configuring IP Addresses](#configuring-ip-addresses)
4. [Managing Network Interfaces](#managing-network-interfaces)
5. [Viewing and Modifying Routing Tables](#viewing-and-modifying-routing-tables)
6. [Displaying Network Statistics](#displaying-network-statistics)
7. [Practical Use Cases](#practical-use-cases)

---

## 1. Basic Syntax

The basic syntax of the `ip` command is:
```bash
ip [options] object [command]
```
- **options**: Additional flags or settings, such as `-4` (IPv4) or `-6` (IPv6).
- **object**: Specifies the type of network object, such as `address`, `link`, or `route`.
- **command**: The action to perform, such as `show`, `add`, or `del`.

## 2. Viewing IP Address Information

To display IP addresses assigned to all interfaces, use the `address` object with the `show` command.

- **Example**: Show IP addresses for all interfaces:
  ```bash
  ip address show
  ```

- **IPv4 Only**: Use `-4` to display only IPv4 addresses:
  ```bash
  ip -4 address show
  ```

- **IPv6 Only**: Use `-6` to display only IPv6 addresses:
  ```bash
  ip -6 address show
  ```

## 3. Configuring IP Addresses

To assign or remove IP addresses for network interfaces, use the `add` or `del` commands.

- **Example**: Assign an IP address to an interface:
  ```bash
  sudo ip address add 192.168.1.10/24 dev eth0
  ```

- **Example**: Remove an IP address from an interface:
  ```bash
  sudo ip address del 192.168.1.10/24 dev eth0
  ```

## 4. Managing Network Interfaces

The `link` object manages network interfaces, allowing actions like enabling or disabling an interface.

- **Example**: Display information about all network interfaces:
  ```bash
  ip link show
  ```

- **Example**: Enable an interface (`eth0`):
  ```bash
  sudo ip link set eth0 up
  ```

- **Example**: Disable an interface (`eth0`):
  ```bash
  sudo ip link set eth0 down
  ```

## 5. Viewing and Modifying Routing Tables

To view and manage routes, use the `route` object.

- **Example**: Display the current routing table:
  ```bash
  ip route show
  ```

- **Example**: Add a new route to reach the `10.0.0.0/24` network via gateway `192.168.1.1`:
  ```bash
  sudo ip route add 10.0.0.0/24 via 192.168.1.1 dev eth0
  ```

- **Example**: Delete a route:
  ```bash
  sudo ip route del 10.0.0.0/24
  ```

## 6. Displaying Network Statistics

The `-s` option with `ip link` displays network statistics for each interface.

- **Example**: Show interface statistics:
  ```bash
  ip -s link show
  ```

## 7. Practical Use Cases

- **Network Configuration**: Set up and manage IP addresses and routes for local network interfaces.
- **Troubleshooting**: Diagnose network issues by viewing IP assignments, interface status, and routing tables.
- **Network Monitoring**: Display network statistics and status information for monitoring traffic.

---

The `ip` command is a comprehensive tool for managing networking on Linux. By using objects like `address`, `link`, and `route`, along with commands for adding, deleting, or displaying information, `ip` enables powerful control over network settings.

For more information, use the `man ip` command or consult online resources for further details.
