# EIGRP-CONFIGURATION
EIGRP Configuration on 4 Routers with 2 Switches and PCs in Cisco Packet Tracer Objective: Configure a network using EIGRP on four routers, each connected to two switches, with multiple PCs, ensuring efficient routing and communication

here is a detailed step-by-step guide to configure EIGRP on the routers and ensure connectivity across the network.

#### Devices in the Topology:
1. **Routers:** Router0, Router1, Router2, Router3
2. **Switches:** Switch1, Switch2
3. **PCs:** Multiple PCs connected to each switch

### Step-by-Step Configuration

#### Step 1: Assign IP Addresses
Assign IP addresses to each router interface as shown in the topology. Here is an example for each router:

**Router0:**
```shell
Router0> enable
Router0# configure terminal
Router0(config)# interface gigabitEthernet 0/0
Router0(config-if)# ip address 10.10.10.1 255.255.255.252
Router0(config-if)# no shutdown
Router0(config-if)# exit
Router0(config)# interface gigabitEthernet 0/1
Router0(config-if)# ip address 10.10.10.5 255.255.255.252
Router0(config-if)# no shutdown
Router0(config-if)# exit
Router0(config)# interface gigabitEthernet 0/2
Router0(config-if)# ip address 192.168.1.1 255.255.255.0
Router0(config-if)# no shutdown
Router0(config-if)# exit
Router0(config)# exit
```

**Router1:**
```shell
Router1> enable
Router1# configure terminal
Router1(config)# interface gigabitEthernet 0/0
Router1(config-if)# ip address 10.10.10.2 255.255.255.252
Router1(config-if)# no shutdown
Router1(config-if)# exit
Router1(config)# interface gigabitEthernet 0/1
Router1(config-if)# ip address 10.10.10.9 255.255.255.252
Router1(config-if)# no shutdown
Router1(config-if)# exit
Router1(config)# exit
```

**Router2:**
```shell
Router2> enable
Router2# configure terminal
Router2(config)# interface gigabitEthernet 0/0
Router2(config-if)# ip address 10.10.10.6 255.255.255.252
Router2(config-if)# no shutdown
Router2(config-if)# exit
Router2(config)# interface gigabitEthernet 0/1
Router2(config-if)# ip address 10.10.10.13 255.255.255.252
Router2(config-if)# no shutdown
Router2(config-if)# exit
Router2(config)# exit
```

**Router3:**
```shell
Router3> enable
Router3# configure terminal
Router3(config)# interface gigabitEthernet 0/0
Router3(config-if)# ip address 10.10.10.10 255.255.255.252
Router3(config-if)# no shutdown
Router3(config-if)# exit
Router3(config)# interface gigabitEthernet 0/1
Router3(config-if)# ip address 10.10.10.14 255.255.255.252
Router3(config-if)# no shutdown
Router3(config-if)# exit
Router3(config)# interface gigabitEthernet 0/2
Router3(config-if)# ip address 192.168.2.1 255.255.255.0
Router3(config-if)# no shutdown
Router3(config-if)# exit
Router3(config)# exit
```

#### Step 2: Configure EIGRP on Routers
Enable EIGRP and advertise the networks on each router.

**Router0:**
```shell
Router0> enable
Router0# configure terminal
Router0(config)# router eigrp 1
Router0(config-router)# network 10.10.10.0 0.0.0.3
Router0(config-router)# network 10.10.10.4 0.0.0.3
Router0(config-router)# network 192.168.1.0
Router0(config-router)# no auto-summary
Router0(config-router)# exit
Router0(config)# exit
```

**Router1:**
```shell
Router1> enable
Router1# configure terminal
Router1(config)# router eigrp 1
Router1(config-router)# network 10.10.10.0 0.0.0.3
Router1(config-router)# network 10.10.10.8 0.0.0.3
Router1(config-router)# no auto-summary
Router1(config-router)# exit
Router1(config)# exit
```

**Router2:**
```shell
Router2> enable
Router2# configure terminal
Router2(config)# router eigrp 1
Router2(config-router)# network 10.10.10.4 0.0.0.3
Router2(config-router)# network 10.10.10.12 0.0.0.3
Router2(config-router)# no auto-summary
Router2(config-router)# exit
Router2(config)# exit
```

**Router3:**
```shell
Router3> enable
Router3# configure terminal
Router3(config)# router eigrp 1
Router3(config-router)# network 10.10.10.8 0.0.0.3
Router3(config-router)# network 10.10.10.12 0.0.0.3
Router3(config-router)# network 192.168.2.0
Router3(config-router)# no auto-summary
Router3(config-router)# exit
Router3(config)# exit
```

#### Step 3: Verify Configuration
Use the following commands to verify the EIGRP configuration and connectivity:

**Check EIGRP Neighbors:**
```shell
Router# show ip eigrp neighbors
```

**Check EIGRP Routes:**
```shell
Router# show ip route eigrp
```

**Ping from one network to another:**
```shell
Router# ping 192.168.2.1
```

#### Step 4: Configure PCs with IP Addresses
Assign IP addresses to the PCs connected to the switches as shown in the topology.



By following these steps, you can configure the provided network topology in Cisco Packet Tracer, ensuring efficient routing and connectivity using EIGRP.
