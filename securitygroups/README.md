# Building Custom Security Groups (Named Firewall Rules)
1. Log in to the AWS Management Console
2. Navigate to Services | EC2 
3. Click the Security Group link in the left side nav
4. Click the Create Security Group button
5. Provide a name of [UserName]-rdp-http
   - Where [UserName] is the AWS username assigned by your instructor
6. Provide a Description of "allow rdp and http"
7. Set the VPC to the VPC you created earlier
8. Verify the Inbound tab is selected and click "Add Rule"
9. Set the Type drop-down to "HTTP"
10. Set the Source to "Anywhere" (0.0.0.0/0, ::/0)
   - This opens Port 80 from all addresses on the Internet
11. Click the Add Rule button
12. Set the Type drop-down to RDP
13. Set the Source to "My IP"
14. This will set the source IP address to your current public IP
15. Click the Outbound tab
   - By default, outbound traffic is not restricted at all
   - Leave as the default, but note that you could restrict outbound traffic if needed
16. Click the Create button
17. Make a note of the ID of this security group (it will start with sg-)
- You have just created a security group that allows access to
HTTP (Port 80) from anywhere on the Internet and 
RDP (Port 3389) only from your public IP
