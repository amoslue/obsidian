subnet mask:
![[Pasted image 20240308110252.png]]
what is #OSI model?
![[Pasted image 20240311231327.png]]

#TCP header
![[Pasted image 20240312013751.png]]![[Pasted image 20240312013807.png]]

#ospf package
1. **Hello Packets**: Used for OSPF router discovery and neighbor establishment. Hello packets are sent periodically on all OSPF-enabled interfaces to discover other OSPF routers and form neighbor relationships. They also help in electing the Designated Router (DR) and Backup Designated Router (BDR) on multi-access networks.
    
2. **Database Description (DBD) Packets**: Once neighbors are discovered, DBD packets are exchanged. These packets provide summaries of the sender's Link State Database (LSDB) and are used during the initial synchronization between OSPF neighbors to identify what link-state information is out of date or missing.
    
3. **Link State Request (LSR) Packets**: After exchanging DBD packets, if a router discovers that it is missing some pieces of the LSDB or needs more recent information, it sends LSR packets to request the specific Link State Advertisements (LSAs) that are needed to fill in these gaps.
    
4. **Link State Update (LSU) Packets**: These packets are responses to LSR packets and contain the actual LSAs that were requested. LSUs are used to convey link-state information, which includes information about the topology of the OSPF network. These packets are also used to flood new or changed LSAs to all OSPF routers in an area.
    
5. **Link State Acknowledgment (LSAck) Packets**: Sent to acknowledge the receipt of LSU packets. LSAcks are used to ensure reliable delivery of LSAs within the OSPF network, as OSPF uses a flooding mechanism to distribute LSAs to all routers in an area or the entire autonomous system.
    

Each of these packet types plays a crucial role in the functioning of OSPF, facilitating the dynamic discovery of neighbors, the exchange of routing information, and the maintenance of a consistent view of the network topology among all routers in an OSPF-enabled network.

#TCP 
三次握手
![[Pasted image 20240321214604.png]]
四次挥手
![[Pasted image 20240321214105.png]]![[Pasted image 20240321214156.png]]