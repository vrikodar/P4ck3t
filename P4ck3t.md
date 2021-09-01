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
   
- [Lab3 {Subnetting Lab2}](#lab3)

- [Some Questions](#some-questions)
   
   - [Question 1](#question1)
   - [Question 2](#question2)
   - [Question 3](#question3)

- [Cabling and Packet Flows](#cabling-and-packet-flows)

   - [Types of Communication](#types-of-communication)
   - [Difference Between Broadband and Baseband](#difference-between-baseband-and-broadband)
   - [Mac Addresses](#mac-address)

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


