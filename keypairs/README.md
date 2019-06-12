# Generate Key Pairs with AWS
1. Log in to the AWS Management Console
2. Verify that your Region is set to the default region for your class
3. Navigate to Services->EC2 and click the Key Pairs link in the left nav
4. Click the Create Key Pair button
5. Provide a name of [UserName]KeyPair (where [UserName] is the AWS user name assigned by your instructor)
6. Click Create
7. Save the file
8. In Chrome, the file will automatically be saved
9. The [username]KeyPair.pem file was saved in the Downloads folder. This contains your generated key pair. Amazon has stored your public key in the region used

## Prepare key for Putty wuth POuttyGen
1. Start PuTTYgen by double-clicking the icon on your desktop and perform the following steps
2. Click the Load button
3. Set the file type drop-down to All Files (\*.\*)
4. Select the [UserName]KeyPair.pem file in Downloads and click Open, then click OK
5. Click the “Save private key” button and click Yes
6. Save the key as [UserName]Key.ppk in the same folder
7. The [UserName]Key.ppk file can now be used by PuTTY to create a secure SSH connection
