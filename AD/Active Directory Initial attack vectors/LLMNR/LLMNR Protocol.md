What is LLMNR ?
- Used to identify  hosts when DNS fails to do so
- Previously NBT-NS
- Key Flaw is that the services utilize a user's username and NTLMv2 hash when appropriately respond to


### LLMNR Protocol

- Link-Local Multicast Name Resolution (LLMNR) is a protocol used in Microsoft Windows operating systems to resolve the NetBIOS (Network Basic Input/Output System) names of neighboring computers on the same subnet when DNS name resolution fails. It is primarily used in scenarios where no DNS server is available or when DNS queries fail due to network issues.

Here's a more detailed explanation of how LLMNR works:

1. **Name Resolution**: When a Windows machine needs to resolve the name of another machine on the same subnet, it first tries traditional DNS resolution. If DNS resolution fails, the machine then attempts to resolve the name using LLMNR.
    
2. **Multicast Query**: The querying machine sends out a multicast LLMNR query to all machines on the local subnet, asking if any machine knows the IP address corresponding to the requested name.
    
3. **Response**: If a machine on the subnet has the requested name in its NetBIOS name cache, it responds with its IP address.
    
4. **Name Collision Avoidance**: Before responding, a machine that has the requested name checks if another machine has already responded with the same name to avoid name collision.
    
5. **Resolution Timeout**: If no response is received within a certain timeout period, the querying machine may retry the LLMNR query or use other means to resolve the name, such as broadcasting a NetBIOS Name Service (NBNS) query or using a HOSTS file.
    

LLMNR operates over UDP (User Datagram Protocol) on port 5355. It is designed to provide name resolution services for hosts on the same local link (subnet), and it does not traverse routers, which helps contain its scope to the local network segment.

While LLMNR can be useful in certain scenarios, it also introduces security risks, such as the possibility of LLMNR poisoning attacks where malicious actors respond to LLMNR queries with false information, leading to potential security breaches.

