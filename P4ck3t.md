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
 

