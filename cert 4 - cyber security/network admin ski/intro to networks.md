# Introduction to Networks

## 2 Basic Switch & End Device Configuration
## 2.2 IOS Navigation

### Primary Command Modes

As a security feature, CISCO IOS software separates management access into 2 command modes:
* User EXEC mode - has limited capabilities, is useful for basic operations and allows only limited number of basic monitoring commands, but does not allow the execution of any commands that might change the config of the device. The user EXEC mode is identified by the ">" symbol.

```
Switch>
Router>
```

* Privileged EXEC mode - used to execute and access higher configuration modes like global configuration mode, and is identified by the "#" symbol.

```
Switch#
Router#
```

### Configuration Mode & Sub-configuration Modes

The global configuration mode is used to configure the device, and any CLI configuration changes made affect the operation of the device as a whole. Global config mode is identified by a prompt that ends with (config)# 

```
Switch(config)#
Router(config)#
```

Global configuration mode is accessed before other specific configuration modes, and the user can enter different sub-configuration modes accordingly. Each of these modes allows the configuration of a particular part or function of the IOS device. 
Two common sub-configuration modes include:
* Line Configuration Mode - (config-line)# - used to configure console, SSH, telnet or AUX access
* Interface Configuration Mode - (config-if)# - used to configure a switch port or router network interface

### Navigate between IOS Modes

| Command                | Description                                                                                 |
| ---------------------- | ------------------------------------------------------------------------------------------- |
| **enable**             | To move from user EXEC to privileged EXEC mode                                              |
| **disable**            | Used to return to user EXEC mode from privileged EXEC mode                                  |
| **configure terminal** | Used to move in and out of global config mode from privileged EXEC mode                     |
| **exit**               | To return to privileged EXEC mode from global config mode                                   |
| **line**               | To enter line sub-config mode, use **line** followed by the management line type and number |
| **end**                | To move from any sub-config mode to privileged EXEC mode. Ctrl + Z can also be used                                                                                            |


## 2.3 The Command Structure

A Cisco IOS device supports many commands, and each IOS command has a specific format, or syntax and can only be executed in the appropriate mode. 

The general syntax for a command, is the command followed by any appropriate keywords or arguments.

![[Screenshot 2024-03-04 183733.png]]

A command might require one or more arguments. To determine the keywords and arguments required for a command, refer to the command syntax, which provides the pattern, or format that must be used when entering a command. 

| Convention   | Description                                                                     |
| ------------ | ------------------------------------------------------------------------------- |
| **boldface** | Boldface text indicates commands and keywords that you enter literally as shown |
| *italics*      | Italic text indicates arguments for which you supply values                     |
| [x]          | Square brackets indicate an option element (keyword or argument)                |
| {x}          | Braces indicate a required element (keyword or argument)                        |
| [x {y ! z}]  | Braces and vertical lines within square brackets indicate a required choice within an optional element. Spaces are used to clearly delineate parts of the command                                                                                 |

**ping** *ip-address* - The command is **ping** and the user-defined argument is the *ip-address* of the destination device.

### Hot Keys & Shortcuts

The table lists keystrokes to enhance command line editing

| **Keystroke**                          | **Description**                                                                             |
| -------------------------------------- | ------------------------------------------------------------------------------------------- |
| **Tab**                                | Completes a partial command name entry.                                                     |
| **Backspace**                          | Erases the character to the left of the cursor.                                             |
| **Ctrl+D**                             | Erases the character at the cursor.                                                         |
| **Ctrl+K**                             | Erases all characters from the cursor to the end of the command line.                       |
| **Esc D**                              | Erases all characters from the cursor to the end of the word.                               |
| **Ctrl+U** or **Ctrl+X**               | Erases all characters from the cursor back to the beginning of the command line.            |
| **Ctrl+W**                             | Erases the word to the left of the cursor.                                                  |
| **Ctrl+A**                             | Moves the cursor to the beginning of the line.                                              |
| **Left Arrow**or **Ctrl+B**            | Moves the cursor one character to the left.                                                 |
| **Esc B**                              | Moves the cursor back one word to the left.                                                 |
| **Esc F**                              | Moves the cursor forward one word to the right.                                             |
| **Right Arrow**or **Ctrl+F**           | Moves the cursor one character to the right.                                                |
| **Ctrl+E**                             | Moves the cursor to the end of command line.                                                |
| **Up Arrow**or **Ctrl+P**              | Recalls the previous command in the history buffer, beginning with the most recent command. |
| **Down Arrow**or **Ctrl+N**            | Goes to the next line in the the history buffer.                                            |
| **Ctrl+R** or **Ctrl+I** or **Ctrl+L** | Redisplays the system prompt and command line after a con                                   |

