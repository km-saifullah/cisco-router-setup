# IP Addressing

An **Internet Protocol (IP)** address is the unique identifying number assigned to every device connected to the internet. An IP address definition is a numeric label assigned to devices that use the internet to communicate. Computers that communicate over the internet or via local networks share information to a specific location using IP addresses. [ [Fortinet](https://www.fortinet.com/resources/cyberglossary/what-is-ip-address) ]

## Types of IP Address

1. IPv4 (IP Version 4)
2. IPv6 (IP Version 6)

## Example of IP Address

Decimal Representation: **192.168.0.1**

Binary Conversion
| 2<sup>7</sup> | 2<sup>6</sup> | 2<sup>5</sup> | 2<sup>4</sup> | 2<sup>3</sup> | 2<sup>2</sup> | 2<sup>1</sup> | 2<sup>0</sup> | Series |
| ------------- | ------------- | ------------- | ------------- | ------------- | ------------- | ------------- | ------------- | ------------- |
| 128 | 64 | 32 | 16 | 8 | 4 | 2 | 1 | Decimal Value |
1 | 1 | 0 | 0 | 0 | 0 | 0 | 0 | 192 (128+64)
1 | 0 | 1 | 0 | 1 | 0 | 0 | 0 | 168 (128+32+16)
0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0
0 | 0 | 0 | 0 | 0 | 0 | 0 | 1 | 1

| 1<sup>st</sup> Octet | 2<sup>nd</sup> Octet | 3<sup>rd</sup> Octet | 4<sup>th</sup> Octet |
| -------------------- | -------------------- | -------------------- | -------------------- |
| 11000000             | 10101000             | 00000000             | 00000001             |

Total Bits: **32**

Number of Octet: **4** (Each octet has 8 bits)

Each Octet Minimum Decimal Value: **0 (00000000)**

Each Octet Maximum Decimal Value: **255 (11111111)**

Each Octet will be Separated by dot(.)

## Classes of IP Address

1. Class-A ⇒ (0.0.0.0 - 127.255.255.255)
2. Class-B ⇒ (128.0.0.0 - 191.255.255.255)
3. Class-C ⇒ (192.0.0.0 - 223.255.255.255)
4. Class-D ⇒ (224.0.0.0 - 239.255.255.255)
5. Class-E ⇒ (240.0.0.0 - 255.255.255.255)

> We cannot assign Class-D and Class-E address to any devices. Because these two classes will use in different purposes. Class-D is reserved for the multicast networking purpose. On the other hand Class-E will be used for experimental or future use purpose.

> The IP address range 127.0.0.0 – 127.255.255.255 is reserved for loopback. Loopback IP address is managed entirely by and within the operating system. These addresses enable the Server and Client processes on a single system to communicate with each other. When a process creates a packet with destination address as loopback address, the operating system loops it back to itself without having any interference of NIC. Here NIC means Network Interface Address.

## Network and Host Bits

| Class | Network Bits | Host Bits | **1st Bits in 1st Octet** | Network (N) and Host(H) Octets | Subnet Mask   |
| ----- | ------------ | --------- | ------------------------- | ------------------------------ | ------------- |
| A     | 8            | 24        | 0XXX                      | N.H.H.H                        | 255.0.0.0     |
| B     | 16           | 16        | 10XX                      | N.N.H.H                        | 255.255.0.0   |
| C     | 24           | 8         | 110X                      | N.N.N.H                        | 255.255.255.0 |
| D     | N/A          | N/A       | 111X                      | N/A                            | N/A           |
| E     | N/A          | N/A       | 1111                      | N/A                            | N/A           |

## Network address (NA)

All the network bits will remain unchanged, all the host bit will be zero.

Example: 192.168.0.45

Decimal: 192.168.0.45 ⇒ Class-C Address

Network Bits: 24

Host Bits: 8

Binary: 11000000 . 10101000 . 00000000 . 00101101

Network Address(NA): 11000000 . 10101000 . 00000000 . 00000000 ⇒ 192.168.0.0

## Broadcast Address (BA)

All the network bit will remain unchanged, all the host bit will be one.

Example: 192.168.0.45

Binary: 11000000 . 10101000 . 00000000 . 11111111 ⇒ 192.168.0.255

## Subnet Mask (SM)

All the network bit will be one, all the host bit will be zero.

Example: 192.168.0.45

Binary: 11111111 . 11111111 . 11111111 . 00000000 ⇒ 255.255.255.0

## Example of NA, BA, SM, First Host, Last Host

Example: **175.210.195.60**

**Class**: Class-B Address

**Network Bits**: 16

**Host Bits**: 16

**Number of Host:** (**2^16**) = **65536**

**Number of Usable Host:** (**2^16**) - **2** = **65536-2 = 65534**

**Binary**: 10101111 . 11010010 . 11000011 . 00111100 ⇒ 175.210.195.60

**NA**: 10101111 . 11010010 . 00000000 . 00000000 ⇒ 175.210.0.0

**BA**: 10101111 . 11010010 . 11111111 . 11111111 ⇒ 175.210.255.255

**SM**: 11111111 . 11111111 . 00000000 . 00000000 ⇒ 255.255.0.0

**FH**: 10101111 . 11010010 . 00000000 . 00000001 ⇒ 175.210.0.1

**LH**: 10101111 . 11010010 . 11111111 . 11111110 ⇒ 175.210.255.254

## Private IP Address

A private IP address is the address space allocated to NIC to allow organizations to create their own private network. The computers, tablets and Smartphone sitting behind your home, and the personal computers within an organizations are usually assigned private IP addresses. A network printer residing in your home or office is assigned a private address so that only your local users can print to your local printer. Private IP addresses are non routable and non saleable.

| Class | Range                         | Available Hosts |
| ----- | ----------------------------- | --------------- |
| A     | 10.0.0.0-10.255.255.255       | 1,67,77,216     |
| B     | 172.16.0.0 - 172.31.255.255   | 1048576         |
| C     | 192.168.0.0 - 192.168.255.255 | 65536           |
