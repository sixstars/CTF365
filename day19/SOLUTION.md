# Day 19
## Solution
Open [Botnet.pcap](./Botnet.pcap) with Wireshark and watch all ICMP traffic, because `ping` relies on ICMP protocol which is so widely used that it might not be blocked by firewalls. (Don't know how to set Wireshark's filtering rule? Just type in `icmp`.) At first sight, the traffic seems to be composed of meaningless nonprintable characters. However, if you watch the entries one by one, you will find that the last changing character in every request/response pair is a character of the flag.