This table lists commands used to exit out of an operation.

| **Keystroke**    | **Description**                                                                                                                                         |
| ---------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Ctrl-C**       | When in any configuration mode, ends the configuration mode and returns to privileged EXEC mode. When in setup mode, aborts back to the command prompt. |
| **Ctrl-Z**       | When in any configuration mode, ends the configuration mode and returns to privileged EXEC mode.                                                        |
| **Ctrl-Shift-6** | All-purpose break sequence used to abort DNS lookups, traceroutes, pings, etc.                                                                          |

## 2.4 Basic Device Configuration

### Device Names

The default name should be changed to something more descriptive. By choosing names wisely, it is easier to remember, document, and identify network devices. Here are some important naming guidelines for hosts:

- Start with a letter
- Contain no spaces
- End with a letter or digit
- Use only letters, digits, and dashes
- Be less than 64 characters in length

From global configuration mode, enter the command **hostname** followed by the name of the switch and press **Enter**. Notice the change in the command prompt name.

```
Switch# **configure terminal** 
Switch(config)# **hostname Sw-Floor-1** 
Sw-Floor-1(config)#
```
### Password Guidelines

Cisco IOS can be configured to use hierarchical mode passwords to allow different access privileges to a network device. 

All networking devices should limit administrative access by securing privileged EXEC, user EXEC and remote Telnet access with passwords, and all passwords should be encrypted. 

When choosing passwords, use strong passwords that are not easily guessed. There are some key points to consider when choosing passwords:

- Use passwords that are more than eight characters in length.
- Use a combination of upper and lowercase letters, numbers, special characters, and/or numeric sequences.
- Avoid using the same password for all devices.
- Do not use common words because they are easily guessed.

### Configure Passwords

When initially connecting to a device, the user is in user EXEC mode. This mode is secured using the console.

To secure user EXEC mode access, enter line console configuration mode using the **line console 0** global configuration command. The zero is used to represent the first (and in most cases the only) console interface. Then specify the user EXEC mode password using the **password** *password* command. Finally, enable user EXEC access using the **login** command.

```
Sw-Floor-1# **configure terminal**
Sw-Floor-1(config)# **line console 0**
Sw-Floor-1(config-line)# **password cisco**
Sw-Floor-1(config-line)# **login**
Sw-Floor-1(config-line)# **end**
Sw-Floor-1#
```

Console access will now require a password before allowing access to the user EXEC mode. 

To have administrator access to all IOS commands, including configuring a device, the user must gain privileged EXEC mode access. It is the most important access method because it provides complete access to the device. 

To secure privileged EXEC access, use the **enable secret** *password* global config command.

```
Sw-Floor-1# **configure terminal**
Sw-Floor-1(config)# **enable secret class**
Sw-Floor-1(config)# **exit**
Sw-Floor-1#
```

Virtual terminal (VTY) lines enable remote access using Telnet or SSH to the device. Many Cisco switches support up to 16 VTY lines that are numbered 0 to 15.

To secure VTY lines, enter line VTY mode using the **line vty 0 15** global config command. Next, specify the VTY password using the **password** _password_ command. Lastly, enable VTY access using the **login** command.

An example of securing the VTY lines on a switch is shown.

