# netmazeexp
Setting Up a Site-to-Site VPN Connection between On-Premises Network and Azure VNet

Establishing a secure Site-to-Site VPN connection between  on-premises network and an Azure Virtual Network (VNet) to enable seamless and secure data transfer.

1. Creating resource group "plink"
2. Creating vnet1 in east asia location with address space "10.1.0.0/16"
3. Creating onpremvnet2(simulating on premises network) in South Africa North with address space "10.0.0.0/16"
4. Creating Gateway Subnets for both  networks.
5. Creating virtual network gateway "vpngateway1" for vnet1 of route based type vpn
6. Creating virtual network gateway "vpngateway2" for onpremvnet2 of route based type vpn
7. Creating local network gateway "localgateway1" for vnet1 with ip address of vpngateway2 and address space of onpremvnet2
8. Creating local network gateway "localgateway2" for onpremvnet2 with ip address of vpngateway2 and address space of vnet1
9. Creating a site-to-site connection  "vnet1toonprem2" from vpngateway1 to vpngateway2 with a shared key
10. Creating a site-to-site connection "onpremvnet2tovnet1" from vpngateway2 to vpngateway1 with the same shared key
11. Creating a virtual machine vm1 in vnet1
12. Creating a virtual machine vm2 in onpremvnet2
13. Adding the nsg rule "AllowAnyCustomAnyInbound" and "AllowAnyCustomAnyOutbound" for allowing icmp protocol for the ping test for both the vms
14. Enabling both inbound and outbound rules for File and printer sharing(echo request) for both the vms
15. Try pinging the other vm with the private address and validate the test

