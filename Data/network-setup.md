Router0:
    Device Model: 1941
    Hostname: Router


FirstSwitch:
    Device Model: 2960 IOS15
    Hostname: Switch
SecondSwitch:
    Device Model: 2960 IOS15
    Hostname: Switch


Server1:
    Device Model: Server-PT
    IP Address: 168.90.0.4
Server2:
    Device Model: Server-PT
    IP Address: 210.3.14.5
Server3:
    Device Model: Server-PT
    IP Address: 210.3.14.4


PC1:
    Device Model: PC-PT
    IP Address: 168.90.0.3
PC2:
    Device Model: PC-PT
    IP Address: 168.90.0.2
PC3:
    Device Model: PC-PT
    IP Address: 210.3.14.3
PC4:
    Device Model: PC-PT
    IP Address: 168.90.0.5
PC5:
    Device Model: PC-PT
    IP Address: 210.3.14.2

Laptop:
    Device Model: Laptop-PT
    IP Address: 168.90.0.6



DHCP Details:

1) Enabling DHCP for "FirstSwitch" and "SecondSwitch":
    ip dhcp pool (FirstSwitch || SecondSwitch)
    network (168.90.0.0 255.255.0.0 || 210.3.14.0 255.255.255.0)
    default-router (168.90.0.1 || 210.3.14.1)

2) Excluding IP for router interfaces:
    ip dhcp excluded-address 168.90.0.1
    ip dhcp excluded-address 210.3.14.1

3) Configuring router interfaces: 
    interface GigabitEthernet0/0
    ip address 168.90.0.1 255.255.0.0
    interface GigabitEthernet0/1
    ip address 210.3.14.1 255.255.255.0