# Routing
```bash
ip route add <network\_ip>/<cidr> via <gateway\_ip>
```

# Egress checking
https://github.com/stufus/egresscheck-framework
```bash
git clone https://github.com/stufus/egresscheck-framework.git
cd egresscheck-framework
./ecf.py
set TARGETIP <localmachine>
set SOURCEIP <compromised box>
set PORTS <ports>
set PROTOCOL ALL
get
generate <payload type>
```
listen with wireshark / tcpdump **(on relevant interface!!)**