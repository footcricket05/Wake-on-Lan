# Wake-on-Lan

![Wake-on-LAN](https://github.com/footcricket05/Wake-on-Lan/raw/main/Images/wol_image.png)

## Overview

Wake-on-LAN (WoL) is a powerful networking standard that allows you to remotely power on a PC over the Internet using the Wake-On-LAN protocol. This technology enables you to wake up a computer from a powered-down or sleep state, making it an invaluable tool for IT professionals, home network enthusiasts, and anyone looking to save time and energy.

## Table of Contents

- [Principle of Operation](#principle-of-operation)
- [Magic Packet Structure](#magic-packet-structure)
- [Limitations](#limitations)
- [Getting Started](#getting-started)
- [Contributing](#contributing)
- [License](#license)

## Principle of Operation

Wake-on-LAN operates by sending a specially crafted network message known as a "magic packet" to the target computer. The magic packet is designed to awaken the target computer from a low-power state, such as being powered down. Here's how it works:

1. **Magic Packet**: The magic packet contains the MAC address of the target computer. This MAC address is a unique identifier for the network interface card (NIC) or Ethernet device in the target computer.

2. **Low-Power Mode**: Computers capable of Wake-on-LAN maintain network devices that can "listen" for incoming packets even when the system is powered down. This low-power mode allows the computer to respond to the magic packet.

3. **Wake-Up Signal**: When the NIC of the target computer receives a magic packet addressed to its MAC address, it signals the computer's power supply or motherboard to initiate system wake-up, similar to pressing the power button.

4. **Broadcast**: The magic packet is sent on the data link layer and is broadcast to all devices on the local network using the network broadcast address. It does not rely on IP addresses.

Wake-on-LAN reduces power consumption in powered-down computers, as it only requires the network interface to stay on in low-power mode. Disabling Wake-on-LAN when not needed can further reduce standby power consumption.

## Magic Packet Structure

The magic packet is a broadcast frame that contains 6 bytes of all 255 (FF FF FF FF FF FF in hexadecimal), followed by sixteen repetitions of the target computer's 48-bit MAC address, resulting in a total of 102 bytes. It can be sent using various network and transport-layer protocols, often as a UDP datagram to port 0, 7, or 9, or directly over Ethernet as EtherType 0x0842.

### Limitations

Wake-on-LAN has some limitations that are important to consider:

1. **Requires Destination MAC Address**: You need the MAC address of the destination computer to send a magic packet. In some cases, a SecureOn password may also be required.

2. **No Delivery Confirmation**: Wake-on-LAN does not provide delivery confirmation, so you won't know if the target computer successfully woke up.

3. **Local Network Dependence**: It may not work outside of the local network unless you have set up appropriate network configurations like subnet directed broadcasts or a Wake-on-LAN gateway service.

4. **Hardware Support**: Wake-on-LAN requires hardware support on the destination computer, so not all computers can be woken up using this method.

5. **Wireless Interface Compatibility**: Most 802.11 wireless interfaces do not maintain a link in low-power states, making them unable to receive a magic packet.

## Getting Started

To use Wake-on-LAN, you can refer to the [documentation](/docs) and follow the steps provided to set up and configure this technology on your network. Make sure your target computer and network equipment support Wake-on-LAN.

## Contributing

We welcome contributions to this project. If you'd like to get involved, please see our [contribution guidelines](CONTRIBUTING.md) for more information.

## License

This project is licensed under the [MIT License](LICENSE). Feel free to use and distribute it as needed.

For more information, visit our [GitHub repository](https://github.com/footcricket05/Wake-on-Lan).

![Wake-on-LAN](https://github.com/footcricket05/Wake-on-Lan/raw/main/Images/wol_image.png)
