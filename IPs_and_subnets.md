## What is an IP address?

An IP address is a unique identifier assigned to a device for connecting to an internal network or over the internet. This address lets other devices know how to find it, similar to how a telephone number works. Examples of devices include servers, routers, personal computers, tablets, and printers. The two common protocols used for assigning IP addresses are IPv4 and IPv6.

A device’s IP address can typically be found in its network settings, or from the command line in your operating system.

In MacOS and Linux Terminal app, use the command:

```/sbin/ifconfig```

In the Windows Command Prompt shell, use the command:

```ipconfig```

An IP address is a sequence of integers divided into four sections, separated by decimals. This represents 32 bits in total with four sections containing 8 bits or octet segments. The integer representation of an IP address is easier to read, however when communicating over networks and the internet, addresses are sent in binary using 1’s and 0’s. For example, consider the IP address 192.168.0.1.

| Format | Octet |Octet |Octet |Octet |
| ----------- | ----------- | ----------- | ----------- | ----------- | 
| Integer version | 192 | 168 | 0 | 1 | 
| Binary version | 11000000 |10101000 |00000000 |00000001 |

An IP address also contains information about the network ID and the host ID. The network ID is the subnet that the host belongs to, and the host ID is the host itself. For more information about subnets, see the section What is a subnet? below.

The following table shows how to identify the host ID and network ID:
| Network ID | Network ID | Network ID |Host ID |
| ----------- | ----------- | ----------- | ----------- |
| 192 | 168 | 0 | 1 | 

## Internal and external IP addresses

An internal IP is a private address assigned to a device inside of a local area network (LAN). Addresses on a LAN are usually assigned automatically by a dynamic host control protocol (DHCP) server on the network.

There are three ranges of IP addresses that are typically used for assigning internal addresses:

- 10.0.0.0 - 10.255.255.255
- 172.0.0.0 - 172.255.255.255
- 192.168.0.0 - 192.168.255.255

External IPs are assigned to devices connected directly to the internet. Typically, corporate servers are assigned a static IP address and always remain the same. Home internet connections are usually assigned dynamic external IP addresses that can change. 

Devices such as routers are configured with both internal and external IP addresses. This allows communication on both the internal LAN and over the internet simultaneously, and act as a gateway for LAN devices to access the internet.

## What is a subnet?

A subnet is used for defining the range of allowable IP addresses on a network segment, and is used for both internal and external IP addresses. As with IP addresses, subnets contain four set integers, separated by decimals. 

For example, consider the subnet 255.255.255.0 represented in both integers and binary.

| Format | Octet |Octet |Octet |Octet |
| ----------- | ----------- | ----------- | ----------- | ----------- | 
| Integer version | 255 | 255 | 255 | 0 | 
| Binary version | 11111111 |11111111 |11111111 |00000000 |

There are three main subnet class types. These classes allow a network administrator to define the size of a network segment by configuring a subnet mask and prefix.

| Class | First octet range |Subnet Mask |Subnet prefix |Number of hosts |
| ----------- | ----------- | ----------- | ----------- | ----------- |
| A | 1-126 | 255.0.0.0 | /8 | 16,777,214 |
| B | 128-191 | 255.255.0.0 | /16 | 65,534|
| C | 192-223 | 255.255.255.0 | /24 | 256|

Using the above examples, we can now determine the following:

- The IP for the device is 192.168.0.1
- The subnet mask for the device is 255.255.255.0
- The combination of IP and subnet mask can be represented as 192.168.0.1 /24
- The subnet can have up to 254 devices because it is a class C type subnet

## Additional considerations 
- Class D and class E subnets exist but they are not used for IP addresses and subnetting because they are often reserved for multicasting and experimentation on the network.
- The 127.0.0.0-127.255.255.255 cannot be used for assigning IP addresses on a network because the range is reserved for local host traffic only.
- The 0 or 255 numbers in the last octet cannot be assigned to devices because they are reserved for broadcasting, and experimentation.
