# P4ck3t

Networking ???   **updated everyday!!**

- [Binary and Decimal Conversions](#binary-and-decimal)

- [Hexadecimal conversions](#hexadecimal)

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

## Special addresses [IPv4]

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
  - allows us to use VLSM {variable lenght subnet masks}
  - 10.0.0.0/8 Rather than 10.0.0.0 255.0.0.0


# Subnetting

*we will see primarly see **"Quick Binary"** method*