```
Sw-Floor-1# configure terminal
Sw-Floor-1(config)# line vty 0 15
Sw-Floor-1(config-line)# password cisco 
Sw-Floor-1(config-line)# login 
Sw-Floor-1(config-line)# end
Sw-Floor-1#
```

### Encrypt Passwords

The startup-config and running-config files display most passwords in plaintext. This is a security threat because anyone can discover the passwords if they have access to these files. 

To encrypt all plaintext passwords, use the **service password-encryption** global config command.

```
Sw-Floor-1# **configure terminal**
Sw-Floor-1(config)# **service password-encryption**
Sw-Floor-1(config)#
```

The command applies weak encryption to all unencrypted passwords. This encryption applies only to passwords in the configuration file, not to passwords as they are sent over the network. The purpose of this command is to keep unauthorised individuals from viewing passwords in the configuration file.

Use the **show running-config** command to verify that passwords are now encrypted.

```
Sw-Floor-1(config)# **end**
Sw-Floor-1# **show running-config**
!
(Output omitted)
!
line con 0
password 7 094F471A1A0A
login
!
line vty 0 4
 password 7 094F471A1A0A
 login
line vty 5 15
 password 7 094F471A1A0A
 login
!
!
end
```

### Banner Messages

To create a banner message of the day on a network device, use the **banner motd #** _the message of the day_ **#** global config command. The “#” in the command syntax is called the delimiting character. It is entered before and after the message. The delimiting character can be any character as long as it does not occur in the message. For this reason, symbols such as the "#" are often used.

```
Sw-Floor-1# **configure terminal** 
Sw-Floor-1(config)# **banner motd #Authorized Access Only#**
```

## 2.5 Save Configurations

There are two system files that store the device configuration:

* **startup-config** - this is the saved configuration file that is stored in NVRAM. It contains all the commands that will be used by the device upon startup or reboot. Flash does not lose its contents when the device is powered off.
* **running-config** - this is stored in RAM and reflects the current configuration. Modifying a running configuration affects the operation of a Cisco device immediately. RAM is volatile and loses all of its content when the device is powered off or restarted.

The **show running-config** privileged EXEC mode command is used to view the running config. 

```
Sw-Floor-1# **show running-config** 
Building configuration... 
Current configuration : 1351 bytes 
! 
! Last configuration change at 00:01:20 UTC Mon Mar 1 1993 
! 
version 15.0 
no service pad 
service timestamps debug datetime msec 
service timestamps log datetime msec 
service password-encryption 
! 
hostname Sw-Floor-1 
! 
(output omitted)
```

To view the startup configuration file, use the **show startup-config** privileged EXEC command. 

If power to the device is lost, or if the device is restarted, all configuration changes will be lost unless they have been saved. To save changes made to the running configuration to the startup configuration file, use **copy running-config startup-config** command.

If changes made to the running config do not have the desired effect and the running-config has not yet been saved, you can restore the device to its previous configuration. Remove the changed commands individually, or reload the device using the **reload** privileged EXEC mode command to restore the startup-config.

The downside to using the **reload** command to remove an unsaved running config is the brief amount of time the device will be offline, causing network downtime.

## 2.6 Ports & Addresses

### IP Addresses

The use of IP addresses is the primary means of enabling devices to locate one another and establish end-to-end communication on the internet. Each end device on a network must be configured with an IP address.

The structure of an IPv4 address is called dotted decimal notation and is represented by four decimal numbers between 0 and 255. IPv4 addresses are assigned to individual devices connected to a network.

IPv6 addresses are 128 bits in length and written as a string of hexadecimal values. Every four bits is represented by a single hexadecimal digit; for a total of 32 hexadecimal values. Groups of four hexadecimal digits are separated by a colon (:) . IPv6 addresses are not case-sensitive and can be written in either lowercase or uppercase.

## 3 Protocols & Models

## 3.1 The Rules

### Communications Fundamentals & Protocols

All communication methods have the following three elements in common:

