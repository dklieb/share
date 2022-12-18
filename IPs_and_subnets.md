# IP addresses and subnets

[What is an IP address?](#understanding-ip-addresses-and-subnets)

[Internal IP addresses](#internal-ip-addresses)

[External IP addresses](#external-ip-addresses)

[What is a subnet?](#what-is-a-subnet)

[Putting it all together](#putting-it-all-together)

[Limitations](#limitations)

## What is an IP address?

An IP address is a unique numerical identifier assigned to a device for connecting to an internal network or over the internet. This address lets other devices know how to find it, similar to how a telephone number works. Examples of devices include servers, routers, personal computers, tablets, IoT devices, and printers. For a device to use an IP address it must have a means of communicating, using either an Ethernet connection or a wireless connection.

A device’s IP address can typically be found in the network settings, or from the command line in your computer's operating system.

From the MacOS or Linux Terminal app, use the command:

```/sbin/ifconfig```

From the Windows Command Prompt shell, use the command:

```ipconfig```

The output will display various networking properties for the computer, including the assigned IP address. For example:

```192.168.0.1```

An IP address contains four sets of integers, each separated by a decimal. This sequence of numbers represents a 32 bit number in total, with each of the four sections containing 8 bits or octets. The integer representation of an IP address is easier to read, however when communicating over networks and the internet, addresses are communicated in binary using 1’s and 0’s. 

Consider the 192.168.0.1 address that can be represented in either the integer or binary format:

| Format  | Octet 1  | Octet 2  | Octet 3  | Octet 4  |
| ------- | -------- | -------- | -------- | -------- |
| Integer | 192      | 168      | 0        | 1        |
| Binary  | 11000000 | 10101000 | 00000000 | 00000001 |

In addition to the IP address being a unique identifier for the device, it also contains information about the network ID and the host ID. A network ID is the subnet that the device belongs to, and the host ID is an identifier for the device itself. 

The following table shows how to identify the network ID and then host ID based on the 192.168.0.1 address example:

| Network ID | Network ID | Network ID | Host ID |
| ---------- | ---------- | ---------- | ------- |
| 192        | 168        | 0          | 1       |

The networking ID and hosting ID information for an IP address will vary based on the subnet mask that is assigned to the device. For more information about subnets, see the section [What is a subnet?](#what-is-a-subnet) below.

## Internal IP addresses

An internal IP is a private address assigned to a device inside of a local area network (LAN). Addresses are usually assigned automatically by a dynamic host control protocol (DHCP) server on the network, but they can also be configured manually. Using a DHCP server is typically the preferred method because it is easier to set up, prevents users from configuring an incorrect address on their devices, and eliminates the possibility of two devices using the same address. Any of these scenarios will prevent devices from connecting to the network.

There are three ranges of IP addresses that are used for assigning internal addresses:

- 10.0.0.0 - 10.255.255.255
- 172.0.0.0 - 172.255.255.255
- 192.168.0.0 - 192.168.255.255

Devices such as personal computers can have multiple internal IP addresses for communicating across different subnets on a network.

## External IP addresses

External IP addresses are assigned to devices connected directly to the internet. Typically, devices such as corporate servers are assigned an external static IP address, meaning the address never changes. IP addresses for home internet connections are usually assigned by the ISP's DHCP server, and can change.

Servers and other supported devices can be assigned multiple external IP addresses. For example, a company may have a security policy that allows it to host a web server and an email server on the same physical server but they must maintain these services on separate IPs addresses.

Some devices including routers are configured with both internal and external IP addresses. This allows for communication with both the internal LAN and the internet simultaneously, while acting as a gateway for LAN devices to communicate with the internet.


## What is a subnet?

When a device is assigned an IP address, it is also assigned a subnet mask. A subnet mask identifies the range of allowable IP addresses on a network segment. This range is also referred to as a subnet.

As with an IP address, the subnet mask that is assigned to a device can be found in the network settings, or from the command line in your computer operating system.

From the MacOS and Linux Terminal app, use the command:

```/sbin/ifconfig```

From the Windows Command Prompt shell, use the command:

```ipconfig```

The output will display various networking properties for the computer, including the assigned subnet mask. For example:

```255.255.255.0```

A subnet mask contains four sets of integers, each separated by a decimal. This sequence of numbers also represents a 32 bit number in total, with each of the four sections containing 8 bits or octets.


| Format  | Octet  1 | Octet  2 | Octet  3 | Octet 4  |
| ------- | -------- | -------- | -------- | -------- |
| Integer | 255      | 255      | 255      | 0        |
| Binary  | 11111111 | 11111111 | 11111111 | 00000000 |

There are three main subnet class types. These classes allow a network administrator to define the size of a network segment by configuring a subnet mask and prefix. A subnet prefix is a short form representation of the subnet mask.

| Class | First octet range | Subnet Mask   | Subnet prefix | Number of hosts |
| ----- | ----------------- | ------------- | ------------- | --------------- |
| A     | 1-126             | 255.0.0.0     | /8            | 16,777,214      |
| B     | 128-191           | 255.255.0.0   | /16           | 65,534          |
| C     | 192-223           | 255.255.255.0 | /24           | 256             |


## Putting it all together

Using the information and examples above, we can now determine the following:

- The IP address for the device is ```192.168.0.1```.
- The subnet mask for the device is ```255.255.255.0```.
- The combination of the IP address and subnet mask can be represented with the subnet prefix as ```192.168.0.1 /24```.
- The subnet is a class C type and can accommodate up to 245 IP addresses.

## Limitations

- The 0 or 255 numbers in the last octet of an IP address range cannot be assigned to devices because they are reserved.
- The 127.0.0.0-127.255.255.255 range cannot be used for assigning IP addresses because it is reserved for local host traffic only.
- Class D and class E subnets exist but they cannot be used for assigning IP addresses because these classes are reserved.
