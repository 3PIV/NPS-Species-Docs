# General Requisites for Windows 10

## Get information about your Instance
1. Get the ID of the Instance.
    * You can get the ID of your instance using the Amazon EC2 console (from the **Instance ID** column).
2. Get the public DNS of the Instance.
    * You can get the public DNS for your instance using the Amazon EC2 console. Check the **Public DNS (IPv4)** column. If this column is hidden, choose the **Show/Hide** icon and select **Public DNS (IPv4)**.
3. The default username for the ec2 instance should be `ec2-user`.

## Enable inbound Traffic to your instance
* Ensure that the security group associated with your instance allows incoming SSH traffic from your IP address. The default security group for the VPC does not allow incoming SSH traffic by default. The security group created by the launch instance wizard enables SSH traffic by default.

## Locate the Private Key for your Instance
* Get the fully-qualified path to the location on your computer of the `.pem` file for the key pair that you specified when you launched the instance. For more information about how you created your key pair, see Creating a Key Pair Using Amazon EC2.

## Set the Permissions of your Private Key
1. Locate the `.pem` key in Windows Explorer, right-click on it then select **Properties**. Navigate to the **Security** tab and click **Advanced**.

2. Change the owner to yourself, disable inheritance and delete all permissions. Then grant yourself **Full control** and save the permissions. 

## General Errors
#### Error: Unprotected Private Key File
* This error means you have not properly set the permissions of your Private Key, please ensure the above step to set permissions has been correctly followed.