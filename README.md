# Basic Router Configuration

## Modes in CISCO Router

There are **three modes** in a CISCO router.

1. User EXEC Mode
2. Privilege Mode
3. Global Configuration Mode

### **User EXEC Mode**

When we start or power on any CISCO router this mode will come up first. We can identify this mode by the sign of **>**. This mode is limited to monitoring some commands.

### **Privilege Mode**

From the User EXEC mode we need type the **enable** command to enter into the privilege mode. We can see the running and starting configuration from this mode.

### Global Configuration Mode

In this mode we can configure a CISCO router from scratch. Here we can set passwords, set IP address etc. To enter this mode we need to type

| User Execution Mode | Privilege Mode          | Global Configuration Mode |
| ------------------- | ----------------------- | ------------------------- |
| Router1>            | Router1#                | Router1(config)#          |
| Limited commands    | Administrative Commands | Configuration Commands    |

## Basic Router Configuration

**Enter Privilege Mode**

```bash
Router1>enable                   ==> This is the User Execution Mode
Router1#                         ==> This is the Privilege Mode
```

**Show Router’s RAM Contents**

```bash
Router1#show running-config
```

**Show Router’s NVRAM Contents**

```bash
Router1#show startup-config
```

**Show Router’s Flash Memory Contents**

```bash
Router1#show flash:
```

**Set Hostname**

```bash
hostname router-1
hostname router 1 [This is invalid hostname format]
Note: Hostname will always be written in one word.
```

**Enter Global Configuration Mode**

```bash
Router1#
Router1#configure terminal         ==> This is the Privilege Mode
Enter configuration commands, one per line.  End with CNTL/Z.
Router1(config)#                   ==> This is the Configuration Mode
```

**Enter Sub Configuration Mode**

```bash
Router1(config)#line con 0
Router1(config-line)#              ==> This is the Sub Configuration Mode
```

**Set Password to the User Execution Mode**

```bash
Router1(config)#line con 0
Router1(config-line)#password 123
Router1(config-line)#login
Router1(config-line)#exit
Router1(config)#exit
Router1#

Note: Here we must need to use **login command**, otherwise the user password will not work properly.
```

**Set Password to the Privilege Mode**

```bash
Router1(config)#enable password 456
```

**Set Encrypted Password to the Privilege Mode**

```bash
Router1(config)#enable secret [password]
```

> If we set both enable and secret enable password to a CISCO Router, the secret enable password will work. The power of secret enable password is more than the enable password. When we remove the secret password from the router the enable password will be automatically activated.

**Encrypted all Passwords in a Router**

```bash
Router1(config)#service password-encryption
```

**Copy Router Configuration from RAM to NVRAM**

```bash
**First Way**
============
Router1#copy running-config startup-config
Destination filename [startup-config]?
Building configuration...
[OK]

**Second Way**
===========
Router1#write memory
Building configuration...
[OK]
```

**Erase all the Configuration from NVRAM**

```bash
Router1#write erase
Erasing the nvram filesystem will remove all configuration files! Continue? [confirm]
[OK]
Erase of nvram: complete
%SYS-7-NV_BLOCK_INIT: Initialized the geometry of nvram
```

**Reload the Router**

```bash
Router1#reload
Proceed with reload? [confirm]
```