* **Message source (sender)** - People or electronic devices that need to send a message to other individuals or devices.
* **Message Destination (receiver)** - Destination receives the message and interprets it.
* **Channel** - Consists of the media that provides the pathway over which the message travels from source to destination.

Protocols must account for the following requirements:

* **An identified sender & receiver**
* **Common language & grammar**
* **Speed & timing of delivery**
* **Confirmation or acknowledgment requirements**

### Network Protocol Requirements

Common computer protocols:

* Message encoding
* Message formatting & encapsulation
* Message size
* Message timing
* Message delivery options

### Message Encoding

Encoding is the process of converting information into another acceptable form for transmission. Decoding reverses this process to interpret the information. 

### Message Formatting & Encapsulation

When a message is sent from source to destination, it must use a specific format or structure. Message formats depend on the type of message and the channel that is used to deliver the message. 

The process of placing one message format inside another message format is encapsulation. De-encapsulation occurs when the process is reversed.

### Message Timing

Message timing is very important in network communications and includes:

* **Flow Control** - Process of managing the rate of data transmission. Flow control defines how much information can be sent and the speed at which it can be delivered.
* **Response Timeout** - Hosts on the network use network protocols that specify how long to wait for responses and what action to take if a response timeout occurs.
* **Access Method** - Determines when someone can send a message. 

### Message Delivery Options

* **Unicast** - Information is being transmitted to a single end device.
* **Multicast** - Information is being transmitted to one more end devices.
* **Broadcast** - Information is being transmitted to all end devices.

![[Screenshot 2024-03-08 122418.png]]


## 3.2 Protocols

Network protocols define a common format and set of rules for exchanging messages between devices, and are implemented by end devices and intermediary devices in software, hardware or both. Each network protocol has its own function, formation and rules for communications. 

### Network Protocol Overview

| **Protocol Type**                    | **Description**                                                                                                                                                                                                   |
| ------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Network Communications Protocols** | Protocols enable two or more devices to communicate over one or more networks.<br>eg: Ethernet - involves multiple protocols IP, Transmission Control Protocol (TCP), HTTP                                        |
| **Network Security Protocols**       | Protocols secure data to provide authentication, data integrity and data encryption. <br>eg: SSH, SSL & TLS                                                                                                       |
| **Routing Protocols**                | Protocols enable routers to exchange route information, compare path information and then select the best path to the destination network. <br>eg: Open Shortest Path First (OSPF), Border Gateway Protocol (BGP) |
| **Service Discovery Protocols**      | Protocols are used for the automatic detection of devices or services. <br>eg: DHCP, DNS                                                                                                                          |
### Network Protocol Functions

| **Function**              | **Description**                                                                                                                                                                                                                                          |
| ------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Addressing**            | Identifies the sender and the intended receiver of the message using a defined addressing scheme. <br>eg: Ethernet, IPv4, IPv6                                                                                                                           |
| **Reliability**           | Provides a guaranteed delivery mechanism in case messages are lost or corrupted in transit. TCP provides guaranteed delivery.                                                                                                                            |
| **Flow Control**          | Ensures that data flows at an efficient rate between two communicating devices. TCP provides flow control services.                                                                                                                                      |
| **Sequencing**            | Uniquely labels each transmitted segment of data. The receiving device uses the sequencing information to reassemble the information correctly, and is useful if the data segments are lost, or received out-of-order. TCP provides sequencing services. |
| **Error Detection**       | Used to determine if the data became corrupted during transmission. <br>eg: Ethernet, IPv4, IPv6, TCP                                                                                                                                                    |
| **Application Interface** | Contains information used for process-to-process communications between network applications. <br>eg: HTTP & HTTPS are used to communicate between client and server web processes.                                                                      |

### Network Protocol Suites

A protocol suite is a group of inter-related protocols necessary to perform a communication function.

A protocol stack shows how the individual protocols within a suite are implemented. The protocols are viewed in terms of layers, with each higher-level service depending on the functionality defined by the protocols shown in the lower levels. The lower layers are concerned with moving data over the network and providing services to the upper layers, which are focused on the content of the message being sent.

