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

*also we know that for subnets the formual is 2^n hence for 29 subnets n ~= 5*

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
      



## Some things to Remember

   - Always use [tab] for command completion
   - ? can be used to ask for help , will also display completed commands or sub-commands
   - by default we enter in user mode **prompt>**
   - en {short for enable} or enable can be used to switch to enabled or privileged mode **prompt#**
   - conf t {short for configure terminal} can be used to switch to global config mode **prompt(config)#**
   - int f0/0 {f0/0 is the interface name} will take us to interface mode **prompt(config-if)#**
   - line console 0 will take us to line mode **prompt(config-line)#**
   - up and down arrow key can be used to go through command history

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

