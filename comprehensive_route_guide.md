
# Comprehensive Guide to the `route` Command in Linux

The `route` command is a network utility used to display and manipulate the IP routing table on Linux systems. It allows administrators to add, delete, or view routing information, making it useful for configuring network paths and gateways.

## Table of Contents
1. [Basic Syntax](#basic-syntax)
2. [Displaying the Routing Table](#displaying-the-routing-table)
3. [Adding Routes](#adding-routes)
4. [Deleting Routes](#deleting-routes)
5. [Setting Default Gateways](#setting-default-gateways)
6. [Making Routes Persistent](#making-routes-persistent)
7. [Practical Use Cases](#practical-use-cases)

---

## 1. Basic Syntax

The basic syntax of the `route` command is:
```bash
route [options] [command] [target] [gateway] [options]
```
- **command**: Specifies the action, such as `add`, `del`, or `show`.
- **target**: The destination network or host for the route.
- **gateway**: The gateway address used to reach the target.

> **Note**: The `route` command is deprecated on some systems in favor of `ip route`. However, it is still available in many distributions.

## 2. Displaying the Routing Table

To view the current routing table, run `route` without additional commands.

- **Example**: Display the routing table:
  ```bash
  route
  ```

## 3. Adding Routes

Use the `add` command to create a new route.

- **Example**: Add a route to the `192.168.2.0/24` network via the gateway `192.168.1.1`:
  ```bash
  sudo route add -net 192.168.2.0/24 gw 192.168.1.1
  ```

- **Example**: Add a route to a specific host (e.g., `10.0.0.5`):
  ```bash
  sudo route add -host 10.0.0.5 gw 192.168.1.1
  ```

## 4. Deleting Routes

To delete a route, use the `del` command.

- **Example**: Delete a network route to `192.168.2.0/24`:
  ```bash
  sudo route del -net 192.168.2.0/24 gw 192.168.1.1
  ```

- **Example**: Delete a route to a specific host:
  ```bash
  sudo route del -host 10.0.0.5
  ```

## 5. Setting Default Gateways

The default gateway is used to route packets to destinations outside the local network.

- **Example**: Set the default gateway to `192.168.1.1`:
  ```bash
  sudo route add default gw 192.168.1.1
  ```

## 6. Making Routes Persistent

Routes added using `route` are not persistent across reboots unless specified in network configuration files.

- On Debian/Ubuntu, add routes in `/etc/network/interfaces`.
- On RHEL/CentOS, add routes in `/etc/sysconfig/network-scripts/route-<interface>`.

For systems using `systemd`, consider using `ip route` with network configuration files for persistent routing.

## 7. Practical Use Cases

- **Network Configuration**: Set static routes to specific networks or hosts.
- **VPN Configuration**: Route traffic for specific IP ranges over a VPN gateway.
- **Custom Gateway Setup**: Define non-default gateways for specific destinations.
- **Troubleshooting**: Display routing tables to diagnose network issues.

---

The `route` command is useful for managing and inspecting routing tables on Linux. With options to add, delete, and set default gateways, it provides flexibility for network configuration.

For more information, use `man route` or consider using `ip route` as a modern replacement.
