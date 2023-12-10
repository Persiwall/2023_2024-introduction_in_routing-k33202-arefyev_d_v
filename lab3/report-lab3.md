SPB:

```
# dec/10/2023 14:42:49 by RouterOS 6.47.9
# software id =
#
#
#
/interface bridge
add name=EoMPLS
add name=Lo0
/interface vpls
add cisco-style=yes cisco-style-id=666 disabled=no l2mtu=1500 mac-address=02:C3:38:F3:1C:51 name=EoMPLS_VPLS remote-peer=10.10.10.5
/interface wireless security-profiles
set [ find default=yes ] supplicant-identity=MikroTik
/routing ospf instance
set [ find default=yes ] name=ospf0 router-id=10.10.10.1
/interface bridge port
add bridge=EoMPLS interface=ether3
add bridge=EoMPLS interface=EoMPLS_VPLS
/ip address
add address=172.31.255.30/30 interface=ether1 network=172.31.255.28
add address=10.10.1.2/30 interface=ether2 network=10.10.1.0
add address=10.10.2.1/30 interface=ether4 network=10.10.2.0
add address=192.168.10.1/24 interface=ether3 network=192.168.10.0
add address=10.10.10.1 interface=Lo0 network=10.10.10.1
/ip dhcp-client
add disabled=no interface=ether2
add disabled=no interface=ether1
/ip route
add distance=1 dst-address=192.168.10.0/24 gateway=ether2
add distance=1 dst-address=192.168.20.0/24 gateway=10.10.10.5
/mpls ldp
set enabled=yes transport-address=10.10.10.1
/mpls ldp interface
add interface=ether2
add interface=ether4
/routing ospf network
add area=backbone
/system identity
set name=R01.SPB
```

MSK:

```
# dec/10/2023 14:50:36 by RouterOS 6.47.9
# software id =
#
#
#
/interface bridge
add name=Lo0
/interface wireless security-profiles
set [ find default=yes ] supplicant-identity=MikroTik
/routing ospf instance
set [ find default=yes ] name=ospf0 router-id=10.10.10.2
/ip address
add address=172.31.255.30/30 interface=ether1 network=172.31.255.28
add address=10.10.1.1/30 interface=ether2 network=10.10.1.0
add address=10.10.3.1/30 interface=ether3 network=10.10.3.0
add address=10.10.10.2 interface=Lo0 network=10.10.10.2
/ip dhcp-client
add disabled=no interface=ether1
/mpls ldp
set enabled=yes transport-address=10.10.10.2
/mpls ldp interface
add interface=ether2
add interface=ether3
/routing ospf network
add area=backbone
/system identity
set name=R01.MSK
```

HKI:

```
# dec/10/2023 15:02:27 by RouterOS 6.47.9
# software id =
#
#
#
/interface bridge
add name=Lo0
/interface wireless security-profiles
set [ find default=yes ] supplicant-identity=MikroTik
/routing ospf instance
set [ find default=yes ] name=ospf0 router-id=10.10.10.3
/ip address
add address=172.31.255.30/30 interface=ether1 network=172.31.255.28
add address=10.10.2.2/30 interface=ether2 network=10.10.2.0
add address=10.10.4.2/30 interface=ether3 network=10.10.4.0
add address=10.10.6.1/30 interface=ether4 network=10.10.6.0
add address=10.10.10.3 interface=Lo0 network=10.10.10.3
/ip dhcp-client
add disabled=no interface=ether1
/mpls ldp
set enabled=yes transport-address=10.10.10.3
/mpls ldp interface
add interface=ether2
add interface=ether3
add interface=ether4
/routing ospf network
add area=backbone
/system identity
set name=R01.HKI
```

LND:

