# P4ck3t

Networking ???   **updated everyday!!**

___
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

