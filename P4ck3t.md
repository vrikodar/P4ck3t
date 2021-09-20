# P4ck3t

Networking ???   **updated everyday!!**

- [Binary and Decimal Conversions](#binary-and-decimal)

- [Hexadecimal conversions](#hexadecimal)

- [OSI and TCP/IP Modle overview](#osi-model)

- [IP addressing ](#ip-addressing)

     - [Special Addresses](#special-addresses)
     - [Subnet Masks](#subnet-masks)
     - [CIDR {classless interdomain routing}](#cidr)

- [Subnetting](#subnetting)

     - [General](#part1)
     - [with Number of Hosts](#subnetting-a-given-network-when-asked-for-number-of-hosts-required)
     - [with Number of Networks](#subnetting-a-given-network-when-asked-for-number-of-subnets-required)

- [Cisco IOS Software and Device Configuration](#cisco-ios-software-and-device-configuration)

     - [Modes](#modes)
     - [Switching to Different Modes](#some-things-to-remember)
       
       - [User Mode](#user-mode) 
       - [Enable Mode](#enable-mode)
       - [Global Configuration Mode](#global-configuration-mode)
       - [Interface Mode](#interface-mode)
       - [Line Mode](#line-mode)
       - [Router Mode](#router-mode)
       
    - [Managing IOS configuration](#managing-ios-configuration) 
    - [Storing files in Flash](#storing-files-in-flash)
    - [Controlling Amount of Output](#terminal-length)
    - [Solving the Resolve Error](#resolve-error)

- [Lab1 {Basic configuration Lab}](#lab1)
    - [Powering on Cisco Router](#task1)
    - [Configuring IP addresses on Cisco Router](#task2)
    - [Setting an Enable Password](#task3)
    - [Setting up Password Encryption Service](#task4)
    - [Setting up a Secret Password](#task5)
    - [Cracking CISCO IOS hashes](#cracking-the-hash)
    - [Setting up telnet on Cisco Router](#task6)
    - [Setting up a Console Password](#task7)

- [Lab2 {Subnetting Lab1}](#lab2)
     - [Configuring Default Gateway on a Switch](#configuring-the-switch)
   
- [Lab3 {Subnetting Lab2}](#lab3)
     - [Setting up DNS Server on a Router](#configuring-the-wan-link-on-site1)

- [Some Questions](#some-questions)
   
   - [Question 1](#question1)
   - [Question 2](#question2)
   - [Question 3](#question3)

- [Cabling and Packet Flows](#cabling-and-packet-flows)

   - [Types of Communication](#types-of-communication)
   - [Difference Between Broadband and Baseband](#difference-between-baseband-and-broadband)
   - [Mac Addresses](#mac-address)
   - [Color Coding](#utp)
   - [Cable Types Ethernet](#cable-categories)
   - [About Hubs](#hub)
   - [About Bridge](#bridge)
   - [About Switches](#switch)
   - [Speed Duplex Differences](#difference-between-half-duplex-and-full-duplex)
   - [About Routers](#router)
   - [Duplex and Speed Mismatch Error](#speed-duplex-and-speed-mismatch)
     - [Fixing Speed and Duplex mismatch Errors](#fixing-duplex-mismatch-errors) 

- [Lab4 Life of A Packet](#lab4)
- [Lab5 Broadcast and Collision Domains {Hub vs Switch}](#lab5)

- [LoopBack Interface on a Router](#loopback-on-a-router)
- [TCP vs UDP](#tcp-vs-udp) 
     - [TCP Brief](#tcp)
          - [TCP 3-way Handshake](#tcp-3way-handshake)
          - [The TCP Header](#tcp-header)
          - [TCP Flags](#flags)
          - [TCP Windows Size](#window-size)
          - [TCP Checksum](#tcp-checksum)
          - [TCP Urgent Pointer](#urgent-pointer)
          - [Sequence Numbers in TCP communication repersentation](#demo-of-sequence-numbers-etc)
      - [UDP Brief](#udp)
          - [UDP Header](#udp-header)
- [How OSI Model Layers Connect Together!!](#how-layers-connect-together)
- [About Port Numbers](#port-number)
- [DHCP Dynamic Host Control Protocol](#dhcp)
     - [Using a Cisco IOS Network Device as DHCP Server](#configuring-a-cisco-ios-network-device-as-dhcp-server)

- [Lab6 DHCP configuration 1 **Basic**](#lab6)

- [Lab7 DHCP configuration 2 **DHCP Relaying Accross Different Networks!**](#lab7)

- [About VLANs](#vlan)
     - [Physical topology VS Logical Topology](#physical-topology-and-logical-topology)  
     - [VLAN Trunking](#trunking)
          - [Native VLAN](#native-vlan)
          - [Port Assignment in VLANs](#port-assignmen-in-vlans)
     - [VTP Vlan Trunking Protocol](#vtp)
          - [VTP Messages](#vtp-messages)
          - [VTP  Modes](#vtp-modes)
          - [Problem with VTP](#serious-issue-with-vtp)
     - [DTP Dynamic Trunking Protocol](#dtp)

- [STP Spanning Tree Protocol](#stp)
     - [BPDUs in STP](#bpdus)
     - [Extended Bridge ID and Portfast](#extended-bridge-id-and-portfast)
     - [Path Cost](#path-cost)

- [CDP Cisco Discovery Protocol](#cdp)
     - [Disabling CDP](#disabling-cdp) 

- [LLDP Link Local Discovery Protocol](#lldp)


- [Port Security CCNA-Sec](#port-security)
     - [How MAC addresses are learnt](#learning-mac-addresses)
     - [Basic Default Port Security , limit of 1 MAC address](#testing-basic-port-security)
     - [Port Security Step-by-Step on Basis of MAC addresses](#port-security-with-specific-mac-address-manually)
     - [**Sticky** Port Security](#port-security-sticky)
     - [CAM Table overflow attack](#CAM-table-overflow-attack)

- [Difference Between Switched Ports and Routed Ports](#switchports-versus-routed-ports)
- [Inter-VLAN Routing](#inter-vlan-routing)
- [IP Routing](#ip-routing)


___

# Binary and Decimal

## bit About?

**Decimal** - `Base10` 

**Binary** - `Base2`

### Decimal to Binary

Example: 192

|             | 192         | 
| :---        |    :----:   |          
| 2           | 96   `0`    | 
| 2           | 48   `0`    |
| 2           | 24   `0`    |
| 2           | 12   `0`    |
| 2           | 6    `0`    |
| 2           | 3    `0`    |
| 2           | 1    `1`    |
| 2           | 0    `1`    |
|             |             |


*In the column reperenstation above we divide 192 with 2 {school??} now once on division if we get remainder as 0 we mark it as zero and if we get a non-zero remainder we mark that as 1 and once we are completely done we can arrange the 1's and zero's from bottom to come up with the binary repersentation, also note that if the resulting the repersentation is not 8 digits we can add 0's in the starting to complete 8 digits length*

**Thus Binary for 192** - `11000000`

___

### Binary to Decimal

Example: 11000000

*For converting Binary to decimal what we can do is arrange this given binary number and mark it from 0 to X*

 **1 1 0 0 0 0 0 0** 
 
*7 6 5 4 3 2 1 0*

*now once this is marked we will only consider the binary 1's and then we will note the numbers marked on them.*

**1 1** 

*7 6*

*Now we will add these numbers together with power of 2 eg: 2^7 + 2^6 *

**so: 2^7 + 2^6 = 128 + 64 = 192** 

___

# Hexadecimal

### Decimal to Hexadecimal

*below is the repersentation of Decimal in Hexadecimal*

| Decimal     | Hexadecimal | 
| :---        |    :----:   |          
| 1           | 1           | 
| 2           | 2           | 
| 3           | 3           | 
| 4           | 4           | 
| 5           | 5           | 
| 6           | 6           | 
| 7           | 7           | 
| 8           | 8           | 
| 9           | 9           | 
| 10          | A           | 
| 11          | B           | 
| 12          | C           | 
| 13          | D           | 
| 14          | E           | 
| 15          | F           | 


Example: 192

**Step1**

*The very first thing to do would be to convert the given decimal number to Binary*

**Technique covered in sections above**


|             | 192         | 
| :---        |    :----:   |          
| 2           | 96   `0`    | 
| 2           | 48   `0`    |
| 2           | 24   `0`    |
| 2           | 12   `0`    |
| 2           | 6    `0`    |
| 2           | 3    `0`    |
| 2           | 1    `1`    |
| 2           | 0    `1`    |
|             |             |

**Thus Binary for 192** - `11000000`

**Step2**

*Then we will divide the 8 bit number we have in two portions of 4 bits each, note that if the number you obtain after the division technique and its not 8 bits you can add zero's to the starting of number to complete 8 bits and then proceed with the bisection*



**Bisection**

1 1 0 0 **|** 0 0 0 0

*After this we need to convert each of these portions to decimal using the same marking with numbers method we saw earlier but keep a note that for each portion we will start from zero to x*

1 1 0 0 **|** 0 0 0 0

3 2 1 0 **|** 3 2 1 0

*now only considering the 1's*

2^3 + 2^2 **|** 0

8 + 4 = 12 **|** 0

12  **|** 0

*Now we saw that 12 in Hex is C and zero remains zero so the Final number would be **C0***

`Answer`: **C0**


# OSI and TCP/IP Model 

## OSI model

|No.| Remember       | Layers        |    Just some examples             |
|:--- | :---           |    :----:     |    :----:                         |
|7|**A**ll         | Application   |HTTP,FTP,SSH,DNS                   |
|6|**P**eople      | Presentation  |SSL,IMAP,FTP                       |
|5|**S**leeping    | Session       |API's,sockets                      |
|4|**T**hrough     | Transport     |TCP,UDP                            |
|3|**N**etworking  | Network       |IP,ICMP,IPSec                      |
|2|**D**on't       | Data-Link     |Ethernet,Bridge,Switch {layer2}    |
|1|**P**ass        | Physical      |Fiber,Hubs,Coaxil,Repeaters        |


## TCP/IP Model

**In TCP/IP model the First 3 layers{application,presentation,session} from OSI model have been merged into one Layer{application}**

|No.| Remember       | Layers        |    ?                              |
|:--- | :---           |    :----:     |    :----:                         |
|5|**A**ll         | Application   |                                   |
|4|**T**hrough     | Transport     |                            |
|3|**N**etworking  | Networking    |The PRO value in this layer would tell  Layer 4 what protocol to user TCP/UDP...                      |
|2|**D**on't       | Data-Link     |The TYPE value in this layer would tell layer 3 what to use IPv4/6    |
|1|**P**ass        | Physical      |                                   |

# IP addressing

   - consists of 4 octets
   - each octet of 8bits makes IP address of 32 bits in Total
   - X.X.X.X   [example: 192.168.1.1]
   - Each X in this address is 8bits 

## Network Address portion [Network-ID]

   - Identifies a specific network
   - routers maintain routing tables that contains the network-ids
   - Look at destination IP address and match to network address

## Host Address portion [Host-ID]

   - Identfies a specific endpoint on a network
   - devices on network such as computers,laptops,phones etc.

## Address classes [Deprecated]

*Note: these address classes have now been replaced with CIDR {classless interdomain routing}, regardless we will also have a look at them*

**Unicast**
```
Class A

Class B

Class C
```
**Multicast**
```
Class D

Class E
```

___

### Class A

   - Starts with Binary 1
   - Ends with 126
   - Binary Range  1.0.0.0 to 126.255.255.255
 
*Note: The supposed range is from 0.0.0.0 to 127.255.255.255 but 0 is reserved for Default Network and 127 for loopback*

**Network portion: `8 bits`**

**Host portion: `24 bits`**

*Example*: 10.1.1.1
    
   - Network 10.0.0.0
   - Host 10.1.1.1

___

### Class B
   - Starts with 128
   - Ends with 191
   - Binary range 128.0.0.0 to 191.255.255.255
 
**Network portion: `16 bits`**

**Host portion: `16 bits`**

*Example*: 172.16.1.1

   - Network 172.16.0.0
   - Host 172.16.1.1

___

### Class C

   - Starts with 192
   - Ends with 223
   - Binary Range  192.0.0.0 to 223.255.255.25


**Network portion: `24 bits`**

**Host portion: `8 bits`**

*Example*: 192.168.1.1

   - Network 192.168.1.0
   - Host 192.168.1.1

____

### Class D

**Multicast, such as used by routing protocols**


   - Starts with 224
   - Ends with 239
   - Binary Range  224.0.0.0 to 239.255.255.25

____

### Class E

**Reserved**

   - Starts with 240
   - Ends with 225
   - Binary Range  240.0.0.0 to 255.255.255.25

___

## Special addresses

### Directed Broadcast address
   
   - sends data to all devices on the network
   - Binary 1's in entire host portion of the address 

*Example*: Network- **172.31.0.0**

   - Directed Broadcast: 172.31.255.255

**A router can can be configured to route directed broadcasts but they are disabled by default due to a security issue that can lead to DOS attacks** 

*Example Below* {**take a moment to appreciate the art work :)**}

![](https://github.com/SxNade/P4ck3t/blob/main/bcast.png)

*In the simple network topology shown above we have a Network 172.16.0.0 in which two machines A{172.16.0.1} and B{172.16.0.2} are present, the Router also has another Network 172.31.0.0 which has over 100 machines.*

**If the router is configured to forward Directed Broadcasts then the request sent by the Attacker with source IP of victim [machine A] will be sent to all the machines present in the other Network {since its a broadcast}{172.31.0.0 in this case}, now all the machines present in the Network 172.31.0.0 will reply back to the Victim {because the broadcast was sent with the source IP of victim} and this will cause massive amount of traffic flowing back to the machine eventually causing a DOS attack**

*Tools such as **smurf** can be used to perform such attacks*

### Local Broadcast address

  - used to communicate with all devices on network
  - 255.255.255.255
  - Dropped by Layer3 devices
  - we can setup DHCP Relaying if our DHCP server is in a Different Network

Example: when a Host connected to a network requests an IP address it will send a broadcast to request an IP address from the DHCP server

### Local loopback address

   - used to let a system send a message to itself
   - useful to make sure that TCP/IP stack is correctly installed on a machine

**Note: Remember that any address in range 127.x.x.x is a loopback address and as this is a Class A network we have over 16 million loopback addresses on a machine and this is also seen as a mistake of network designers since by doing this we lost use of over 16 million addresses on public networks**


### RFC private addresses

*Reference URL*: https://datatracker.ietf.org/doc/html/rfc1918

**IANA has reserved a Private Address space**

```diff
- 10.0.0.0     10.255.255.255  (10/8 prefix)
- 172.16.0.0   172.31.255.255  (172.16/12 prefix)
- 192.168.0.0  192.168.255.255 (192.168/16 prefix)
```

### IPv4 Link Local addresses

*Reference URL*: https://datatracker.ietf.org/doc/html/rfc3927#page-10

*Reference URL*: https://docs.microsoft.com/en-us/windows-server/troubleshoot/how-to-use-automatic-tcpip-addressing-without-a-dh
   
   - Automatic Private IP Addressing (**APIPA**)
   - Range: 169.254.0.0/16

## Subnet Masks

   - used to determine the Network and Host portion
   - Find if a device is Remote or Local

**Remote: to be reached via Default gateway**

**Local: can be reached directly without Default gateway**

*Class A,B,C have Default masks known as Natural masks*

```diff
- Class A  255.0.0.0
- Class B  255.255.0.0
- Class C  255.255.255.0  
```

**Note: cisco devices don't support discontiguous masks such as 240.255.3.297, only contiguous masks like 255.255.192.0 or 255.240.0.0 are supported**

## CIDR

  - Classless inter-domain routing
  - Replaces Classful IP addressing
  - allows us to use VLSM {variable length subnet masks}
  - 10.0.0.0/8 Rather than 10.0.0.0 255.0.0.0


# Subnetting

*we will see primarly see **"Quick Binary"** method*

   - given host IP we need to Find 
   - Network/subnet
   - First Host
   - Last Host
   - Broadcast

## General Rules

   - For subnet Fill the Host portion with zeros
   - For Broadcast Fill the Host portion with 1's
   - For First Host add 1 to the subnet
   - For Last Host subtract one from broadcast

### Part1

*Example: 192.168.1.18/24*

*right away we can see that we have /24 now each octet in IP makes up to 8bits and this means that the Network portion of 24 bits is **192.168.1** and the remaining host portion is **.18***

**we will convert the host portion to Binary using the Method we saw in [Binary and Decimal Conversions](#binary-and-decimal)**

converted: 192.168.1.00010010
```diff
- Subnet: now in order to find the subnet we need to fill the Host portion will 0's.
+ converted: 192.168.1.00000000
- Hence the subnet is 192.168.1.0

! First Host: First host is one more than subnet which will be 192.168.1.1

- Broadcast: For broadcast we fill the Host portion with 1's 
+ converted: 192.168.1.11111111
- Hence the Broadcast address is 192.168.1.255

- Last Host: Last Host is 1 less than the broadcast which will be 192.168.1.254
```

### Part2

*In this example we will have a look at address in which host portion is present beyond octet boundary*

Example: 172.16.35.123/20

*/20 means that the host portion starts some where between 35. so we will convert 35 and 123 in binary*

```diff

- 172.16.0010 | 0011.01111011

- Subnet: now in order to find the subnet we need to fill the Host portion will 0's.
+ - 172.16.0010 | 0000.00000000   {we will also convert it to binary again and count from end of each octet even if its divided}

! Hence subnet is 172.16.32.0

- First Host: 1 more than the subnet hence 172.16.32.1

- Broadcast: Fill host portion with  1's
+ - 172.16.0010 | 1111.11111111   {we will also convert it to binary again and count from end of each octet even if its divided}

! Hence Broadcast is 172.16.47.255

- Last Host: 1 Less than the broadcast hence 172.16.47.254
```


### General Rules

*When asked For number of Hosts: **Hosts = 2^n - 2***
   - we count Host bits from right hand side

*When asked For number of Networks: **Networks = 2^n*** 
   - we count Host bits from left hand side
   - n is number of bits in Host portion

___

#### Subnetting a Given network when asked for Number of hosts required

**Note: we count Host bits from right hand side**

Question: *we are given a subnet 10.1.1.0/24 and we need to divide the network into smaller subnets where each subnet needs to support 14 hosts*

**we have /24 which means that the host portion is the last octet of the IP address**

*For 14 hosts the value of n should be approx 4*

```diff

- 10.1.1.       00000000
  <--Network--> <--Host-->
```
*The host portion has 8 bits but we only need 4 bits in host portion*

**after counting and dividing we get the Following**

```diff

- 10.1.1.         0 0 0 0     0 0 0 0
  <--Network--> <--subnet--> <--Host-->
```

*now we can only mangle with subnet portion, but now the new subnet mask is 8+8+8+4{from subnet portion} that is /28*

**we will change the 0's to 1's one by one {we don't need to go through all permutations}**

*1st Network*

```diff

- 10.1.1.         0 0 0 0     0 0 0 0
  <--Network--> <--subnet--> <--Host-->
```

*now we need to convert entire host portion to decimal again and the resulting network is*


```diff

- 10.1.1.0/28
```

*2nd Network*

```diff

- 10.1.1.         0 0 0 1     0 0 0 0
  <--Network--> <--subnet--> <--Host-->
```

*now we need to convert entire host portion to decimal again and the resulting network is*

```diff

- 10.1.1.16/28
```


*3rd Network*

```diff

- 10.1.1.         0 0 1 0     0 0 0 0
  <--Network--> <--subnet--> <--Host-->
```

*now we need to convert entire host portion to decimal again and the resulting network is*

```diff

- 10.1.1.32/28
```

*we can see that the networks are incrementing with the same difference of 16 hence we can easily deduce networks after 1 or 2*

*Last Network*

```diff

- 10.1.1.         1 1 1 1     0 0 0 0
  <--Network--> <--subnet--> <--Host-->
```

*now we need to convert entire host portion to decimal again and the resulting network is*

```diff

- 10.1.1.240/28
```

**we have total 2^n or 2^4 = 16 networks with each supporting 14 hosts**

___

#### Subnetting a Given network when asked for Number of Subnets required

*Example: we are given a network 10.128.192.0/18 and we need to subnet it into 30 subnets with maximum number of hosts*

*Now as we know that its /18 the octet boundary lies after 128 that is from 192 and so on*

*also we know that for subnets the formual is 2^n hence for 30 subnets n ~= 5*

**we count the bits from Left to right, also note that now the network portion has 5 more bits hence the mask is /23**

```diff

- 10.128.11     0 0 0 0 0     0 .0 0 0 0 0 0 0 0
<--Network-->   <--subnet-->   <--Host-->
```

*1st Network*

```diff

- 10.128.11     0 0 0 0 0 0   0.0 0 0 0 0 0 0 0
 <--Network-->  <--subnet-->   <--Host-->
```

*now we need to convert entire host portion to decimal again and the resulting network is*


```diff

- 10.128.192.0/23
```

*2nd Network*

```diff

- 10.128.11     0 0 0 0 0 1   0.0 0 0 0 0 0 0 0
 <--Network-->  <--subnet-->   <--Host-->
```

*now we need to convert entire host portion to decimal again and the resulting network is*


```diff

- 10.128.194.0/23
```

*Last Network*

```diff

- 10.128.11     1 1 1 1 1 1   0.0 0 0 0 0 0 0 0
 <--Network-->  <--subnet-->   <--Host-->
```

*now we need to convert entire host portion to decimal again and the resulting network is*


```diff

- 10.128.254.0/23
```
*Now as we have n=5 we have 32 subnets/networks each with maximum hosts*


___

# Cisco IOS Software and Device Configuration

**Cisco IOS is the most common operating system in cisco devices some cisco devices also have Nexus-OS**

## Connecting to the Device

  - console cable
  - Physical connection can be made through the EXEC interface
  - through telnet, ssh etc. once the router is already configured for the same 

**Note: Important thing to remember is that when the router boots up it looks for device configuration file by sending a TFTP request at local broadcast address by default** 

## Modes

   - User Mode {Default}
   - Privilege Mode or Enabled Mode
   - Global configuration Mode
   - Interface Mode
   - Line mode
     - console: line console mode
     - auxiliary: line aux mode
     - vty: configure vty ports used for telnet or ssh etc..
   - Router Mode
      



## Some things to Remember

   - Always use [tab] for command completion
   - ? can be used to ask for help , will also display completed commands or sub-commands
   - by default we enter in user mode **prompt>**
   - en {short for enable} or enable can be used to switch to enabled or privileged mode **prompt#**
   - conf t {short for configure terminal} can be used to switch to global config mode **prompt(config)#**
   - int f0/0 {f0/0 is the interface name} will take us to interface mode **prompt(config-if)#**
   - line console 0 will take us to line mode **prompt(config-line)#**
   - router "routing-protocol" {eg: router rip} will take us to router mode **prompt(config-router)#**
   - up and down arrow key can be used to go through command history
   - show history command will display the entire history of commands at once
   - CTRL+A will take you to the beginning of a command
   - CTRL+E will take you to the end of a command
   - CTRL+U will clear entire typed command
   - CTRL+C will cancel a command 
   - show startup-config will display the startup configuration
   - show running-config will display the currently running configuration
   - sh ip int brief {displays ip addr on different interfaces}
   - sh ip route {will show the routing table}
   

**Note: en in user mode will take to privilege mode and we can-not go to Global config mode directly from user mode we can only go to global config mode from privileged mode, also remember to execute the right command in right mode**

![](https://github.com/SxNade/P4ck3t/blob/main/router.png)

### User mode

*Goes by the name*

### Enable mode

  - allows us to use a lot of show commands
  - allows debugging
  - required to configure device

**Note: we can also configure the router to ask for a password when a user tries to switch to privilege mode**

### Global Configuration Mode
  
  - allows us to change global configuration such as hostname,motd etc..
  - conf t is acronym for configure terminal 

#### motd

**Message of the day or motd is displayed when someone connects to our router, we should set a sensible motd to our devices**

*we start by getting to global config mode and then use command banner motd # to start adding a legal message and then we can end the message with #*

![](https://github.com/SxNade/P4ck3t/blob/main/motd.png)

*After we have added the motd we can exit the router and once we connect again we will see the motd*

![](https://github.com/SxNade/P4ck3t/blob/main/displayed.png)

### Interface Mode

  - Change Interface configuration
  - IP address
  - enable/disbale interface
 
#### Be sure to make use of tab completion and also ?

![](https://github.com/SxNade/P4ck3t/blob/main/interface.gif)

### Line Mode
  
  - we can use it to configure a password for router when we connect to the console port.
  - line console 0 {will take us to line mode}
  - login 
  - password "password-to-set"
  - exit or CTRL+Z to exit current mode and so on...

![](https://github.com/SxNade/P4ck3t/blob/main/login.gif)

### Router mode

 - can be used to configure routing protocols {we will mainly focus on OSPF and EIGRP}
 - router ospf  {will take us to router mode and will allow us to configure ospf}

## Managing IOS configuration

 - we can copy configuration from RAM to NVRAM {copy running-config startup-config , will overwrite startup-config with running-config} [short: **copy run start**]
 - we can copy configuration from NVRAM to RAM {copy startup-config running-config , will merge the config } [short: **copy start run**]
 - we can also copy config to a TFTP server {copy run tftp and copy start tftp}

 - configure replace nvram:startup-config   {no merge will replace running with startup-config}

 - erase startup-config {erases the startup-config in NVRAM}

*It is always a good idea to mantain a backup of configuration of router some where , maybe on TFTP server etc..so that even when you replace a router you can just flash the new configuration to bring everything back to normal rather than reconfiguring everything back from scratch*


### Storing files in Flash

 - sh flash {will display the files stored in flash, operating system of router is also stored here by default}

 - cp run flash:first.cfg   {will copy running config to a file first.cfg in flash}
 - more flash:first.cfg  {see contents of first.cfg}
 - wr {to build and save startup-config}

### Terminal Length

 - change the amount of output displayed at once
 - terminal length 0    {will display the Entire output at once}
 - terminal length x    {x is the custom number of lines to display at once}

### Resolve Error

**Note: sometimes when router does not have any DNS servers it might try to resolve a wrong command or a Domain, to resolve this we can run some commands to stop DNS resolution as Follows**

 - en
 - conf t
 - no ip domain lookup

*Now it should time out :)*

# Lab1

**Download the Lab.pkt file, URL: https://github.com/SxNade/P4ck3t/raw/main/Labs/Lab1.pkt**

## Lab Objectives

![](https://github.com/SxNade/P4ck3t/blob/main/Labs/images/lab1.png)

## Task1

*we First need to poweron the devices, we can do so by going to physical and zoom-in to turn the switch to 1*

![](https://github.com/SxNade/P4ck3t/blob/main/Labs/images/lb1-power.png)

**In CLI we will say no to initial configuration Dialogue**

*Now we will configure the Hostname, so that the prompts show Router1 and Router2 respectively*

![](https://github.com/SxNade/P4ck3t/blob/main/Labs/images/lb1-r1.png)

**Similarly we can also configure the hostname on the second one**

## Task2

**Now we need to configure the IP addresses as shown in the Diagram**

**we have 10.1.1.1|2/24 on r1 and r2 so subnet mask is 255.255.255.0

**For Router 1 below**

 - sh ip int brief {in priv mode will show us all the interfaces, we can see what to configure}
 - int gigabitEthernet 0/0/0 
 - no shut {short for no shutdown}
 - ip address 10.1.1.1 255.255.255.0 
 
 - sh ip int gigabitEthernet 0/0/0  {confirm}
 
 ![](https://github.com/SxNade/P4ck3t/blob/main/Labs/images/lb1-r1-int.png)

**After we also configure the interface on r2 we can see the interface going up again so its better to no shut interface after we have configured the IP and mask**

**For Router 2 below**

 - sh ip int brief {in priv mode will show us all the interfaces, we can see what to configure}
 - int gigabitEthernet 0/0/0 
 - ip address 10.1.1.2 255.255.255.0
 - no shut {short for no shutdown}

 - sh ip int gigabitEthernet 0/0/0  {confirm}

![](https://github.com/SxNade/P4ck3t/blob/main/Labs/images/lb1-r2-int.png)

**we can now also try to ping one router from the other**

![](https://github.com/SxNade/P4ck3t/blob/main/Labs/images/lb1-ping.png)

*In the image above we will see that on console of router1 we see one ping is dropped indicated by (.) before 4!'s and this is because First Router1 sends a ARP Request to look for the the target Host's mac {hence First ping drops} and then it successfully pings 10.1.1.2, since 10.1.1.2 already knows the Mac of 10.1.1.1 at this point no ping is dropped from its side*

**Tip: we can run 'sh arp' to see the ARP table of router**

## Task3

*Now we will configure an enable password of "cisco"*
 
  - en
  - conf t
  - enable password cisco
  - exit

![](https://github.com/SxNade/P4ck3t/blob/main/Labs/images/lb1-enpass.png)
![Reconnect and Switch to #](https://github.com/SxNade/P4ck3t/blob/main/Labs/images/lb1-enpass-ask.png)

*Note: when we do sh run we can easily see the enable password in the running config*

## Task4

*we will setup the encryption service which will save the password in config file in encrypted form*

 - en
 - conf t
 - service password-encryption 
 - end

![](https://github.com/SxNade/P4ck3t/blob/main/Labs/images/lb1-enc.png)

## Task5

*enabling a secret password*

**Note: enable password is stored in plain text by default whereas enable secret password stores the password in MD5 encryption by Default**

- en
- conf t
- enable secret cisco123
- end

![](https://github.com/SxNade/P4ck3t/blob/main/Labs/images/lb1-secret.png)

**Note that the enable secret  will overwrite the enable password eg: the password we set with enable secret will be the Final password, hence now the password will be cisco123 not cisco which was previously**

*If we can get our hands on this configuration some-how either by TFTP server or somekind of backup etc. we have the password in clear text or in Hash form, we can also try to crack the hash using hashcat or any other of your choice. for hashcat md5 module is 500*

### Cracking the Hash

*hash file contains the md5 hash we found from conf file*

`hashcat -m 500 hash rockyou.txt`

```
Watchdog: Temperature abort trigger set to 90c

Host memory required for this attack: 345 MB

Dictionary cache hit:
* Filename..: rockyou.txt
* Passwords.: 14344361
* Bytes.....: 139921333
* Keyspace..: 14344361

$1$mERr$5.a6P4JqbNiMX01usIfka/:cisco123          
                                                 
Session..........: hashcat
Status...........: Cracked
Hash.Name........: md5crypt, MD5 (Unix), Cisco-IOS $1$ (MD5)
Hash.Target......: $1$mERr$5.a6P4JqbNiMX01usIfka/
Time.Started.....: Thu Aug 26 07:15:06 2021 (1 sec)
Time.Estimated...: Thu Aug 26 07:15:07 2021 (0 secs)
Guess.Base.......: File (rockyou.txt)
Guess.Queue......: 1/1 (100.00%)
Speed.#1.........:   <---Truncated---->

Started: Thu Aug 26 07:14:55 2021
Stopped: Thu Aug 26 07:15:07 2021
```

## Task6

*Configuring Telnet*

 - en
 - conf t
 - line vty 0 4   {0-4 basically 5 lines}
 - login
 - password cisco

*This will configure password of cisco on telnet and we will try to telnet into this router1 from router2*

![](https://github.com/SxNade/P4ck3t/blob/main/Labs/images/lb1-telnet.png)

*Similarly we can also configure telnet on router2*

## Task7

*Configuring password for console {user mode}*

 - en
 - conf t
 - line console 0 
 - login
 - password cisco
 - end

![](https://github.com/SxNade/P4ck3t/blob/main/Labs/images/lb1-line-console.png)

**and now we will be asked for password when we connect to the console**

![](https://github.com/SxNade/P4ck3t/blob/main/Labs/images/lb1-login-console.png)

**Now it is  recommended that at the End we should save the running config to startup config with {avoid if specifically asked to not do so}**

 - copy run start
     or
 - copy running-config startup-config

 - wr {**will do the same**}


# Lab2

*Our First subnetting lab*

**You can download the lab File from: https://github.com/SxNade/P4ck3t/raw/main/Labs/Lab2.pkt**

![](https://github.com/SxNade/P4ck3t/blob/main/Labs/images/lb2.png)

```
Configure the network as follows:
1) You have been allocated subnet 192.168.1.0/24. 
Subnet this into four subnets as follows 
2) Subnet 1 for site 1
3) Subnet 2 for the link between R1 and the Internet Router
4) Subnet 3 for site 2
5) Subnet 4 for the link between R2 and the Internet Router
6) Configure the routers per the instructions in the diagram.
7) Configure the switches with the second last IP address in the subnet
8) Configure the DHCP servers with the third last IP address in the subnet.
And configure the DHCP server to allocate IP addresses to the clients
9) Verify that PCs can access cisco.com and facebook.com using their browsers
```

**we can right away see that we are asked to subnet the given network in Four subnets that is we are asked for number of networks hence we will use the method we saw earlier**

Here: [Subnetting With Number of Networks Required](https://github.com/SxNade/P4ck3t/blob/main/P4ck3t.md#subnetting-a-given-network-when-asked-for-number-of-subnets-required)


*Now as we know that its /24 which is exactly present on the octet boundary and 192.168.1. is Network portion and .0 is the Host portion*

*also we know that for subnets the formual is 2^n hence for 4 subnets n = 2*

**we count the bits from Left to right, also note that now the network portion has 2 more bits hence the mask is /26**

```diff

- 192.168.1        .0 0       0 0 0 0 0 0 
<--Network-->   <--subnet-->   <--Host-->
```

*1st Network*

*now we need to convert entire host portion to decimal again and the resulting network is*

```diff

- 192.168.1.0/26
```

*2nd Network*

```diff

- 192.168.1        .0 1       0 0 0 0 0 0 
<--Network-->   <--subnet-->   <--Host-->
```

*now we need to convert entire host portion to decimal again and the resulting network is*


```diff

- 192.168.1.64/26
```

*3rd Network*

**Now we know that the network is increasing with 64 so we can right away deduce that the next network is**

```diff

- 192.168.1.128/26
```

*4th Network*

```diff

- 192.168.1.192/26
```

**Hence the Four subnets we have**

 - 192.168.1.0/26
 - 192.168.1.64/26
 - 192.168.1.128/26
 - 192.168.1.192/26
 

## Configuring First subnet

*Now according to the instructions we need to configure router1 with the last IP address in that subnet*

**Subnet we have right now is 192.168.1.0/26**

**Method: [Subnetting for Broadcast,Last,First Host etc.](https://github.com/SxNade/P4ck3t/blob/main/P4ck3t.md#part1)**

*Direct answers will be added here, manual conversion etc have been already covered in previous sections*

**Also Note that as we have /26 the Mask is `255.255.255.192`**

*After calculations we have*

**Network:** `192.168.1.0/26`

**First Host:** `192.168.1.1/26`

**Broadcast:** `192.168.1.63/26`   {Also note that Broadcast is 1 less than the Next subnet}

**Last Host:** `192.168.1.62/26`  {one less than the Broadcast}

**2nd Last Host:** `192.168.1.61/26`

**3rd Last Host:** `192.168.1.60/26`

### Configuring Router1

*we need to configure this router with the last IP address in the subnet which is `192.168.1.62/26`*

![](https://github.com/SxNade/P4ck3t/blob/main/Labs/images/lb2-r1.png)

### Configuring the Switch 

*we need to configure the switch with Second Last IP address in the subnet*

![](https://github.com/SxNade/P4ck3t/blob/main/Labs/images/lb2-s1.png)

*After we have configured this we can also try to ping the router from the switch*

![](https://github.com/SxNade/P4ck3t/blob/main/Labs/images/lb2-s1-ping.png)

*we also need to configure a Default gateway on Switch*

![](https://github.com/SxNade/P4ck3t/blob/main/Labs/images/lb2-s1-def.png)


### Configuring the DHCP server

*we will open DHCP server GUI config and then select the Ethernet interface*

![](https://github.com/SxNade/P4ck3t/blob/main/Labs/images/lb2-dhcp1.png)

*we also need to configure the Default gateway for the DHCP server*

![](https://github.com/SxNade/P4ck3t/blob/main/Labs/images/lb2-dhcp1-def.png)

*Now we should be able to ping both router and switch from the DHCP server*

![](https://github.com/SxNade/P4ck3t/blob/main/Labs/images/lb2-dhcp1-ping.png)

**After all this we need to configure a DHCP pool on the dhcp server, we will go to the services tab**

*we know that in this particular subnet we have 6 bits in host portion so number of hosts is 2^n-2 = 62 hosts so ideally we should add arround 50 hosts in the DHCP pool max hosts*

![](https://github.com/SxNade/P4ck3t/blob/main/Labs/images/lb2-dhcp1-pool.png)

*and Now if we check the PC's they will be allocated IP's through DHCP*

![](https://github.com/SxNade/P4ck3t/blob/main/Labs/images/lb2-dhcp-ips.png)

## Configuring the Next subnet

*Now the subnet we have `192.168.1.64/26` and this is going to be the one between Router1 and the serial link of Internet router*

Now as we know tha the subnet or Network is 192.168.1.64 we can easily work out everything without calculating in Binary

**First Host**: `192.168.1.65/26`  {one more than the subnet}

**Broadcast**: `192.168.1.127/26` {one less than the Next Subnet}

**Last Host**: `192.168.1.126/26` {one less than the Broadcast}

**2nd Last host**: `192.168.1.125/26`

**3rd last host**: `192.168.1.124/26`

*Now according to instructions we need to configure the serial link with First IP on Router1*

![](https://github.com/SxNade/P4ck3t/blob/main/Labs/images/lb2-r1-serial1.png)

**Now we will configure the Internet Router connection to that serial int and we will assign it the last Host address**

![](https://github.com/SxNade/P4ck3t/blob/main/Labs/images/lb2-intrtr-ser.png)

**After this we will be able to ping serial of Router from this internet Router**

![](https://github.com/SxNade/P4ck3t/blob/main/Labs/images/lb2-intrtr-ping.png)

**we can also try to ping the DNS address 8.8.8.8 from PC's in the subnet as well as from Router1**

![](https://github.com/SxNade/P4ck3t/blob/main/Labs/images/lb2-ping-every.png)


`A Quick traceroute to cisco.com will reveal the complete path our packets are following`

![](https://github.com/SxNade/P4ck3t/blob/main/Labs/images/lb2-tracert-pc1.png)


- Our Packet First Switch {not in the traceroute} and 

- Then it Goes to the Ethernet interface on the Router1[192.168.1.62] {packets leave from Serial int on current router} and

- then reach the Serial interface on the internet Router1[192.168.1.126] which then Forwards them to the cisco.com server 


**In a Similar way we can also configure other subnets that need to be assigned to the other Network and Serial link**

**After everything is configured properly we should also be able to reach PC1 running on 192.168.1.1**


`we do a simple traceroute from PC3 to PC1`

![](https://github.com/SxNade/P4ck3t/blob/main/Labs/images/lb2-tracert-final.png)

*In Accordance with the Traceroute {switch and leaving end points are not present in traceroute}*

-  our packet First goes to 192.168.1.190 which is the Router 2 present in the Network
-  Next our packet is shown going to 192.168.1.254 which is the Serial interface connected to Router2
-  Then our Packet goes to 192.168.1.65 which is Serial interface of Router1 connected to Internet Router
-  Finally our Packet reaches to 192.168.1.1 which is PC1 {through switch}


# Lab3


**can be Downloaded from [here](https://github.com/SxNade/P4ck3t/raw/main/Labs/Lab3.pkt)**

**Lab Objectives**

```
In a previous lab, 192.168.1.0/24 was broken up to support the subnets in this lab.
Now you need to subnet the network to extend and conserve IP addresses:
1) Break up 192.168.1.64/26 to support as many subnets as possible with 8 hosts per subnet. 
2) Allocate the first new subnet to site 3. 
3) Manually configure all devices in the subnet.
- Router with last IP address in subnet
- Switch with the 2nd last IP address
- Hosts from first IP address
4) Subnet the last new subnet you got from 192.168.1.64/26 with /30 masks 
and then allocate the subnets to the serial links. Configure the routers appropriately.
5) Verify that PCs can access cisco.com and facebook.com using their browsers
```

![](https://github.com/SxNade/P4ck3t/blob/main/Labs/images/lb3-obj.png)


*Now we need to subnet 192.168.1.64/26 Furthuer into maximum number of subnets with each subnet supporting 8 hosts*

*so the Formula here is 2^n-2 for hosts thus n ~= 4 so actually we will have 14 hosts in each subnet*

**Now we will again use the methods we learned earlier to subnet this network Furthur to come up with the following subnets**

 - `192.168.1.64/28` {1st Network}
 - `192.168.1.80/28` {2nd Network}
 - `192.168.1.96/28` {3rd Network}
 - `192.168.1.112/28` {4th Network}

*We can now allocate the new first subnet to the new network `192.168.1.64/28`*

*Before we do so we have been told that we need to take `192.168.1.112/28` and then break it with /30 masks in other words 2^n - 2 = 2 hosts for n=2 that is we need to subnet it again to support 2 hosts so again we are asked for number of hosts and the value of n = 2 so we subnet this subnet again*

- `192.168.1.112/30` {1st}
- `192.168.1.116/30` {2nd}
- `192.168.1.120/30` {3rd}
- `192.168.1.124/30` {4th}


## Configuring the WAN Link on Site1

**Now we need to change the wan link between Router1 and Internet Router**

**we have the network `192.168.1.112/30` which has mask 255.255.255.252**

 - First host is 192.168.1.113
 - Last Host 192.168.1.114
 - Broadcast 192.168.1.115
 
 *we will now give the Serial interface on Router1 the First ip address*
 
 ![](https://github.com/SxNade/P4ck3t/blob/main/Labs/images/lb3-r1.png)
 
 *and the Internet Router with Last IP address*
 
![](https://github.com/SxNade/P4ck3t/blob/main/Labs/images/lb3intrts.png)


**we can also configure DNS on Router1 to look for cisco.com as Follows**

![](https://github.com/SxNade/P4ck3t/blob/main/Labs/images/lb3-dns-ping.png)

## Configuring site3

**Now we need to configure site3, first we wull configure the WAN link on site3 with `192.168.1.116/30`**

- First host 192.168.1.117
- Last Host 192.168.1.118
- Broadcast 192.168.1.119

```
IntRouter>en
IntRouter#conf t
Enter configuration commands, one per line.  End with CNTL/Z.
IntRouter(config)#int s0/2/0
IntRouter(config-if)#ip address
IntRouter(config-if)#ip address 192.168.1.117 255.255.255.252
IntRouter(config-if)#
00:55:50: %OSPF-5-ADJCHG: Process 1, Nbr 4.4.4.4 on Serial0/2/0 from LOADING to FULL, Loading Done

IntRouter(config-if)#end
IntRouter#
%SYS-5-CONFIG_I: Configured from console by console

IntRouter#
```

**also on the Router4**

```
R4>
00:55:50: %OSPF-5-ADJCHG: Process 1, Nbr 3.3.3.3 on Serial0/1/0 from LOADING to FULL, Loading Done

R4>en
R4#conf t
Enter configuration commands, one per line.  End with CNTL/Z.
R4(config)#int s0/1/0
R4(config-if)#ip addres
R4(config-if)#ip address 192.168.1.118 255.255.255.252
R4(config-if)#end
R4#
%SYS-5-CONFIG_I: Configured from console by console

R4#ping 192.168.1.117

Type escape sequence to abort.
Sending 5, 100-byte ICMP Echos to 192.168.1.117, timeout is 2 seconds:
!!!!!
Success rate is 100 percent (5/5), round-trip min/avg/max = 1/1/1 ms

R4#conf t
Enter configuration commands, one per line.  End with CNTL/Z.
R4(config)#ip doma
R4(config)#ip domain
R4(config)#ip domain-lo
R4(config)#ip domain-lookup 
R4(config)#ip name-server 8.8.8.8
R4(config)#exit
R4#
%SYS-5-CONFIG_I: Configured from console by console

R4#ping cisco.com
Translating "cisco.com"...domain server (8.8.8.8)
Type escape sequence to abort.
Sending 5, 100-byte ICMP Echos to 8.8.8.9, timeout is 2 seconds:
!!!!!
Success rate is 100 percent (5/5), round-trip min/avg/max = 1/9/21 ms

R4#
```

*We are also able to reach the internet to cisco.com etc..*

## Configuring The LAN in site3

*Now as from instructions Before we need to use the First subnet we got From breaking `192.168.1.64/26` with each subnet supporting 8 hosts*

**The First Network we Got From that was `192.168.1.64/28` with mask of `255.255.255.240`**

 - `192.168.1.65` First Host
 - `192.168.1.78` Last Host
 - `192.168.1.79` Broadcast

**We would have to allocate IP addresses to the PC's statically between range of 65-78 excluding 65 and 75 themselves**


**First we need to configure the Gigabit interface on router4**

![](https://github.com/SxNade/P4ck3t/blob/main/Labs/lb3-r4-gig.png)

**And then we will configure the IP address for VLAN on switch, we will also specify the Default gateway on switch as the Router4 gig**

![](https://github.com/SxNade/P4ck3t/blob/main/Labs/lb3-s3-vlan.png)

*Next we can also try reaching cisco.com from switch after configuring the DNS as we saw earlier*

![](https://github.com/SxNade/P4ck3t/blob/main/Labs/images/lb3-s3-internet.png)

*In the traceroute we can see that the packets First go to `192.168.1.65` which is the gig of router4 and then to `192.168.1.117` which is serial interface of internet Router and then eventually to the cisco.com server*

## Configuring the IP addresses on PC's 

*Since we don't have a DHCP server in the network we need to statically configure IP addresses on the PC's*

**The range we have is:** `192.168.1.65` to `192.168.1.78` {excluding these start and end IP's} {subnet mask /28 which is 255.255.255.240}

- PC6 192.168.1.66
- PC7 192.168.1.67
- PC8 192.168.1.68

**Below is screenshot of only PC6, others can be configured in same way**

**First we need to go to settings to configure the DNS server to 8.8.8.8 and Default gateway to 192.168.1.65 {router4 gig interface}**

![](https://github.com/SxNade/P4ck3t/blob/main/Labs/images/lb3-pc7-gateway.png)

**After this we can select the Fast ethernet interface and configure the static IP**

![](https://github.com/SxNade/P4ck3t/blob/main/Labs/images/lb3-pc7-static-ip.png)

### Finally we can Try pinging the Router and even try reaching cisco.com from PC6

![](https://github.com/SxNade/P4ck3t/blob/main/Labs/images/lb3-pc-ping.png)

**We will also able to reach PC's in the other sites from site3's PCs {pc6 in example below}**

![](https://github.com/SxNade/P4ck3t/blob/main/Labs/images/lb3-tracert-site3.png)

`Path is depicted below`

![](https://github.com/SxNade/P4ck3t/blob/main/Labs/images/lb3-path-final.png)


# Some Questions

## Question1

*Below is a simple network where two routers are connected together, Router1 has IP address 10.1.1.1/24 and Router2 has IP address 10.1.2.2/24 will the Routers be able to ping each other*

![](https://github.com/SxNade/P4ck3t/blob/main/Questions/q1.png)

*Now since we know that /24 means 255.255.255.0 and this implies that the First Router is on Network 10.1.1.0 whereas the second Router is 10.1.2.0 and this means that both are on different Networks and since there is no Default gateway present {which could do some kind of routing bw two} The Devices will not be able to ping each other*


**On Router1 we can run following commands and then try to ping 10.1.2.2**

*Switch on Debug Mode*

 - debug ip packet    {in priv mode}
 - ping 10.1.2.2

**In debugging mode we will be more clear about whats happening**

![](https://github.com/SxNade/P4ck3t/blob/main/Questions/q1-debug.png)

*The Debug mode states that the packets are unroutable*

**In order to make this work we would have to change the mask on both sides to /16 or 255.255.0.0**, with that our Network portion on Both sides would be `10.1.0.0` and `10.1.0.0` respectively {same} which means that the two routers should then be able to ping each other.

`we will now change the subnet masks on both sides`

![](https://github.com/SxNade/P4ck3t/blob/main/Questions/q1-config.png)

*We will again try the ping in debug mode*

![](https://github.com/SxNade/P4ck3t/blob/main/Questions/q1-ping-done.png)

*Its clearly visible that the first ping fails that is because of ARP and the other all pings are successfull*


## Question2 

*Below is a small network where two routers are connected togther , IP's and masks are written. will these Routers be able to ping each other*

![](https://github.com/SxNade/P4ck3t/blob/main/Questions/q2.png)

*To test this we can enter following command on Router1 to debug icmp*

 - en
 - debug ip icmp

**Then we can send pings from Router0 to see what happens**

![](https://github.com/SxNade/P4ck3t/blob/main/Questions/q2-ping.png)


*Now this worked because both the machines are present in the same Network or in other words they have same Network-ID, we can observe this after converting the 3rd octet of both IP's into binary and we will see that the entire Network portion on both machines is same hence they were able to ping each other*

## Question3

*Below is a simple netork of two connected Routers, will these routers be able to ping each other*

![](https://github.com/SxNade/P4ck3t/blob/main/Questions/q3.png)

*we can also check the running config of both routers to confirm the IP and mask*

![](https://github.com/SxNade/P4ck3t/blob/main/Questions/q3-conf.png)

**Now we know that the network portion is /20 thus the Network portion of both the IP's are different which means that they will not be able to reach each other directly eg: they will not be able to ping each other**

*we can convert both to binary*

**10.1.248.1/20*

```diff

- 10.1.1111    1000. 00000001 
<--Network-->  <--Host-->
```
**10.1.192.2/20*

```diff

- 10.1.1011    0110. 00000010 
<--Network-->  <--Host-->
```


**as it is clearly visible that both of them have diff network portions they will not be able to ping each other**

![](https://github.com/SxNade/P4ck3t/blob/main/Questions/q3-ping.png)


# Cabling and Packet Flows

## Types of communication

1. **Unicast** - one to one communication
2. **Broadcast** - one device sends traffic to all devices in a subnet or in entire network {depends on the configuration of the network}
3. **Multicast** - one device sends traffic to some devices {multiple but only specific devices}

## A bit of Ethernet

**Just a Short Revisit**

`Layer1`
   - Physical {ethernet}

`Layer2`
   - Data Link {Mac Addresses}
 
`Layer3`
  - Network {IP addresses}

`Layer4`
  - Transport {TCP/UDP}


**Some old implementations of cables**

 - `10base5` 
    - Thicknet 
    - range: 500 m

 - `10base2` 
    - Thinnet 
    - range: 185 m
    - coaxil cable
    - maximum speed of 10Mbps
    - base means baseband

### Difference Between baseband and broadband

 - `Baseband`
   - only allows single signal to traverse the wire at any given time and that signal uses all the frequencies

 - `Broadband`
   - allows multiple signals to traverse the wire at any given time.


## MAC address

 - 48 bits in Length
 - OUI portion 24 bits + Station Address 24 bits
 - OUI is the organizational identifier which tells us the company manufacturing the device
 - End Station adddress has to be a unique value

![](https://github.com/SxNade/P4ck3t/blob/main/pimages/2021-09-01_00-13.png)


**CSMA/CD is used in a Bus topology in an ethernet network**

CS: carrier sense
MA: multiple access

CD: collision detection

## Problems with 10base2

 - short length, more length means more signal degradation
 - bandwidth is shared among all devices in a network
 - single collision domain
 - single broadcast domain
 
**Hence 10base2 was replaced with 10baseT**
 - 10baseT usually a unsheilded twisted pair
 - sheilded twisted pair also may be used
 - single broadcast domain
 - T means twisted pair
 
 ## UTP 
 
 *unshielded twisted pair*
 
 ![](https://s3-us-west-1.amazonaws.com/foscoshopify/graphics/uploads/2011/01/UTP-Cable-Picture.jpg)
 
 **color coding**
 
 ![](https://github.com/SxNade/P4ck3t/blob/main/pimages/2021-09-01_01-59.png)
 
## Straight through cables

 - used when connecting a PC to something like switch,bridge etc..

## crossover cable

 - allows to connect devices of same type


## Difference between the two

![](https://i.ytimg.com/vi/tOhER85dyFw/mqdefault.jpg)


## Modern cabling

**In modern days something like MDI / MDIX is used**

 - normally routers & pc's use MDI
 - Normally switches and hubs use MDIX {media dependent interface crossover}

 - Auto MDI/MDIX allows for automatic switching once a cable is connected
 - Auto detect cable type (cross over / straight through)
 - so we don't need to worry about the cable type today but still we should keep a check

## Cable categories

**Higher category**

 - more twists
 - less susceptible to electromagnetic interfrence

*CAT1*
 - was previously used for telephones and modems 

*CAT1*
 - was previously used for telephone and data networks up to 4mbps
  
*CAT3*
 - was previously used for networks up to 10Mbps now generally used for telephones

*CAT4*
 - Defined up to 20MHz with speeds up to 16Mbps

*CAT5* 
 - Defined up to 100Mhz speeds of 10/100 Mbps supported longer cable length

### CAT5e

 - defined up to 100MHz support 1Gbps
 - improves upon crosstalk specifications
 - 100Mbps

### CAT6

 - defined up to 250 Mhz supports 10Gbps 
 - 55m
 - Better crosstalk specifications

### CAT6a

 - defined up to 500 MHz suppors 10 Gbps
 - 100m
 - a means augmented
 - improvements in crosstalks

### CAT7

 - defined up to 600 Mhz support 10Gbps - 100m
 - Different connector than RJ45
 - also known as class F

![](https://5.imimg.com/data5/JF/RJ/MY-5307513/cat7-fiber-cable-500x500.jpg)

**Tera connector**

![](https://upload.wikimedia.org/wikipedia/commons/c/ca/Tera_steckverbinder.JPG)


### CAT7a

 - defined up to 1000 Mhz support 100Gbps 
 - 50m
 - also known as class Fa

### CAT8

 - supports 40Gbps

**CAT8.1**
 - backward compatible and interoperable with Cat 6a
 
**CAT8.2**
 - interoperable with Cat 7
 

### Direct Attachment cable

**DAC copper twinax**

- up to 15m
- has SFPs on each end
- SFP: small form factor pluggable
- may support fiber or copper
- this replaces GBIC's {Gigabit interface converters}
- inserted in SFP+ slot

![](https://pactech-inc.com/wp-content/uploads/2021/05/Direct-Attach-Copper-DAC-Cable-%E2%80%93-Rapide%E2%84%A2-10G-SFP-Passive-Twinax-Cable-Connectors-1.jpg)

### Roll Over Cable

 - special cable used in console of networking devices
 - COM to console

![](https://upload.wikimedia.org/wikipedia/commons/c/c0/CiscoConsoleCable.jpg)

## Hub

 - not very popular today
 - replaced by bridges and then bridges by switches.
 - wireless operates in same way as hub
 
 
 - is a physical layer device
 - hub is dumb
 - multiport repeater
 - repeats the frame found on one port to all other ports
 - Physical topology of a hub is a star topology

![](https://4.bp.blogspot.com/-wofJZwcU0zg/VoLQ5bY1A8I/AAAAAAAAALA/MF4_OIrlqO4/s1600/star.jpg)

 - **If a cable broke only one device is affected**
 - Distance can be extended easily by adding another hub

**Hub is a multiport repeater**

*For example in the topology shown below the Packet sent by A destined to C is Forwarded by Hub to All devices connected but is only accepted by C and dropped by Rest of them*

![](https://github.com/SxNade/P4ck3t/blob/main/pimages/2021-09-01_03-28.png)

**Physical Topology**: `Star`

**Logical Topology**: `Bus`

*Although The physical structure is a Star the network functions like a Bus, Hence its a Single collision,broadcast Domain*
 - bandwidth also gets divided with number of devices present

## Bridge 

 - Layer2 device
 - more intelligent than hub
 - has a MAC address table known as CAM table {processing in software, where as switches do so in Hardware}
 - Star Topology
 
 **when a birdge boots up the mac address table of bridge is empty**
 
 *Initial traveling of the packet*
 
 ![](https://github.com/SxNade/P4ck3t/blob/main/pimages/2021-09-01_03-45.png)
 
 *In the diagram above when A sends a packet to C it will be fowarded by bridge to all other ports {meanwhile Bridge will also pupulate the CAM table with A's mac-address} and then once C accepts the packet it will send a reply {bridge will then also add address of C to CAM table}*
 
 
*Now that the Bridge knows where A and C is suppose C sends a packet to A , bridge will directly send it out from port A as it knows the position of A from its CAM table*
 
![](https://github.com/SxNade/P4ck3t/blob/main/pimages/2021-09-01_03-49.png)

 - in The topology above there are 4 collision Domains
 - all the hosts in the network are on a different collision Domain
 - However its still the same Broadcast Domain

## Switch

 - Layer2 device
 - processing is done using ASICs (Application integrated Circuits)
 - no degradation in performance between two devices
 - can move traffic at wire speed
 - supports more ports than Bridges
 - star topology
 
 *Siwtch would work similar to bridge but will be a lot faster*
 
 ![](https://github.com/SxNade/P4ck3t/blob/main/pimages/2021-09-01_04-56.png)
 
 - again 4 collision domains in topology above
 - single broadcast domain
 - {dedicated bandwidth}
 - speed / duplex doubles the bandwidth


### Difference Between Half Duplex and Full Duplex

## Half Duplex

 - only one side can send the traffic at once
 - Walkie-talkie

## Full Duplex
 
 - both sides can send and recieve simuntaneously
 - mobile phone call
 - during full duplex collision detection is disabled


## Router

 - Layer3 devices
 - make Routing Decesions based on IP addresses
 - Serial Interfaces: using PPP 
 - Ethernet Interfaces: uses mac for forwarding on layer2


**Similar to CAM tables routers have Routing Table populated with Network addresses**

*Below is a example Network topology*

![](https://github.com/SxNade/P4ck3t/blob/main/pimages/2021-09-01_06-27.png)

*So basically when a devie wants to communicate with a device on local segment, device will send a ARP request broadcast on the local segment targeted to the IP address we probe and the device with that IP address sends ARP reply back*

*Below is wireshark capture of some ARP traffic*

![](https://github.com/SxNade/P4ck3t/blob/main/pimages/arp.png)

**Routing to a PC on Different network**

 - when sending traffic to a target the sender device would see if the target is present on the local segment or not, if the target is not present on the local network the device will still send the packet but in the Layer2 info it would be targeted to the MAC address of the Default Gateway, The sender might send an ARP to the default gateway to First learn its IP address. when the gateway would forward the traffic it would change the Source MAC address of its MAC {target MAC will be of target IP} and the IP info of source and target IP address would remain the same.


**so basically Layer2 info is changed by Layer3 Router when Routing in different networks Layer3 info remains same unless NAT is used**

# Lab4

**You can Download the File**: ![Here](https://github.com/SxNade/P4ck3t/raw/main/Labs/Lab4/Lab4.pkt)


## Lab Objectives

![](https://github.com/SxNade/P4ck3t/blob/main/Labs/Lab4/lb4-obj.png)


**we need to turn on simulation mode in Packet Tracer and then do a ping from PC1 to PC2**

*in our simulation we have already ran a ping in real time mode first to populate arp cache with targte devices mac address , just for convinience and now we will send another ping and also open the box for more info by clicking on the icmp packet in Simulation column*

![](https://github.com/SxNade/P4ck3t/blob/main/Labs/Lab4/lb4-q1.png)

**we can easily see that the target MAC address is the same as that of G0/0/0 interface of Router1, we can see the MAC of router from its running config or even from the config tab**

**Question1**
 - *Hence the Answer to the First Question is: E*

**Question2**
 - *Now The Second Question Asks for that Exact value of MAC: **0010.AAAA.AAAA***

**Question3**
 - *Third Question Asks about the Encapsulation used at A: its Ethernet Layer2*

**Question4**
 - *Fourth Question asks us about the Destination MAC address at B: its going to be the same **E** {we can click the play once and then open the packet details to verfiy}

**Question5**
 - same answer but we need to tell the exact value which is: **0010.AAAA.AAAA***


**Question6-7**
 - Dest mac address at C: we see the outbound PDU of the Packet At Router1 and we see that there is no MAC address {**K**}, the encapsulation used is **HDLC** 
 
 ![](https://github.com/SxNade/P4ck3t/blob/main/Labs/Lab4/lb4-q6.png)
 
**Question8-9-10**
 - The destination MAC address at D is of PC2 **B**
 - we can see the value to be **0010.2222.2222** {note: we can also see this from command prompt with iponfig /all}
 - we can clearly see that the encapsulation used is EthernetII

![](https://github.com/SxNade/P4ck3t/blob/main/Labs/Lab4/lb4-q8.png)


**Question11-12-13**
 - The destination MAC address at E is of PC2 **B**
 - the value is: **0010.2222.2222**
 - The encapsulation used is clearly visible to be **EthernetII**

![](https://github.com/SxNade/P4ck3t/blob/main/Labs/Lab4/lb4-q10.png)

*yeah we can easily answer for echo reply **Note that echo reply will have a ICMP type 0x00, type0x08 is a ICMP request***

# Lab5

**You can Download the File**: [Here](https://github.com/SxNade/P4ck3t/raw/main/Labs/Lab5/Lab5.pkt) 

**all checks will be run in simulation mode**

**Question1**
 - we will send a ping to PC4 running on IP `10.1.1.4`
 - we can inspect the packet that reached to hub and we will see that its a **ARP broadcast packet**

![](https://github.com/SxNade/P4ck3t/blob/main/Labs/Lab5/lb5-q1.png)

**Question2**
 - we forward the packet by one step
 - we will see that the packet is forwarded by Hub to all devices in the network ie. to PC2,PC3,PC4

![](https://github.com/SxNade/P4ck3t/blob/main/Labs/Lab5/lb5-q2.png)

**Question3**
 - Again we forward the packet by two steps
 - we will see that the packet is Forwarded to PC3,PC2 and PC1 when the sent packet from PC4 reaches to Hub.

![](https://github.com/SxNade/P4ck3t/blob/main/Labs/Lab5/lb5-q3.png)


**Question4**
 - in a similar way we forward the packet with play/pause button
 - when PC1 again sends the packet to PC4 the hub will forward it to all devices except the ingress port ie. to PC2,PC3,PC4 , the packet will be accepted by PC4 but will be dropped by the rest since it was intented to IP of PC4.

![](https://github.com/SxNade/P4ck3t/blob/main/Labs/Lab5/lb5-q4.png)

**Question5**
 - when we ping PC8 running on 10.1.1.8 from PC5 in simulation mode we can open the packet  details to  see that its an **ARP Broadcast packet**

![](https://github.com/SxNade/P4ck3t/blob/main/Labs/Lab5/lb5-q5.png)

**Question6**
 - we  click on the play button once to forward the packet from switch , since this is a broadcast it is sent to all the devices present except for the sender.

![](https://github.com/SxNade/P4ck3t/blob/main/Labs/Lab5/lb5-q6.png)

**Question7**
 - During the return traffic sent from PC8 to PC5 the reply traffic is directed  twowards PC5 and hence it would leave from Gi1/0/1 to PC5 since the switch now knows where PC5 is present so only PC5 will get the return traffic.

![](https://github.com/SxNade/P4ck3t/blob/main/Labs/Lab5/lb5-q7.png)


**Question8**
 - now after the reply switch also learned where PC8 is present so now when PC5 replies back the packet is only forwarded to PC8 by the switch
 - we can hit the play button to move the packet {**Note that play once will start the simulation and we can press it again to pause**}

![](https://github.com/SxNade/P4ck3t/blob/main/Labs/Lab5/lb5-q8.png)

**At this moment we can also check the CAM table of Switch and it should contain enteries for PC5 and PC8**

![](https://github.com/SxNade/P4ck3t/blob/main/Labs/Lab5/lb5-macs.png)

**Question9-10**
 - Both in Network1 and Network2 there is a single Broadcast Domain Because when we send a Broadcast {ARP} it was Flooded to all the connected devices {of course leaving the sender}

**Question11**
 - In Network1 there is single collision domain and we can confirm this by seding a ping from two different device to a same device at same moment and we will see that the packets collide
 - In Network2 each device has a sperate collision domain which means there are 4 collision domains again we can check this by running a ping at same moment from two different devices at same time and we will see that the packets are sent one by one and no collision takes place

# Speed Duplex and Speed Mimatch

 - these mismatches occur when autonegotiation fails or when manual configurations are mismatched 
 - For example when one side is configured to use full duplex but the other side may be using half duplex
 - pings might succeed in a duplex mismatch

*During duplex mismatch some errors are generated on the IOS command line that will tell us that there is a Duplex mismatch error on X interface, when testing duplex mismatch by sending a large number of pings at once we might see a Late collision error and this can also be viewed using sh int x {x is the interface}*

![](https://www.ictshore.com/wp-content/uploads/2017/01/1027-03-show_interfaces.png)

**when there is a duplex mismatch the side set to half duplex will see a late collision error**

## Fixing Duplex mismatch errors

**The best way is to set some things to auto**

**On Both Sides**

 - en
 - conf t
 - int x {x is the interface where we saw the duplex mismatch error}
 - speed auto
 - duplex auto {see if we can set this or end here}
 - end


*Note: clear counters x {clears the previuous collision counts etc on interface x..}*

# loopback on a router

*A loopback interface on a router is a logical interface, it never goes down on itself until we manually shut it down*

**we can make a loopback interface using**

 - en
 - conf t
 - interface loopback x {the interface number}
 - ip address 192.168.1.1 255.255.255.0
 - no shut
 - end

we can advertise the loopback interface using a routing protocol such as **OSPF** and then reach it from external network

# TCP vs UDP

 - Both TCP and UDP allow for something known as session multiplexing which means that single host with single IP address is able to communicate with multiple servers
 - Both reside at Layer4

![](https://github.com/SxNade/P4ck3t/blob/main/pimages/tcp-udp.png)


## TCP

 - connection oriented 
 - Full Duplex operation
 - In connection establishment something known as a 3-way handshake occurs
 - segmentation
   - MTU {Maximum transmission Unit} depends on physical medium. {eg: of fastethernet it is 1500 bytes}
   - TCP supports 65495 bytes in a single packet {in theory}
 
 - Maximum Segment size {MSS} is Largest amount of data {in bytes} that TCP will send in a segment  
 - MSS should be set small enough to avoid IP fragmentation {better performance}
 - every segment transferred is acknowledged {**reliability**}
 - Sequencing of data packets 
 - uses end-to-end flow control 
 - TCP uses sliding window to control flow of data {**Basically when you see your internet speed rising slightly and eventually to max**}

### TCP 3way Handshake

![](https://s3.ap-south-1.amazonaws.com/afteracademy-server-uploads/what-is-a-tcp-3-way-handshake-process-three-way-handshaking-establishing-connection-6a724e77ba96e241.jpg)

### TCP Header

![](https://github.com/SxNade/P4ck3t/blob/main/pimages/2021-09-03_07-04.png)

`SYN bit is set` - Initial Sequence number
         - The actualy first databyte will have Seq number of this plus 1

`If no SYN bit` - sequence number is the accumlated sequence number of the first data byte for this paccket of current session.


`ACK bit is set` - ACK number value is equal to the next seq number that reciver is expecting to receive

**The First ACK sent by each end acknowledges the other ends initial sequence number**

**In Ipv4 header is of minimum of 5 words and max of 15 words in other words Minimum size of header is `20bytes` and maximum size is `60bytes` which leaves options for 0-40 bytes, Reserved field is set to 0 and is reserved for Future use!**

### Flags

**Both CWR and ECE {used together} are part of a congestion notification mechanism {Quality of service}**

`CWR` - Congestion Windows Reduced Flag

`ECE` - Echo Congestion Notification Echo Field or Flag 

*when hosts conmmunicate to indicate congestion and let the transmitter know that it needs to slow-down*

`URG` - indicates that the segment is urgent and should be processed asap

`ACK` - used for acknowledgement of data

`PSH` - set by TCP sender to cause TCP receiver to immideately pass that segments data to the receiver's application socket along with all other inordered data that receiver has yet to give to the application

`RST` - Resets the connection

`SYN` - used to synchronize sequence numbers,only the first packet sent from each side will have this flag set

`FIN` - Finish means that there is no more data from the sender


### Window Size

 - Specifies the size of receive window or in other words the number of bytes the receiver is currently willing to receive.

### TCP checksum
 
 - used for error checking of the Header and data 

### Urgent Pointer

 - these 16 bits are used when the URG bit has been set, the urgent pointer is used to indicate where the urgent data ends

### Demo of Sequence Numbers etc

*This is just an example illustration where windows size is assumed to be 1*

![](https://github.com/SxNade/P4ck3t/blob/main/pimages/seqnum.png)


## UDP

 - connectionless
 - no guarantee of data delivery
 - UDP relies on Hgiher Layer protocols to manage fragments
 - UDP does not have any Flow control {again relies on Higher layer protocols for this}
 - UDP does not setup sessions
 - no reliability
    - provides limited error delivery
 - no data recovery features
   - for example TFTP using UDP has its own built in mechanism to handle this


### UDP Header

![](https://www.gatevidyalay.com/wp-content/uploads/2018/10/UDP-Header.png)

**2bytes - 16bits**

*minimum header length therefore is 8bytes {in Theory max size is 655535 bytes, this is also a max limit that IPv4 will set}, UDP checksum is an optional feature for IPv4 to check for errors whereas in IPv6 it is not optional.*

## How Layers Connect Together

![](https://insights.profitap.com/hs-fs/hubfs/The%207%20Layers%20of%20OSI.png?width=560&name=The%207%20Layers%20of%20OSI.png)

 - At Layer2 in an EthernetII frame there is a Field called Type {**TYPE**} Number which allows the host to differentiate between multiple layer3 protocols {IPv4, IPv6}
 - At Layer3 a Protocol Number is used to differentiate the different protocols running at Layer4, in an IP header the Protocol field {**PRO**} will tell wether TCP or UDP will be used at Layer4
 - At Layer4 a port number is used differentiate multiple applications being used at Layer7


## Port Number

`Complete Range`: 0-65535

`IANA List`: [Here](https://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.xhtml)

![](https://github.com/SxNade/P4ck3t/blob/main/pimages/port.png)

**Typically a random port is used as source port and well known port number is used as destination by `default`**

 - port numbers basically bind layer4 and layer7

![](https://ipcisco.com/wp-content/uploads/2021/01/network-ports-ipcisco.com_.jpg)

**Below is a list of some well known port numbers**

![](https://i.pinimg.com/564x/13/83/25/1383253f7cb1255135bfcc9593c50d97--network-infrastructure-cloud-computing.jpg)

**DNS**: uses UDP to serve requests , TCP is used when the response data exceeds 512bytes or also for `Zone Transferes` ![this??](https://github.com/SxNade/DnsBlade)

**Ephemral Port Numbers**

 - Short lived port used by client side of connection
 - temporary and only last for the duration of the session
 - IANA suggests a range of 49152-65535 for this
 - BSD uses ports 1024-4999
 - Linux uses 32768-61000
 - windows to server 2003 uses 1025 to 5000
 - vista/windows7 uses IANA range
 - free BSD uses IANA range since release 4.6


# DHCP

**DHCP**: *Dynamic Host control protocol*

`as said by google`

*The Dynamic Host Configuration Protocol is a network management protocol used on Internet Protocol networks for automatically assigning IP addresses and other communication parameters to devices connected to the network using a client–server architecture*


**Packet Flow in DHCP**

![](https://www.tutorialandexample.com/wp-content/uploads/2019/07/dhcp.png)

## Configuring a Cisco IOS Network Device as DHCP server

**Below is a simple Network between two Routers, we will configure DHCP on Router on the right side to allocate IP address to the Router automatically**

![](https://github.com/SxNade/P4ck3t/blob/main/pimages/nwrk.png)

*we have configured IP address on Gig interface of Router2 only, we will now configure DHCP on the same to automatically assign IP address to R1 which will act as a DHCP client here*

**we will configure DHCP server on R2 and also we will configure the interface on R1 to use DHCP for ip allocation** 

![](https://github.com/SxNade/P4ck3t/blob/main/pimages/dhcp-nwrk.png)

*we see that after appropriate configuration the IP address was successfully allocated*

**we can also see what DHCP addresses have been allocated by checking the bindings on R2**

![](https://github.com/SxNade/P4ck3t/blob/main/pimages/2021-09-05_05-42.png)

# Lab6

**The Lab file can be Downloaded** [here](https://github.com/SxNade/P4ck3t/raw/main/Labs/Lab6/Lab6.pkt)

*Basic DHCP Server Lab*

![](https://github.com/SxNade/P4ck3t/blob/main/Labs/Lab6/dhcp-conf.png)

*we can also confirm that the PC was successfully allocated an IP address and we can now try to ping the loopback interface of router1*

![](https://github.com/SxNade/P4ck3t/blob/main/Labs/Lab6/ip-alloc.png)

**And now we can try pinging the loopback address, which on router1 is `1.1.1.1`**

![](https://github.com/SxNade/P4ck3t/blob/main/Labs/Lab6/ping-loop.png)

# Lab7

**The Lab file can be Downloaded** [here](https://github.com/SxNade/P4ck3t/raw/main/Labs/Lab7/Lab7.pkt)

![](https://github.com/SxNade/P4ck3t/blob/main/Labs/Lab7/lab7.png)

*Before we can configure the DHCP server on Router1 we will have to configure an IP Helper address on Switch1 to forward DHCP requests*

![](https://github.com/SxNade/P4ck3t/blob/main/Labs/Lab7/swch-ip-help.png)

*Even after this when Router gets a DHCP request from PC's in Other networks {vlan10 and 20} it needs to be aware of those networks, we can make the configuration as follows*

**we will create two static routes to the vlan's via switch**

![](https://github.com/SxNade/P4ck3t/blob/main/Labs/Lab7/stat-rt.png)


**For PC's to ping router1's loopback we need to add a static Route on switch also to reach to the loopback of router1**

![](https://github.com/SxNade/P4ck3t/blob/main/Labs/Lab7/switch-rt.png)

**we also need to enable inter-vlan Routing on the switch with this one single command**

![](https://github.com/SxNade/P4ck3t/blob/main/Labs/Lab7/switch-ip-rt.png)

*we will choose DHCP in config of PC's and then we will configure DHCP on the PC's*

**DHCP pools for both vlans are configured as shown below**

![Pool1](https://github.com/SxNade/P4ck3t/blob/main/Labs/Lab7/pool1.png)

![Pool2](https://github.com/SxNade/P4ck3t/blob/main/Labs/Lab7/pool2.png)

*After this if we check the PC's they will have the IP addresses allocated*

![](https://github.com/SxNade/P4ck3t/blob/main/Labs/Lab7/ip-alloc-pcs.png)

*we can now ping the loopback of router1 from the PC's and also check the Route etc..*

![](https://github.com/SxNade/P4ck3t/blob/main/Labs/Lab7/ping-trc.png)

# VLAN

*Virtual LANs (VLANs) are a solution to allow you to separate users into individual network segments for security and other reasons*

*we can also think of VLAN as a `broadcast domain / a logical network {subnet}`*

**Advantages**

 - Segmentation
 - Flexibility
 - Security

## Physical topology and Logical Topology

**As soon as vlans are implemented in a network the logical topology will be a lot different than the physical topology**

*Below is a simple physical topology with two seprate vlans of `Red and Green`*

![](https://github.com/SxNade/P4ck3t/blob/main/pimages/phys.png)

*In real the Logical topology of the Network looks like as follows*

![](https://github.com/SxNade/P4ck3t/blob/main/pimages/2021-09-08_03-22.png)

**Unless inter-vlan routing is enabled** *when A sends a Broadcast it would only be received by D similarly when C sends a broadcast it will only be received by B*

## Trunking

*we have a similar topology below but here we have the two switches connected to each other with a Trunk link and such type of link is used by switches to communicate vlan information with each other*

![](https://github.com/SxNade/P4ck3t/blob/main/pimages/2021-09-08_03-50.png)

*The trunk ports would run a Trunking protocol*

**Now the same Physical topology would physically look like this**

![](https://github.com/SxNade/P4ck3t/blob/main/pimages/2021-09-08_03-52.png)

**Trunking**

 - Allows multiple VLANs to traverse a link
 - 802.1Q {Trunking protocol}
 - ISL  {deprecated Trunking protocol}

## 802.1Q

*An 802.1q frame looks as follows, it is different than a standard ethernet frame {the image below first has the standard Eth frame and then the 802.1q frame on its bottom}*

![](https://github.com/SxNade/P4ck3t/blob/main/pimages/2021-09-08_03-56.png)

**The frame has a 4byte TAG header, FCS or the checksum is recalculated**

 - TPID or the Tag protocol identifier indentifies this as IEEE 802.1q frame, the TPID is 2bytes in length
 - PRI or priority is 3bit used to priortize certain traffic types over other , heavly used in Quality of service
 - CFI or Canonical Format Indicator was used in old days for compatibility between ethernet and token ring networks

## Native VLAN

*Native vlans are untagged, when a port on a switch is set as Trunk that interface can transmit and receive tagged frames and frames belonging to the Native VLANS do not carry VLAN tags when sent over this trunk so if an untagged frame is received at this trunk port that frame would automatically be associated with the Native VLAN*

![](https://github.com/SxNade/P4ck3t/blob/main/pimages/2021-09-08_05-26.png)

## Port assignment in VLANs

 - `Static VLANs`: Statically assigned by an administrator 
 - `Dynamic VLANs`: using something like VMPS {VLAN membership policy server} {based on MAC address new devices attached are alloted VLANs}
 - `Voice VLANs`: Specifically used by IP phones

## VTP

 - cisco proprietary
 - Layer2 protocol
 - Allows for propogation of VLAN information
     - Addition,deletion and renaming of VLANs
 - Propogated across trunk links

 - VTP uses MAC address `01-00-0C-CC-CC-CC`
 - Messages
     - Summary Advertisements
     - Subset Advertisements
     - Advertisement requests

 - By default Devices would belong to a NUll Domain

**Concept of the Revision Number**

**For example:** 

 *we have a VTP domain named cisco and the initial Revision number on the devices is 1*
 
 ![](https://github.com/SxNade/P4ck3t/blob/main/pimages/2021-09-09_04-28.png)
 
 *and we add a new VLAN3 to the main switch{**the one in which change was made,`added VLAN`**}, the revision number of the switch will increment from Revision1 to Revision2*
 
 ![](https://github.com/SxNade/P4ck3t/blob/main/pimages/2021-09-09_04-30.png)
 
 *After this the information about the new VLAN will be advertised to all other switches in the VTP domain so that they can sync their databases to the latest revision number, the switch on the top will send a `VTP Summary Advertisement` {**Multicast**} to inform them that a change has been made. Then all the devices will send back a `Advertisement Request` to ask for the latest information and then the switch at the top will send detailed information about the change using a `subset advertisement` the net result is that the revision number of all these switches will increment to the same revision number as the switch where the change was made , revision2 in this case*
 
![](https://github.com/SxNade/P4ck3t/blob/main/pimages/2021-09-09_04-38.png)


## VTP Messages

**Summary Advertisement**
 - Every 5 minutes
 - or whenever there is a change
 - inform other switches of the current VTP domain and configuration number


**Summary Request**
 - when switch has been reset
 - VTP domain name has been changed
 - Switch has received a VTP summary advertisement with a higher configuration revision than its own


**Subset Advertisement**
 - Contains a list of VLAN information
 - if there are several VLANs, more than one subset advertisement may be required

## VTP Modes

**Server**
 - Create VLANs
 - Modify VLANs
 - Delete VLANs
 - Sends and forwards advertisements
 - Synchronizes database
 - Saves VLAN configuration

**Client**
 - cannot create,change or delete VLANs
 - sends and forwards advertisements
 - Synchronizes database

## Serious Issue with VTP

*Below is a Simple Network Topology with two different VLANs {Green and Red}*

![](https://github.com/SxNade/P4ck3t/blob/main/pimages/2021-09-11_01-24.png)

*Now suppose that someone plugs another switch to the topology which has only one VLAN blue and revision number of 50*

![](https://github.com/SxNade/P4ck3t/blob/main/pimages/2021-09-11_01-26.png)

*Also note that the port attached with this switch is configured as Trunk including all other links, now what will happen is that this switch will start starting requests for syncing the database and this will cause all other switches to change their Revision number to 50 and this will also cause VLANs Green and Red to be removed , only VLAN present will be Blue on all switches. All the ports present in the Green and Red VLANs will be error disbaled since the VLANs are deleted, this  took down the whole network Nice! :)*

# DTP

*Dynamic Trunking Protocol*

 - Cisco Proprietary protocol

![](https://www.ziaul.co.uk/wp-content/uploads/2016/10/Switchport_Modes.jpg)

# Spanning Tree

**Different Types of Spanning Tree**

 - `IEEE 802.11D`: The legacy standard of Spanning tree {when bridges were used!}
 - `CST`: assume that there is one spanning tree instance for the entire network
 
 - `PVST`: Only supported ISL
 - `PVST+` {Also known as PVST now days}: Suports ISL and 802.1Q
      - `Cisco Enhancement of spanning Tree that provides a specrate 802.1D Spanning Tree instance`

 - `MSTP, 802.1S` {Multiple Spanning Tree}: optimizes PVST by mapping Multiple VLANs to the same Spanning Tree instance
 - `RSTP, 802.1W` {Rapid Spanning Tree}: Improves convergence over the 1998 version of Spanning Tree by Adding Roles to ports and also by Enhancing BPDUs exchanges
     - only supports a single instance of Spanning Tree

 - `Rapid PVST+` {Default in Cisco Switches}
      - one Spanning Tree instance per VLAN and also have Rapid Convergence along
   
**Why spanning Tree?**

*Below is a Sample topology in which we have two switches connected to each other via two links {to provide redundancy}, one PC is also attached to each one of them*

![](https://github.com/SxNade/P4ck3t/blob/main/pimages/2021-09-12_06-30.png)

*when this network is Full functional and we try to ping device B from device A {After ARP and stuff} S1 will update its MAC address table for A and then flush the frame out of all ports except from the ingress port {To look for B}, now when switch2 receives the frame from port1 it will update its MAC address table but then it will also recv the same frame from port3 since S1 flooded it out from all ports and then S2 will be in confusion about what is the location of A*

![](https://github.com/SxNade/P4ck3t/blob/main/pimages/2021-09-12_06-37.png)

*Now in our example we can assume that the frame from port3 came later so s2 will update the CAM table to reflect A on port3*

*Also on the other end while this is going on S2 has flooded the frame to Host B twice for now and this can really get confusing for Device B*

**This also causes constant changing of CAM table in the switches which causes  MAC addresses instability in the CAM table**

## BPDUs

 - contain information about spanning tree
 - unique MAC addresses

*How switches Learn about each other?*

**BPDUs are sent every 2 seconds by the switch**

![](https://github.com/SxNade/P4ck3t/blob/main/pimages/2021-09-12_06-55.png)

**Important info Contained in BPDUs**

 - Bridge ID: 8 byte value unique to switch
     - 2byte priority Feild
     - 6byte system ID {based on Burnt in MAC address of switch}
 
 - Consists of the priority 32768 {in decimal or 8000 in HexaDecimal} by default  
 
 *Sent to Target Multicast address of `01:80:C2:00:00:00 or 01:00:0C:CC:CC:CD for VLAN spanning tree`
 
 **Types of BPDUs**
 
 **1.)** `Configuration BPDU`: used by spanning tree to provide information to switches
 
 **2.)** `Topology Change BPDU`: TO tell switches of a change
 
 **3.)** `Acknowledgement BPDU`: used to confirm the receipt of a topology change in a notification
 
**The lowest MAC address switch becomes the STP root by Default**

### Root ports and Designated Ports

`as we know very well`: **The lowest MAC address switch becomes the STP root by Default**

**Root Port**

![](https://github.com/SxNade/P4ck3t/blob/main/pimages/2021-09-12_08-03.png)

**Designated Port**

`A designated port is the best port to use on a per segment basis to get to the root bridge`

*Any other ports {Altn} are put in BLK or Blocking Mode*

### Extended Bridge ID and Portfast

## Extended Bridge ID

 - STP requires that every switch have a unique Bridge ID

**The priority as split into two parts as Follows**

![](https://slideplayer.com/slide/12988442/79/images/17/PVST%2B+Extended+Bridge+ID.jpg)

*The priority can be only be set as multiple of 4096*

![](https://dl.boxcloud.com/api/2.0/internal_files/250559250437/versions/264222263621/representations/jpg_paged_2048x2048/content/1.jpg?access_token=1!tCU_DaQvrFdM4EUiDb6ebTMCCE8IB-iSrxUO3K_jxaWBNxwxbM_VDLiW0ZOPb1uHJzGgAG0xdzATesKmxek1oxJzlnJ7Rn3dK6IPIKANlwTndRoOWlmJybhUOBIQdZhhQvmQ2R4zQjM3UzijJ0YA-VwGtSl_OU8t5o69Krexy0BMREXE3_39AXN-P2XfWiDPLNaV47GbhBufqskMRVz7olBCCOaHLGcJ6TkNL49oZzAzmJQRmTLLIDqi4IeDYx3rdoKy6BS0cLi24ZhoaxMG9sW7mnNNuifmPKDntc5QN1X40u3PkUwWOKAWswBbWUF1crDvVGR7LRVFlJ0ATjJ8TyUYrxl19dxxycI6Cj1DR0rp6JtCFhB6Pmdu8bvehWgjgEk5KGc5V78_Oq-faSdVprJWV3uIKXybJ5ZKFKrT5Ihjg4zSoNGbwxCMEx0OvN2hkcv35WT67jpsVAscosdeDbSGyXlh6jqtD7yEo3OBp3XiMgyS_0ZlHu8Kh5qk-HVpo-PLydxaenqKTy6FWWB8ZOZz9GRAr3Uc4mHP33SviL8ntTnNqM8unrOx5Ky_AKxadMLnEt1s3bS_AJsj5unz8UQT4yhq2JUD5jRkQtwWYZeOAsZFb0l7S60ecMG6ucxjz0Vn9tzr8oVhI7Te7MN32isi-MqboBgfzRUwNiZFHnoilxU_vx8leZca1zBOgWhO9N_nZ0mzGwoahRuFBWOeeWn0AH5IoI10w5uK3Cm1fJ7vB9RkBZdhYME.&box_client_name=box-content-preview&box_client_version=2.78.1)

## Edge Ports, Port Fast Ports

*In the Network given below when the PC's boot up they might start in less than 30seconds and request an IP address from the DHCP server but since the STP will be in convergence the ports might be in Blocking state hence the PC might not receive an IP address as the DHCP request from the PC would be dropped*

![](https://github.com/SxNade/P4ck3t/blob/main/pimages/2021-09-13_00-16.png)

**For the same reason the Ports connected directly to these Devices {PC's etc} will be configured as Port Fast Ports {Cisco} / Edge Ports {other vendors}**


 - You should not enable Port Fast on link between switches Because this can introduce loops in your topology
 - Port Fast Ports should only be enabled on Access Ports {not on Trunk Ports}
 - Port Fast ports / Edge Ports immediately transition to the forwarding state
 - **For some reason if a BPDU is recevied on port it immediately goes to Blocking State, this will help to prevent introducing loops in the network {For example someone accidentally plugs in a switch on Port Fast Port}**

## Path Cost

 - is incremented on per link basis
 - Is calculated from the sum total of port costs
 - Port Costs have Default values 

![](https://i.ytimg.com/vi/QABhcoLUmf8/maxresdefault.jpg)

**Chart in accordance with dates**

![](https://2.bp.blogspot.com/-OJpipQtcl08/WdtF8GDlF5I/AAAAAAAABaY/KT9oRwL1VqsCuzvfQOB98iL8VklFy_bcgCLcBGAs/s1600/STP_default_port_costs.JPG)

*Ports in STP have specific states*

![](https://github.com/SxNade/P4ck3t/blob/main/pimages/2021-09-13_01-20.png)

**A Quick note is that we should always use RPVST+ over PVST since it offers faster covergence which means more network performance**

*`RPVST and PVST are backward compatible`*

[**`Reference`**](https://www.cisco.com/c/en/us/support/docs/lan-switching/spanning-tree-protocol/24062-146.html)

![](https://github.com/SxNade/P4ck3t/blob/main/pimages/2021-09-13_01-38.png)

**STP Comparison**

![](https://github.com/SxNade/P4ck3t/blob/main/pimages/2021-09-14_00-11.png)

# CDP 

`CDP`: *Cisco Discovery Protocol*

`LLDP` {industry standard}: *Link Layer Discovery protocol*

**Both of these Run at Layer2 in the OSI model to see how devices are connected together**

**command**: `show cdp neighbors` {to see connected devices}

*Also Noted that CDP would only show Directly connected Devices by Default*

**command**: `show cdp neighbor details` {to see more details about the connected devices}

*Note that CDP will still work if no IP address is configured on a directly connected neighbouring device because CDP does not rely on IP*

**we can Get Details about a specific device by specifying its Device-ID**

**command**: `sh cdp entry Device-ID`

*we can also use a Mix of Protocols to MAP out the Devices in the Network, we can ssh to a Device which we discover First using CDP and then use LLDP on that Device to look for other devices connected to it!*

**command**: `sh lldp neighbors`

*Again for more details we can run the Following*

**command**: `sh lldp neighbors detail`

## Disabling CDP

*as CDP spits out a wealth of juicy information about the devices we might need to disable it entirely or on specific interface for better security of the network*

**Disabling CDP entirely**

`no cdp run` {disables CDP entirely on a device}

*Also note that by Default CDP sends packet every 60 seconds to look for devices so it might take a delay of 60 seconds for a Device to show up in CDP neighbors*

*After CDP is disabled some Devices might take 180 seconds to disappear from the List*

**Disabling CDP on a Specific Interface**

`conf t`

`int Gig{interface-name}`

`no cdp enable`

`end`

*A lot of companies usually disable CDP on internet connected Interfaces*


## LLDP

*Link local discovery protocol*

**LLDP can be enabled on a device globally {on all interfaces} as Follows**

`en`

`conf t`

`lldp run`

`end`

*commands to check for neighboring devices etc.. still remain similar to those used in cdp*

`sh lldp neigbhors` {to looks for devices near by}

`sh lldp neigbhor detail` {for more details}

**We can uncover more option / commands with the built in help system in IOS using ?**

# Port Security

*Port security controls how many addresses can be learned on a single switch port, this feature is implemented on a port-by-port basis. A typical user just uses a single MAC address, Exceptions to this may be a virtual machine or two that might use a different MAC address or if there is an IP phone with a built-in switch which may also account for additional MAC addresses*

**with port security we can also implement minimal level of authentication on the basis of MAC addresses for example we can allow access on a port from only specific MAC addresses and also Deny specific MAC address so basically we can setup white,Black lists for MAC addresses**

## Learning MAC addresses

**Static**
 - Statically configure MAC addresses that are allowed
 - Pros: A lot of control
 - Con: manually work out MAC of devices

**Dynamic Learning**
 - we can specify the number of MAC addresses to be permitted on a port
 - for example if we specify 2 MAC addresses, After the switch has learned 2 MAC addresses it will not permit any other MAC addresses

 - A thing with Dynamic learning is that when the port Goes down or when the switch is rebooted the MAC addresses learned are removed and new MAC addresses are learnt when the port comes up again

 - **Aging Interval**
     - By setting a Aging interval we can make the switch forget the Dynamic MAC addresses after a period of time and learn again

**Sticky Learning**
 - Allows us to automatically add a MAC address to the running configuration of the switch
 - Then we can save the running configuration to the start-up configuration

## Testing Basic Port Security

*Below is a simple network of two connected routers with a switch in between them, we can ping both routers from each end and the switch has dynamically learned the MAC address of the Routers on each port but we don't have any port-security mechanism enabled yet*

![](https://github.com/SxNade/P4ck3t/blob/main/pimages/topology.png)

*we can check the CAM table etc..*

![](https://github.com/SxNade/P4ck3t/blob/main/pimages/ps-sw.png)

*Now we will try adding port Security to the Gig/1 interface of Switch {The port needs to be a access port}*

![](https://github.com/SxNade/P4ck3t/blob/main/pimages/enable-ports.png)

*By Default port security is limiting MAC adddresses on a port to 1 , we can run show port-security address for more info*

![](https://github.com/SxNade/P4ck3t/blob/main/pimages/portS-mac.png)

*Also note that the MAC address now shown here is the only one that will be allowed on the port, we can test this by changing the MAC address on Gi0/0/0 interface of R1*

![](https://github.com/SxNade/P4ck3t/blob/main/pimages/portS-down.png)

*Since we changed the MAC address that was permitted the port went down and we can also see the Count of Security Violation is set to 1, A last seen MAC is also mentioned and this is the MAC that caused the Security Violation {Port went down!}*

**we can reachange the MAC address back to the normal one and see if the port Goes up again**

![](https://github.com/SxNade/P4ck3t/blob/main/pimages/portS-up.png)

## Port Security with Specific MAC address Manually 

*Now we will configure port security on the second interface of the switch , we will specify the MAC address manually as well as some of other settings*

*we specify a single MAC address on second interface, the Action we specify is shutdown {is Default}*

```
S1(config)#int Gi
S1(config)#int GigabitEthernet 0/2
S1(config-if)#switc
S1(config-if)#switchport mo
S1(config-if)#switchport mode acc
S1(config-if)#switchport mode access 
S1(config-if)#switc
S1(config-if)#switchport po
S1(config-if)#switchport port-security m
S1(config-if)#switchport port-security max
S1(config-if)#switchport port-security maximum 1
S1(config-if)#switc
S1(config-if)#switchport po
S1(config-if)#switchport port-security ma
S1(config-if)#switchport port-security mac
S1(config-if)#switchport port-security mac-address 0023.3300.0003
Total secure mac-addresses on interface GigabitEthernet0/2 has reached maximum limit.
S1(config-if)#switchport port-security vio
S1(config-if)#switchport port-security violation shutdo
S1(config-if)#switchport port-security violation shutdown 
S1(config-if)#switchport port-security
S1(config-if)#end
S1#
%SYS-5-CONFIG_I: Configured from 
```
**Gives a Fking limit error for no reason but we can instead set a limit of 2 may be and then specify a MAC** 

*TO fix this we first shut down the interface since switch automaticall was learning a MAC from that interface of R2 and full filling the limit of 1 before we could even specify a MAC manually :)*

```
S1>en
S1#conf t
Enter configuration commands, one per line.  End with CNTL/Z.
S1(config)#int GI
S1(config)#int GIgabitEthernet 0/2
S1(config-if)#switch
S1(config-if)#switchport po
S1(config-if)#switchport port-security mac
S1(config-if)#switchport port-security mac-address 0023.3300.0003
S1(config-if)#no shut

S1(config-if)#
%LINK-5-CHANGED: Interface GigabitEthernet0/2, changed state to up

%LINEPROTO-5-UPDOWN: Line protocol on Interface GigabitEthernet0/2, changed state to up

%LINK-5-CHANGED: Interface GigabitEthernet0/2, changed state to administratively down

%LINEPROTO-5-UPDOWN: Line protocol on Interface GigabitEthernet0/2, changed state to down

S1(config-if)#end
S1#
%SYS-5-CONFIG_I: Configured from console by console

S1#show port
S1#show port-security int Gi
S1#show port-security int GigabitEthernet 0/2
Port Security              : Enabled
Port Status                : Secure-shutdown
Violation Mode             : Shutdown
Aging Time                 : 0 mins
Aging Type                 : Absolute
SecureStatic Address Aging : Disabled
Maximum MAC Addresses      : 1
Total MAC Addresses        : 1
Configured MAC Addresses   : 1
Sticky MAC Addresses       : 0
Last Source Address:Vlan   : 000A.4129.8A01:1
Security Violation Count   : 1

S1#
```

**Now the interface went Down because the MAC of R2 is different than the one we have specified as allowed manually :)**

*After this we can rechange the MAC of R2 and shut-noshut the interface again to make R2 access the switch port again*

## Port Security Sticky

*Suppose we have a 52 port switch and we need to configure 2 MAC addresses on each port, it can be tiring and here we can use the sticky option which will allow the switch to learn the MAC addresses initially and then save them to the config automatically then we can use `wr` to save everything*

**However it is important that we control the initial state of the network that is initially we see that what devices are going to be connected etc..**

*Here we configured the Max MAC addresses to be 2 and also we configured `Sticky` :)*

![](https://github.com/SxNade/P4ck3t/blob/main/pimages/port-security-sticky.png)

*Also if we see the running config, we will spot that one command was automatically run after the Sticky command to add the MAC address to the configuration*


## CAM Table Overflow Attack

*A user may try sending thounsands of frames into the network with a different bogus MAC address for each frame , as the user tries to exhaust the limits of the dynamic MAC address table on the switch it might cause the switch to forward all frames to all ports within a VLAN so that the attacker can begin to sniff all the packets, this is reffered to as CAM table overflow attack. `Content-addressable memory (**CAM**)` is a fancy way to refer to the MAC address table on the switch*


# Switchports Versus Routed Ports

*on a `switch` // switch ports can-not be directly allocated IP addresses since they are Layer2 interfaces  but we can have something called the **SVI** {Switched virtual interface such as VLAN1}*

*Routed Ports or ports on a Router can Directly be allocated an IP address*

## Inter-VLAN Routing

we can run the Following commands to enable Inter-VLAN Routing on a Switch

 - `en`
 - `conf t`
 - `ip routing`
 - `end`


*On The Routers in Different VLANs we need to disable IP Routing and set the VLAN Interfaces as Default Gateways on Routers*

 - `en`
 - `conf t`
 - `no ip routing`
 - `ip default-gateway <VLAN-IP> <SUBNET-MASK>`
 - `end`

# IP Routing

`from google` IP Routing is an umbrella term for the set of protocols that determine the path that data follows in order to travel across multiple networks from its source to its destination. 

## Routed Protocol vs Routing Protocol

`Routed Protocol` 
     - carries user Data 
     - eg:IPv4,IPv6
     - each router making independent decision in determining path
     - Routed protocols are independent of each other
     
`Routing Protocols`
     - Examples: EIGRP,OSPF,RIP,ISIS,BGP
     - used by routers to communicate information about networks
     - determine the best route between networks
     - These Different Routing Protocols will use different parameters in determining the best path 
     
## Static VS Dynamic Routing

`Static Routes`
     - Administrator manually enters route
     - no over head on network that might unnecessarily consume bandwidth
     - Manual update is required when there are changes in topology
     
`Dynamic Routes`
     - uses a Routing protocol
     - Automatically adjust Routes based on topology or traffic changes
     - Routers exchange network information with each other 
     
## How Routers Determine the Best Route

`Static` - Decided by administrator

`RIP` - Hop Count

`OSPF` - Bandwidth 

`EIGRP` - Bandwidth + Delay

![](https://github.com/SxNade/P4ck3t/blob/main/pimages/2021-09-20_08-24.png)

**Today the protocols most used are OSPF or EIGRP**

## AS IGPs and EGPs

`AS` {**Autonomous System**}:Is a group of networks under a single administrative domain, such as of a big company

`IGPs` {**Interior/Internal Gateway protocol**}: such as RIP,EIGRP,OSPF within an AS

`EGPs` {**Exterior/External Gateway Routing protocols**}: used between AS's such as BGP {Border Gateway protocol}

### **Autonomous System Numbers**

 - within an AS no need to register or apply for an AS number
 - when communicating onto internet apply for AS number
 - Public Autonomous System Number
 - Private Autonomous System Number

## Types of Routing Protocols

### Distance Vector

 - Routing by Rumor
 - Determine the direction and distance to destination
 - Easy to configure
 - very limited visibility
 - RIP is an example
 - uses the Bellman-Ford algorithm to calculate the path
 - Routers advertise routes as a vector if distance and direction
     - Direction: `next hop address`
     - Distance: `uses a metric such as hop count`

### Link State Routing Protocol

 - visibility of entire network (or area)
 - can make a much more informed decision about how to get to the destination network
 - Example is OSPF and IS-IS
 - Each router originates information about itself, its directly connected links and the state of those links
 - uses an algorithm called `shortest path First` (SPF)
 - Every Router constructs a map of the connectivity to a netwwork in the form of a graph
 - could be Difficult to configure
 - Require more memory and processing power

### Advance Distance Vector

 - EIGRP {**Enhanced Gateway routing protcol**} `hybrid routing protocol with combined elements of both distance vector and link state into a single routing protocol`
 - In theory it {EIGRP} takes best of both combined into a single routing protocol and gives you the power of link state with ease of distance vector
 - Con of EIGRP is that it works only on Cisco and for backward compatibility we should use OSPF

## Administrative Distance

 - Believability factor of a route
 - when multiple routing protocols are configured on a router and are trying to put routing information in RIB {Routing information Base}
 - who will the Router believe????

 - Administrative Distance is used as a tie breaker to determine which routing protocol to believe!
 - Technically the Routing protocol with lowest is more believable and its information is inserted into RIB `Routing information Base`

### Administrative Distance Values

 - a Directly connected interface has a believability factor of `0` so it holds prefrence over eveything
 - `Static Route`: **1**
 - `Internal EIGRP`: **90**
 - `OSPF`: **110**
 - `RIP`: **120**
 - `unknown`: **255**

**AD Values of other protocols**

 - `IBGP`: 200
 - `EBGP`: 20
 - `ISIS`: 115

#### Example of Conflicting Route Decision

![](https://github.com/SxNade/P4ck3t/blob/main/pimages/2021-09-20_11-46.png)

*In the image above we can see that the Router will take the EIGRP route over RIP but also note that RIP route is still stored in the rip database and if at any time if EIGRP link went down it will follow the RIP route and when at any point the EIGRP link comes up the router will again follow it*

## Classful routing protocols

 - these protocols donot advertise subnet mask
 - consistency of subnet mask assumed ie: routers assume that all are using same mask as they are
 - Example: RIP version1 
 - Hence not used in networks today

## Classless routing protocols

 - Do advertise subnet mask
 - Support `VLSM` {**Variable lenght subnet mask**}
 - Summary Routes can also be manually configured
 - Examples: OSPF,EIGRP,RIP-version2,ISIS

## Administrative Distance VS Mask length