```
# dec/10/2023 15:09:38 by RouterOS 6.47.9
# software id =
#
#
#
/interface bridge
add name=Lo0
/interface wireless security-profiles
set [ find default=yes ] supplicant-identity=MikroTik
/routing ospf instance
set [ find default=yes ] name=ospf0 router-id=10.10.10.4
/ip address
add address=172.31.255.30/30 interface=ether1 network=172.31.255.28
add address=10.10.6.2/30 interface=ether2 network=10.10.6.0
add address=10.10.7.1/30 interface=ether3 network=10.10.7.0
add address=10.10.10.4 interface=Lo0 network=10.10.10.4
/ip dhcp-client
add disabled=no interface=ether1
/mpls ldp
set enabled=yes transport-address=10.10.10.4
/mpls ldp interface
add interface=ether3
add interface=ether2
/routing ospf network
add area=backbone
/system identity
set name=R01.LND
```

LBN:

```
# dec/10/2023 15:17:41 by RouterOS 6.47.9
# software id =
#
#
#
/interface bridge
add name=Lo0
/interface wireless security-profiles
set [ find default=yes ] supplicant-identity=MikroTik
/routing ospf instance
set [ find default=yes ] name=ospf0 router-id=10.10.10.6
/ip address
add address=172.31.255.30/30 interface=ether1 network=172.31.255.28
add address=10.10.3.2/30 interface=ether2 network=10.10.3.0
add address=10.10.4.1/30 interface=ether3 network=10.10.4.0
add address=10.10.5.1/30 interface=ether4 network=10.10.5.0
add address=10.10.10.6 interface=Lo0 network=10.10.10.6
/ip dhcp-client
add disabled=no interface=ether1
/mpls ldp
set enabled=yes transport-address=10.10.10.6
/mpls ldp interface
add interface=ether2
add interface=ether3
add interface=ether4
/routing ospf network
add area=backbone
/system identity
set name=R01.LBN
```

NY:

```
# dec/10/2023 15:29:45 by RouterOS 6.47.9
# software id =
#
#
#
/interface bridge
add name=EoMPLS
add name=Lo0
/interface vpls
add cisco-style=yes cisco-style-id=666 disabled=no l2mtu=1500 mac-address=02:14:45:15:45:BC name=EoMPLS_VPLS remote-peer=10.10.10.1
/interface wireless security-profiles
set [ find default=yes ] supplicant-identity=MikroTik
/routing ospf instance
set [ find default=yes ] name=ospf0 router-id=10.10.10.5
/interface bridge port
add bridge=EoMPLS interface=ether4
add bridge=EoMPLS interface=EoMPLS_VPLS
/ip address
add address=172.31.255.30/30 interface=ether1 network=172.31.255.28
add address=10.10.7.2/30 interface=ether2 network=10.10.7.0
add address=10.10.5.2/30 interface=ether3 network=10.10.5.0
add address=192.168.20.1/24 interface=ether4 network=192.168.20.0
add address=10.10.10.5 interface=Lo0 network=10.10.10.5
/ip dhcp-client
add disabled=no interface=ether1
/ip route
add distance=1 dst-address=192.168.10.0/24 gateway=10.10.10.1
add distance=1 dst-address=192.168.20.0/24 gateway=ether2
/mpls ldp
set enabled=yes transport-address=10.10.10.5
/mpls ldp interface
add interface=ether2
add interface=ether3
/routing ospf network
add area=backbone
/system identity
set name=R01.NY
```
SGI.Prism:

```
# dec/10/2023 15:35:26 by RouterOS 6.47.9
# software id =
#
#
#
/interface wireless security-profiles
set [ find default=yes ] supplicant-identity=MikroTik
/ip address
add address=172.31.255.30/30 interface=ether1 network=172.31.255.28
add address=192.168.20.10/24 interface=ether2 network=192.168.20.0
/ip dhcp-client
add disabled=no interface=ether1
/ip route
add distance=1 gateway=192.168.20.1
/system identity
set name=SGI_Prism
```

PC1:

```
# dec/10/2023 15:40:08 by RouterOS 6.47.9
# software id =
#
#
#
/interface wireless security-profiles
set [ find default=yes ] supplicant-identity=MikroTik
/ip address
add address=172.31.255.30/30 interface=ether1 network=172.31.255.28
add address=192.168.10.10/24 interface=ether2 network=192.168.10.0
/ip dhcp-client
add disabled=no interface=ether1
/ip route

