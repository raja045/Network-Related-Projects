# Overview
This project guides you through the process of setting up your own Virtual Private Network (VPN) server using an **AWS EC2 instance** and **OpenVPN Amazon AMI**. A VPN server helps secure your internet connection and ensures privacy by routing your traffic through a secure server.
![VPN_Diagram](https://github.com/raja045/Network-Related-Projects/assets/94227376/d88737f8-d1cc-4e87-ba6e-1c7a2a382e81)

# Services Used
- OpenVPN AMI for Amazon AWS.
- AWS - EC2 Instance.

# Project Setup
Refer to this blog for detailed explanation STEP 1 and STEP 2. [BLOG LINK](https://nakamotosecurity.blogspot.com/2024/07/the-ultimate-guide-to-setting-up.html )
### STEP 1: Launch an EC2 Instance
- Log in to AWS Management Console: Navigate to the EC2 Dashboard.
- Create a New Instance:
- Click on Launch Instance.
- Choose the OpenVPN Access Server from the AWS Marketplace.
- Select the instance type (t2.micro is sufficient for small-scale use).
- Configure instance details as required.
- Add storage (default settings are usually sufficient).
- Configure security group:
- Allow inbound rules for ports 22 (SSH), 443 (HTTPS), and 943 (Admin Web UI).
- Allow port 1194 (UDP) for OpenVPN connections.
- Review and launch the instance.

### STEP 2: Access the Instance

- Connect to Your Instance: Use an SSH client to connect to the instance.
  <img width="841" alt="image" src="https://github.com/raja045/Network-Related-Projects/assets/94227376/f6fb2f34-9557-4882-ae29-147a6a90c21c">

  Note: Recommended username during connecting SSH Client is **openvpnas**
  ```
  chmod 400 "my-openvpn.pem"
  ```
  ```
  ssh -i my-openvpn.pem openvpnas@<Public_IP_of_EC2_Instance>
  ```

### STEP 3: OpenVPN Configuration
- Follow the on-screen instructions to complete the setup.
  
  <img width="756" alt="image" src="https://github.com/raja045/Network-Related-Projects/assets/94227376/b50eafd5-7287-448c-b39d-c3c3d8383104">

  Accessing the Admin UI:
- Open a web browser and navigate to https://Public_IP_of_EC2_Instance:943/admin.
- Login with the configured username and password.
Note: refer to the blog, for detailed steps for OpenVPN coonfiguration.

### STEP 4: Downloading a Client to the OpenVPN Server
- Navigate to the URL https://Public_IP_of_EC2_Instance:943/ on the device where you want to install the OpenVPN client.
  <img width="1264" alt="image" src="https://github.com/raja045/Network-Related-Projects/assets/94227376/b5bfb0dd-7f3d-4d51-8523-1e91eb44b0c0">
- Download and Install the client in your device.

## Testing the VPN.
- Check this [website](https://whatismyipaddress.com) before connecting to VPN and after connecting to the VPN.
- you can also use any website listed below.
- https://www.whatismyip.com/
- https://nordvpn.com/what-is-my-ip/
- https://www.showmyip.com/ 

## Conclusion
Setting up your own VPN server provides enhanced security and privacy for your internet activities. This project demonstrates the step-by-step process using AWS EC2 and OpenVPN, ensuring you have control over your VPN server configuration and management.

## Resources
- https://aws.amazon.com
- https://www.canva.com/design/DAGKZaDvFmU/dxGnHNP4LKOU00PmPw0_8w/view?utm_content=DAGKZaDvFmU&utm_campaign=designshare&utm_medium=link&utm_source=editor
- https://openvpn.net/as-docs/aws-ec2.html#strengthen-security-76631
- https://nakamotosecurity.blogspot.com/2024/07/the-ultimate-guide-to-setting-up.html 


