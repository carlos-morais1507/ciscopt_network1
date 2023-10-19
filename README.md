
# Cisco Packet Tracer Project 1 - Basic Network
**Made by:** Carlos Alberto Morais Junior
**Date:** 10/18/2023

![image](https://github.com/carlos-morais1507/ciscopt_network1/assets/105527392/341d701e-ae5d-416e-a7bb-2814a9436c86)

## Network Components
| Device Name | Interface | Address      | Subnet Mask   | Connecting Device Name | Connecting Device Interface          |
|-------------|-----------|--------------|---------------|-------------------|-----------|
| Router0     | G0/0      | 192.168.1.1  | 255.255.255.0 | Switch0           | G0/1      | 
| Router0              | G0/1      | 192.168.2.1  | 255.255.255.0 | Switch1           | G0/1      |
| Switch0     | F0/1      | 192.168.1.10 | 255.255.255.0 | PC0               | F0/1      |
| Switch0            | F0/2      | 192.168.1.11 | 255.255.255.0 | PC1               | F0/1      |
| Switch1     | F0/1      | 192.168.2.10 | 255.255.255.0 | PC2               | F0/1      |
| Switch1             | F0/2      | 192.168.2.11 | 255.255.255.0 | PC3               | F0/1      |

> All conections were done with **Copper Straight Through** cables

## Router0 Configuration (CLI Commands)
```
Processor board ID FTX152400KS
2 Gigabit Ethernet interfaces
DRAM configuration is 64 bits wide with parity disabled.
255K bytes of non-volatile configuration memory.
249856K bytes of ATA System CompactFlash 0 (Read/Write)

				--- System Configuration Dialog ---
Would you like to enter the initial configuration dialog? [yes/no]: no

Press RETURN to get started!


Router>enable
Router#configure terminal
Enter configuration commands, one per line. End with CNTL/Z.
Router(config)#interface g0/0
Router(config-if)#ip address 192.168.1.1 255.255.255.0
Router(config-if)#no shutdown

Router(config-if)#
%LINK-5-CHANGED: Interface GigabitEthernet0/0, changed state to up

%LINEPROTO-5-UPDOWN: Line protocol on Interface GigabitEthernet0/0,changed state to up

Router(config-if)#exit
Router(config)#interface g0/1
Router(config-if)#ip address 192.168.2.1 255.255.255.0
Router(config-if)#no shutdown
Router(config-if)#

%LINK-5-CHANGED: Interface GigabitEthernet0/1, changed state to up

%LINEPROTO-5-UPDOWN: Line protocol on Interface GigabitEthernet0/1,changed state to up

Router(config-if)#exit
Router(config)#
```
## PCs Configurations (PC0 as example)
![image](https://github.com/carlos-morais1507/ciscopt_network1/assets/105527392/1b59261f-0b68-491f-9fe5-0bf30706640e)

> The same configuration was applied to the other PCs, changing it's IP Adress and Default Gateway following the Network Components table. 

## Simple UDP Tests
Three tests were made:
- One from PC0, passing by Switch0 to Router0;
- One from PC2, passing by Switch1 to Router0;
- One from PC0, passing by Switch0, Router0 and Switch1 to PC2;

This tested the connection of the switches to the router and the connection between switches.


| Status | Source | Destination | Type | Time (sec) | Num |
|---|---|---|---|---|---|
|Successful|PC0|Router0|ICMP|0.000|0|
|Successful|PC2|Router0|ICMP|0.000|1|
|Successful|PC0|Router2|ICMP|0.000|2|
