# Creating a VPC
## Using the Launch VPC Wizard
1. Navigate to Services | VPC, verify default region.
2. Cick the Launch VPC Wizard button
3. Verify “VPC with a Single Public Subnet” is selected; click the Select button
4. Use the following values to create your VPC, where X is your user number and [username] is your AWS username
   - IPv4 CIDR block: 10.X.0.0/16
   - IPV6 CIDR block: No IPv6 CIDR Block
   - VPC name: [username]-vpc
   - Public subnet: 10.X.100.0/24
   - Availability Zone: your choice (but remember what you chose)
   - Subnet name: [username]-publicsubnet-1
   - Enable DNS hostnames: Yes
   - Hardware tenancy: Default
5. Click Create VPC
6. Click OK when the VPC is created
7. Record your VPC ID
8. Click the Subnets link and record your Public Subnet ID and the Availability Zone of your subnet
## Add a second public subnet in a different Availability Zone
1. Click Create Subnet and use the following values:
   - Name: [username]-publicsubnet-2
   - VPC: The VPC you just created
   - Availability Zone: A different zone than you selected for first subnet
   - CIDR block: 10.X.101.0/24
2. Click Yes, Create
3. Select the subnet just created
4. In the Route Table tab at the bottom, click Edit route table association
5. Change the Route table ID to the one from the first subnet
   - (It will be the route table that contains an Internet gateway (igw))
6. Click Save and then click Close
7. Perform the following steps for both subnets in your VPC
   1. Select the subnet and click Actions | Modify Auto-Assign Public IP
   2. Check the Enable auto-assign… checkbox and click Save
8. If you have more time, feel free to create a third subnet
