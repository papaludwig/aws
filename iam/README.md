# Objectives
In this exercise, you will:
- Create a new user to allow access to AWS
- Manage permissions for the user to restrict access to AWS
# Overview
AWS Identity and Access Management (IAM) enables you to create additional users that can access AWS resources available within your AWS account. In this exercise, you will create a new IAM user, set the access control for that user, and verify the user's permissions.
# Creating a new user
1. Log into AWS
2. Navigate to Services->IAM
3. Click the *Users* link
You should see a list of existing users.
4. Locate your user name in the list, and click your name(not the checkbox) to select it. Using the information in the console, answer the following questions:
  - What group(s) is your user a member of?
  - Are there any Group Permissions attached to your user? If so, what are they?
5. Click the *Users* link, then click the *Add User* button.
7. In the User name text field, enter a user name of [UserName]-restrict (where [UserName] is your current AWS user name).
8. Check the AWS Management Console access checkbox.
9. Select Custom password and specify a password that is the same as your current password ([UserName]PW!). Uncheck Require password reset.
10. Click Next: Permissions
11. Click Attach Existing policies directly
12. Search for ec2R
13. Check the AMazonEC2ReadOnlyAccess checkbox
14. Click Next:Review
15. Click the Create user button, then click Close.
16. Feel free to investigate MFA (Multi-Factor Authentication). To enable it, you will need an MFA device. The Google Authenticator app for smartphones works and can be downloaded for free. To enable it, click the new user just created in the user list, select the Security credentials tab, and click the edit button next to Assigned MFA Device.
17. Log out of the AWS Management Console, and click the link to sign in to the AWS Management Console.
18. Sign in with the new user name you just created.
19. On the EC2 dashboard, view all running instances. You will see some running instances.
20. Verify if you can or cannot perform the following actions:
  - Terminate an instance
  - View monitoring details
  - Connect (SSH/RDP) to the instance
  - Launch a new instance
21. Try to access other AWS recourses (S3, CloudFront, IAM, etc.). Are you able to access any other resources?
22. When you're done, log out and log back in with your original user name.
## Congratulations! You have created a new IAM user and restricted access to only view EC2 resources.