### Evolution of Protocol Suites

* **Internet Protocol Suite (TCP/IP)** - Is an open standard protocol suite maintained by the Internet Engineering Task Force (IETF).
* **Open Systems Interconnection (OSI)** - OSI protocol included a seven-layer model, the OSI reference model, and categorises the functions of its protocols. The OSI protocols have largely been replaced by TCP/IP.
* **AppleTalk** - Short-lived proprietary protocol suite released by Apple Inc.
* **Novell NetWare** - Short-lived proprietary protocol suite and network operating system developed by Novell Inc.

### TCP/IP Protocol Suite

TCP/IP protocols are available for the application, transport, and internet layers. There are no TCP/IP protocols in the network access layer.

![[Screenshot 2024-03-08 at 2.00.34 pm.png]]


## 4 Physical Layer

The OSI physical layer provides the means to transport the bits that make up a data link layer frame across the network media. This layer accepts a complete frame from the data link layer and encodes it as a series of signals that are transmitted to the local media. The encoded bits that comprise a frame are received by either an end device or an intermediate device.

The physical layer standards address three functional areas:

- Physical Components
- Encoding
- Signaling

### Physical Components

The physical components are the electronic hardware devices, media, and other connectors that transmit the signals that represent the bits. Hardware components such as NICs, interfaces and connectors, cable materials, and cable designs are all specified in standards associated with the physical layer.

### Encoding

Encoding or line encoding is a method of converting a stream of data bits into a predefined "code”. Codes are groupings of bits used to provide a predictable pattern that can be recognized by both the sender and the receiver. In other words, encoding is the method or pattern used to represent digital information.

### Signaling

The physical layer must generate the electrical, optical, or wireless signals that represent the "1" and "0" on the media. The way that bits are represented is called the signaling method. The physical layer standards must define what type of signal represents a "1" and what type of signal represents a "0". This can be as simple as a change in the level of an electrical signal or optical pulse. For example, a long pulse might represent a 1 whereas a short pulse might represent a 0.

### Bandwidth

Data transfer is usually discussed in terms of bandwidth. Bandwidth is the capacity at which a medium can carry data. Digital bandwidth measures the amount of data that can flow from one place to another in a given amount of time. Bandwidth is typically measured in kilobits per second (kbps), megabits per second (Mbps), or gigabits per second (Gbps).

A combination of factors determines the practical bandwidth of a network:

- The properties of the physical media
- The technologies chosen for signaling and detecting network signals

| **Unit of Bandwidth** | **Abbreviation** | **Equivalence**                           |
| --------------------- | ---------------- | ----------------------------------------- |
| Bits per second       | bps              | 1 bps = fundamental unit of bandwidth     |
| Kilobits per second   | Kbps             | 1 Kbps = 1,000 bps = 103 bps              |
| Megabits per second   | Mbps             | 1 Mbps = 1,000,000 bps = 106 bps          |
| Gigabits per second   | Gbps             | 1 Gbps = 1,000,000,000 bps = 109 bps      |
| Terabits per second   | Tbps             | 1 Tbps = 1,000,000,000,000 bps = 1012 bps |
Terms used to measure the quality of bandwidth include:

- Latency
- Throughput
- Goodput

**Latency**

Latency refers to the amount of time, including delays, for data to travel from one given point to another.

**Throughput**

Throughput is the measure of the transfer of bits across the media over a given period of time.

Due to a number of factors, throughput usually does not match the specified bandwidth in physical layer implementations. Throughput is usually lower than the bandwidth. There are many factors that influence throughput:

- The amount of traffic
- The type of traffic
- The latency created by the number of network devices encountered between source and destination

**Goodput***

Goodput is the measure of usable data transferred over a given period of time. Goodput is throughput minus traffic overhead for establishing sessions, acknowledgments, encapsulation, and retransmitted bits. Goodput is always lower than throughput, which is generally lower than the bandwidth.

