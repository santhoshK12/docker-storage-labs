# Docker Networking Labs – Practical

## Lab 1 – Default Bridge Network

Steps:
- Created two containers: net1 and net2
- Found IP of net1
- Pinged net1 from net2

Command Example:
docker inspect net1
docker exec -it net2 bash
ping -c 3 <net1-ip>

Result:
Ping successful. Containers can communicate using IP.

Learning:
Default bridge allows container communication via IP.

--------------------------------------------------

## Lab 2 – Custom Bridge Network (secure-net)

Steps:
- Created custom network secure-net
- Ran app1 and app2 inside secure-net
- Pinged app1 from app2 using container name

Command Example:
docker network create secure-net
docker run --network secure-net app1
docker run --network secure-net app2
ping app1

Result:
Ping successful using container name.

Learning:
Custom networks support container DNS name resolution.

--------------------------------------------------

## Lab 3 – Network Isolation

Steps:
- Created other-net network
- Ran container isolated in other-net
- Tried ping isolated from secure-net container

Result:
Ping failed (Name resolution failed).

Learning:
Different Docker networks are isolated.

--------------------------------------------------

## Lab 4 – Host Network

Steps:
- Ran container with --network host
- Tried accessing localhost port

Learning:
Host network shares host network stack.

--------------------------------------------------

## Lab 5 – None Network

Steps:
- Ran container with --network none
- Tried apt update

Result:
Failed due to no network.

Learning:
None network disables networking completely.

--------------------------------------------------

## Final Conclusion

Default Bridge → Basic container communication  
Custom Bridge → Secure + DNS support  
Host Network → Direct host networking  
None Network → No connectivity
