## Objectives
In this exercise, you will
- Log in to AWS and set up account security credentials
- Configure the EC2 command-line tools to run on your local workstation

## Overview
During this exercise, you will use the user name assigned by your instructor to log in to and become familiar with the AWS Management Console. 
You will then configure access credentials to allow your account to access AWS via command-line tools or REST-based web service APIs.
Finally, the command-line management tools will be configured to use your user's access credentials.

Warning! During this class, you will be provided with credentials that can provision resources in AWS.
You are expected to only use these credentials to perform the exercises and deploy the required resources to complete the exercises.
Please refrain from using these credentials to deploy additional resources in AWS.

## Logging in to the AWS Management Console
1. Start a web browser and go the AWS login URL of https:// instantbrains.signin.aws.amazon.com/console.
2. Sign in with the user name and password provided by the instructor. Use instantbrains for the Account ID or alias if it is not already populated.
- Warning! Remember, your user belongs to the same AWS account as others attending this class. You may see some resources already provisioned by other attendees. Throughout the week, be sure to only modify your own resources.
3. Switch to the EC2 dashboard by clicking Services and then EC2.
   - When you click Services, the different services can be organized by function group or alphabetically.
You can click the A-Z button to sort alphabetically.
   - You can also type into the filter/search field to narrow the results
4. Set the Region drop-down menu (in the top right) to the region assigned by your instructor.
5. In the Service Health section, click the link to Service Health Dashboard.
6. This should open the AWS Service Health Dashboard in a new browser tab.
his dashboard provides real-time service availability of all the AWS services.
It is a good idea to check this page occasionally.
7. Very briefly, investigate the Service Health Dashboard to verify that services seem to be functioning.
8. Close the browser tab displaying the Service Health Dashboard when you are done.
Be careful not to close the tab or browser displaying the AWS Management Console.
9. Explore some of the AWS capability by clicking Services and then clicking
a few of the entries; e.g., Elastic Beanstalk, S3, EC2, and CloudFront.
We will investigate most functionality in detail later in the course, so do not modify anything at this time.

## Configuring your account security credentials
Currently, your user has access to the AWS Management Console but is not able to use the command-line tools or web service interfaces.
To utilize these capabilities, each user must create access keys.
These access keys can be set for any AWS user.
For AWS accounts, these are set in the Security Credentials section of the AWS account screen.
For IAM-created accounts, they are set within the IAM services of the Management Console.

1. Select Services | IAM and click Users on the left side.
2. Locate your user name in the table, and click your user name (not the checkbox).
3. Go to the Security Credentials tab, and investigate the contents.
4. Your user should not currently have any access keys, signing certificates, or a multifactor authentication device.
- We will now create new access keys.
5. Click the Create Access Key button.
   - You will see a dialog indicating that the keys have been generated and can be downloaded.
   - Be careful not to clowe this dialog until you've saved everythingyou need.
6. Click Show to view the keys.
7. Click the Download .csv file button and select the browser option to save the file
(Chrome will save the file to downloads without prompting). The browser should save the file as accessKeys.csv in the Downloads folder.
- Warning! It is important to save these keys, because Amazon only allows the secret key to be downloaded when created.
If you forget to save it or lose the file, there is no way to recover the secret key.
However, as you see, it is very easy to create a new set.
- There is a limit of three access keys per user. This is enough to allow key rotation. If yu accidentally exhaust keys, delete some.
8. When you are done, click Close to close the Create Access Key dialog. You should now be back on the Security Credentials tab of IAM.

## Configuring the EC2 command-line tools
The EC2 command-line tools are available as a command line interface (CLI) for Windows, Mac, or Linux/Unix, or as Windows Powershell tools.
The command-line tools provide an alternative to the Management Console and are useful to allow tasks to be scripted for automation.
The command-line tools also currently contain more functionality than the Management Console.
They can be downloaded from http:// aws.amazon.com/cli.

1. The command-line tools for Windows may have already been downloaded and installed on your environment.
Check this by opening a command prompt and typing
````
aws --version
````
2. If you get a "command not found" error or similar, install the AWS CLI tools appropriate for your OS.
3. For Windows, this just involves downloading the installer file and double-clicking it to run it.

### We will now configure them with your credentials.
1. Open a Windows command prompt by double-clicking the Command Prompt icon on the desktop.
3. Type the following command at the command prompt to try to list all available regions within EC2:
````
aws ec2 describe-regions
````
   - You should see a message that you must specify a region. We have not yet configured the tools.
4. Type the following command at the command prompt to configure the command- line tools:
````
aws configure
````
   - You should be prompted to enter your AWS Access Key ID.
The AWS access keys required were created and downloaded in the previous section of this exercise. The keys should be in the accessKeys.csv file Downloads folder.
5. Open the accessKeys.csv file in Notepad or some other editor. The file will contain two values: your access key id and secret access key,
separated by commas:
6. Highlight just the Access Key ID field from this file and copy it to our clipboard.
Do not close the file, as you will need to copy the secret key shortly.
7. Switch back to the command prompt window and paste the access key id. Press Enter.
   - You should now be prompted to enter your AWS Secret Access Key.
8. Switch back to your editor. Highlight the Secret Access Key value and copy it.
9. Switch back to the command prompt window and paste the Secret Access Key. Press Enter.
   - You should now be prompted to enter a Default Region Name.
This is the name of the AWS region to use if you do not specify one for each command.
This can reduce typing if you perform most operations in the same region.
In this course, we will set it to the region assigned by your instructor (usually us-east-1).
11. Enter the API name of the region assigned by your instructor. It will be in the form: us-east-1, us-west-2, eu-west-1, etc. Press Enter.
   - You will now be prompted to enter output format. Valid values are json, text, or table.
For this course we will use json, but feel free to explore other formats if you like.
You can always run the aws configure command again and change the format.
13. Type json and press Enter.

- The AWS command-line tools should now be configured.
14. Test the EC2 tools by typing the following command:
````
aws ec2 describe-regions
````
Wait for the results, then try:
````
aws ec2 describe-availability-zones
````
This will display the command-line interface names that Amazon used for the regions and zones.

15. Test the IAM tools by typing the following command, where <UserName> is the AWS user name assigned by your instructor:
````
aws iam list-groups-for-user --user-name [UserName]
````

If you have more time investigate additional command-line tool commands:
The AWS command line syntax is:
````
aws [options] <command> <subcommand> [parameters] Help can be obtained for commands by typing help as a parameter.
````
1. Switch to the command prompt window and type the following for more information:
````
aws help
````
Investigate the information displayed.
Within the help information displayed, locate the Available Services.
This lists all the AWS services that can be controlled with the command-line tools.
You will see many services listed.

Help can be obtained for each service by typing:
````
aws <service-name> help
````
For example:
````
aws ec2 help
aws autoscaling help
aws s3 help
````
2. Retrieve the help information for a few services, and investigate the available commands.
Help can be also be obtained for individual commands by typing:
````
aws <service-name> <command> help
````
For example:
````
aws ec2 describe-regions help
````
