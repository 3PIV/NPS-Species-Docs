# Using SCP to Transfer a File

To find your public DNS (IPv4) please consult the [Windows General Prerequisite](./Windows/WinGenRequisites/WinGenRequisites.md)

1. Transfer a file **to** your instance using the instance's public DNS name. For example, if the name of the private key file is `my-key-pair`, the file to transfer is `ENVIRONMENTS.zip`, the user name is ec2-user, and the public DNS name of the instance is `ec2-198-51-100-1.compute-1.amazonaws.com`, use the following command to copy the file to the `ec2-user` home directory:
```
scp -i /path/my-key-pair.pem /path/ENVIRONMENTS.zip ec2-user@c2-198-51-100-1.compute-1.amazonaws.com:~
```
The following should be the response:
```
The authenticity of host 'ec2-198-51-100-1.compute-1.amazonaws.com (10.254.142.33)'
can't be established.
RSA key fingerprint is 1f:51:ae:28:bf:89:e9:d8:1f:25:5d:37:2d:7d:b8:ca:9f:f5:f1:6f.
Are you sure you want to continue connecting (yes/no)?
```
2. Type, verbatim: `yes`
3. To transfer filw **from** your linux instance to your local machine, reverse the parameters. For example, to transfer the `ENVIRONMENTS.zip` file from your EC2 instance back to the home directory on your local computer, use the following command on your local computer:
```
scp -i /path/my-key-pair.pem ec2-user@ec2-198-51-100-1.compute-1.amazonaws.com:~/SampleFile.txt ~/
```

## General Errors
#### bash: scp: command not found
* If you receive a "bash: scp: command not found" error, you must first install scp on your Linux instance. For some operating systems, this is located in the openssh-clients package. For Amazon Linux variants, such as the Amazon ECS-optimized AMI, use the following command to install `scp`:
  ```
  sudo yum install -y openssh-clients
  ```