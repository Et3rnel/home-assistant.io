---
title: "Securing"
description: "Instructions on how to secure your Home Assistant installation."
---

One major advantage of Home Assistant is that it is not dependent on cloud services. Even if you're using Home Assistant only on a local network, securing your instance is paramount.

## Checklist

Here's a summary of what you *must* do to secure your Home Assistant system:

- **Use the `secrets.yaml` File**: Centralize sensitive data in `secrets.yaml` to prevent accidental exposure. This file should be excluded from version control and shared data. Ensure both the main configuration and secrets files are backed up regularly.
  
  - **Note**: Storing secrets in `secrets.yaml` does not encrypt them. Consider encrypting your entire file system or at least the directory where your configuration is located if you require an added layer of security.

- **Keep Systems Up-to-Date**: Regularly update Home Assistant and all related components to ensure you benefit from the latest security patches and improvements.

## Remote Access

If you seek secure remote access, the easiest option is [Home Assistant cloud](/cloud/), which also supports the [founders of Home Assistant](https://www.nabucasa.com/about/).

Another option is TLS/SSL through the add-on [Duck DNS](/integrations/duckdns/) integrating Let's Encrypt.

When exposing your instance to the internet, employ a [VPN](https://pivpn.io) or an [SSH tunnel](/blog/2017/11/02/secure-shell-tunnel/). Make sure to expose the used port in your router.

### Extras for Manual Installations

To further enhance security, consider the following recommendations:

- **SSH Security**:
  - Set `PermitRootLogin no` in your SSH configuration (typically `/etc/ssh/sshd_config`).
  - Use SSH keys for authentication over passwords, especially if enabling remote access to your SSH services.

- **Host Security**:
  - Follow best practices for securing the host system. Some recommended guides include:
    - [Securing Debian Manual](https://www.debian.org/doc/manuals/securing-debian-manual/index.en.html) (also relevant for Raspberry Pi OS)
    - [Red Hat Enterprise Linux 7 Security Guide](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/7/html/security_guide/index), [CIS Red Hat Enterprise Linux 7 Benchmark](https://www.cisecurity.org/cis-benchmarks/)

---

This updated documentation integrates the previous discussion and structures it to provide clear guidance for securing a Home Assistant installation.
