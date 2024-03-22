## LLMNR Poinsoning

- From a technical perspective, LLMNR poisoning is a type of network attack that exploits the Link-Local Multicast Name Resolution (LLMNR) protocol. Here's a more detailed explanation:
- 
1. **Normal LLMNR Operation**: In a normal network environment, when a computer needs to resolve the name of another computer on the same local subnet, it sends out an LLMNR query as a multicast message to all computers on the subnet.
    
2. **Poisoning the LLMNR Responses**: An attacker can launch an LLMNR poisoning attack by sending malicious responses to LLMNR queries before the legitimate host has a chance to respond. The attacker's response contains a false IP address mapping for the requested hostname.
    
3. **Victim Accepts the Poisoned Response**: If the victim's computer receives the attacker's response before the legitimate response, it may accept the false IP address mapping provided by the attacker. This can lead to the victim's computer sending network traffic intended for the legitimate host to the attacker's machine instead.
    
4. **Potential Consequences**: LLMNR poisoning can be used to conduct various types of attacks, including man-in-the-middle (MITM) attacks, where the attacker intercepts and potentially alters the communication between two parties. This can allow the attacker to capture sensitive information or perform other malicious activities.
    

To mitigate LLMNR poisoning attacks, it is recommended to disable LLMNR where it is not needed, use secure protocols such as DNSSEC, and implement network segmentation and access controls to limit the impact of compromised hosts.

## Easy Manner
- LLMNR poisoning is like someone answering a question for you before you get the chance to ask it. Here's a simple explanation:

Imagine you're in a classroom and you're about to ask a question. Before you can ask, someone else in the room quickly gives you the wrong answer. You might believe it's correct because it was the first response you heard. In computer networks, LLMNR poisoning works similarly. When a computer asks for the address of another computer on the same network, an attacker can quickly respond with a fake address. If the victim's computer accepts the fake address, it can be tricked into sending sensitive information to the attacker's machine instead of the intended destination.