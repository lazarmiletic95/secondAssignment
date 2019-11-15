* 2 Web-Servers with Load Balancing

** Description
This docker configuration creates to paralel nginx instances one of them hosts a HTML page containing the text "red" and the other one on the contarary hosts a page containing the text "blue".

These two nginx servers are balanced through ha-proxy.

Two nginx servers are port forwarded in bridge mode to the host machine and the ha-proxy is using the host networking mode to access those two port forwarded servers. These can also be implemented in a virtual networking interface but I wanted to have access to each server directly as well.


** Web Access
On the machine this docker-compose is run on, the user can access from:
..:9999 -> Hosts the load balancer
..:10000 -> Hosts the red web server
..:10001 -> Hosts the blue web server