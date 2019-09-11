# Connect to Your Linux Instance using WSL
Use the following procedure to connect to your Linux instance using the Windows Subsystem for Linux (WSL).

1. In a terminal window, use the **ssh** command to connect to the instance. You specify the private key (`.pem`) file, the user name for your Linux Instance (default `ec2-user`), and the public DNS (IPv4) name for your instance (Found in the [General Linux Prerequisites](./NIX/NIXGenRequisites.md)). 
    * `sudo ssh -i /path/my-key-pair.pem ec2-user@123.123.123.111.my.public.dns`
    You should see the response:
    ``` 
    The authenticity of host 'ec2-user@123.123.123.111.my.public.dns'
    can't be established.
    RSA key fingerprint is 1f:51:ae:28:bf:89:e9:d8:1f:25:5d:37:2d:7d:b8:ca:9f:f5:f1:6f.
    Are you sure you want to continue connecting (yes/no)?
    ```
2. Enter, exactly: `yes`.
    * You should see the following response:
    ```
    Warning: Permanently added 'ec2-user@123.123.123.111.my.public.dns' to the list of known hosts.
    ```