# Created Virtual Machine and deployed a Web Server
Project was created to demostrate my knowledge and skills in Azure

# Step by Step tasks use:
1. Created a Resource Group- Named rg “RG-USE-NxtCloud”
   
![Screenshot 2024-03-04 080408](https://github.com/VaShan77/Created-A-Virtual-Machine/assets/98129731/3ad0e7fa-5ba3-4f53-9eb1-e92b9db7a3f5)

2. Created a Virtual Network- Change IPv4 address to 172.10.0.0/16
   
![Screenshot 2024-03-04 080602](https://github.com/VaShan77/Created-A-Virtual-Machine/blob/main/Screenshot%202024-03-04%20080602.png)

3. Added a new subnet- “SNET-USE-NxtCloud”
![Screenshot 2024-03-04 080409](https://github.com/VaShan77/Created-A-Virtual-Machine/blob/main/Screenshot%202024-03-04%20080409.png)   

4. Created a Network Security Group “NSG-USE-NxtCloud”
![Screenshot 2024-03-04 081354](https://github.com/VaShan77/Created-A-Virtual-Machine/blob/main/Screenshot%202024-03-04%20081354.png)

5. Connected NSG to Subnet.

6. Created a Bastion Subnet.

![Screenshot 2024-03-04 082100](https://github.com/VaShan77/Created-A-Virtual-Machine/blob/main/Screenshot%202024-03-04%20082100.png)

7. Created a Bastion resource.

8. Created a Virtual Machine. Set up  was with an Ubuntu Server 18.04 LTS. Size changed to B1s. Selected SSH public key. Changed key pair name. Selected NONE for Public inbound port because I’m securing with Bastion. Left storage size to default, 30 GB. Downloaded key pair.

![Screenshot 2024-03-04 083356](https://github.com/VaShan77/Created-A-Virtual-Machine/blob/main/Screenshot%202024-03-04%20083356.png)

9. Connect to VM with Bastion. Used download SSH file from earlier.

10. Once connected to VM, installed Next Cloud.

11. On CLI ran as root: sudo snap install nextcloud

12. Next ran: sudo nextcloud.manual-install admin joseph

13. Last ran: sudo nextcloud.enable-https self-signed

14. Exit out of session.

15. Back to Azure portal in VM page. Selected the network interface then under settings selected IP Configuration.

![Screenshot 2024-03-04 091345](https://github.com/VaShan77/Created-A-Virtual-Machine/blob/main/Screenshot%202024-03-04%20091345.png)


16. Created a new Public IP Address for inconfig1 named “VMIP-USE-NxtCloud”


17. Created Inbound Port Rule to allow traffic from my current IP address.

![Screenshot 2024-03-04 091831](https://github.com/VaShan77/Created-A-Virtual-Machine/blob/main/Screenshot%202024-03-04%20091831.png)


18. Added DSN name to public IP address.


19. Configured server with added DNS name: joseph-use-nxtcloud.eastus.cloudapp.azure.com


20. Exited CLI. In new tab, logged in to server with: https:// joseph-use-nxtcloud.eastus.cloudapp.azure.com

![Screenshot 2024-03-04 093352](https://github.com/VaShan77/Created-A-Virtual-Machine/blob/main/Screenshot%202024-03-04%20093352.png)
