# Network Delay Measurement using SDN (Mininet + POX)

## Objective
To measure network delay (RTT) between hosts using ping.

## Tools Used
- Mininet
- POX Controller
- OpenFlow

## Topology
- Single switch (3 hosts)
- Multi-switch (2 switches, 4 hosts)

## Commands

Start controller:
python3 pox.py log.level --DEBUG openflow.of_01 forwarding.l2_learning

Run Mininet:
sudo mn --topo single,3 --controller=remote
sudo mn --topo linear,2,2 --controller=remote

Test:
pingall
h1s1 ping h2s2

Check flows:
sudo ovs-ofctl dump-flows s1
sudo ovs-ofctl dump-flows s2

## Screenshots

### POX Controller
![POX](screenshots/pox_controller.png)

### Ping Results
![Ping](screenshots/ping_results.png)

### Flow Table
![Flow](screenshots/flow_table.png)

## Observations
- First packet delay is high
- Later packets are faster
- Multi-hop delay is higher

## Conclusion
Delay increases with number of switches.
