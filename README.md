# Set up OpenVPN for Remote Access

## Introduction

In this guide, we'll embark on the journey of setting up OpenVPN for remote access, simplifying the process to ensure seamless connectivity. Utilizing Duck DNS for free dynamic DNS hosted on AWS adds flexibility to our network configuration.

<img width="452" alt="open-vpn-before-sign-on" src="https://github.com/rasheedjimoh/openvpn/assets/157264080/d73c7e34-d5d8-463e-8431-a049bb9948bf">


## Getting Started with Duck DNS

Begin by creating an account on Duck DNS and generate a subdomain pointed at your current public IP address.

![duckdns](https://github.com/rasheedjimoh/openvpn/assets/157264080/cc83670b-1dd3-4b0c-a696-121ca6ef961f)


## Configuring Dynamic DNS on pfSense

Access the pfSense web configurator, navigate to Services, and click on Dynamic DNS. Select Custom as the Service Type. Paste the URL provided by Duck DNS, including the subdomain and token, into the Update URL box. Ensure the result match is set to OK.

**Setting Up OpenVPN Server:**

Head to VPN and select OpenVPN. Choose Local User Access as the Type of Server. Create a new certificate authority, such as RJEnterprise OpenVPN CA. Enable "Force all client-generated traffic through the tunnel" in Redirect IPv4 Gateway options. Specify the LAN IP address accessible over the VPN and allow remote access to LAN and DMZ.

**Configuring Firewall and OpenVPN Rules:**

Add Firewall and OpenVPN rules to permit connections from anywhere and all traffic through the VPN.

**Managing VPN Users:**

Navigate to User Manager and create VPN users to grant access to the network.

**Installing OpenVPN Client Export Package:**

In the Package Manager, search for openvpn-client-export and install it. Download the client version compatible with your operating system and install it on the client device.

<img width="305" alt="openvpn-connected" src="https://github.com/rasheedjimoh/openvpn/assets/157264080/40368de3-d56d-4624-97ae-94ed3549177e">


## Connecting and Verification

Log in with the username and password created earlier and connect to verify the setup. Confirm connectivity by pinging inbound. Check the status to ensure that inbound and outbound traffic are increasing, indicating a successful connection.

<img width="416" alt="openvpn-status-connected" src="https://github.com/rasheedjimoh/openvpn/assets/157264080/8b7e28fb-f632-4e77-b738-120956bf8d48">


With these simplified steps, you'll establish secure remote access using OpenVPN, enhancing your network's capabilities effortlessly.

<img width="343" alt="able to ping inbound" src="https://github.com/rasheedjimoh/openvpn/assets/157264080/ccaee10f-aab6-4e41-8898-4a1df809dff9">
