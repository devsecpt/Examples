#! /usr/bin/env python3
import sys
if len(sys.argv) != 2:
    print("Usage: arpscan <net>\n  eg: arpscan 192.168.1.0/24")
    sys.exit(1)
from warnings import filterwarnings
filterwarnings("ignore")
from scapy.all import srp, Ether, ARP, conf
conf.verb = 0
ans, unans = srp(Ether(dst="ff:ff:ff:ff:ff:ff") / ARP(pdst=sys.argv[1]),
                 timeout=2)

print("MAC\t\t\tIP")
for snd,rcv in ans:
    print(rcv.sprintf("%Ether.src%\t%ARP.psrc%"))
