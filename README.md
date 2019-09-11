# AWS
## Prerequisites

### Connecting To AWS and Transferring Files to Your Instance
Before being able to use the Seelab's MaxEnt application, it is paramount that a user is able to: 

1. Be able to **Connect** to AWS
2. Be able to **Transfer** files with AWS

To ensure this two prerequisites are satisfied, below is a set of instructions for Windows and *NIX (Mac, Linux, Unix) machines. Connecting with a Windows machine can be done with PuTTY or WSL (Windows Subsystem for Linux). Please contact your administrator to determine which route is permitted in the workplace.
#### Windows
Before continuing with PuTTY or WSL - follow the [General Pre-Requisites for Windows](./Windows/WinGenRequisites/WinGenRequisites.md). There are two ways to connect/transfer with AWS from Windows, both perform equivalently.
* #### Windows with Putty
1. Install PuTTY on your Windows Machine
2. [Convert your private key (`.pem` file) using PuTTYgen](./Windows/PuTTY/PuTTYgen.md)
3. [**Connect** to your instance using PuTTY](./Windows/PuTTY/ConnectWithPuTTY.md)
4. [**Transfer** files to Your Linux Instance Using WinSCP](./Windows/PuTTY/WinSCP.md)
* #### Windows with WSL
1. Install WSL and a Linux Distribution on your local computer
2. Copy the private key from Windows to WSL
    * In a WSL terminal window, copy the `.pem` file (for the key pair that you specified when you launched the instance) from Windows to WSL. Note the fully qualified path to the `.pem` file on WSL to use when connecting to your instance.
    * `cp /mnt/<Windows drive letter>/path/my-key-pair.pem ~/WSL-path/my-key-pair.pem`
3. [**Connect** to your instance using WSL](./Windows/WSL/ConnectingWSL.md)
4. [**Transfer** files to Your Linux Instance using SCP](./Windows/WSL/TransferringWSL.md)

#### Mac/Linux
Before continuing please follow the [General Pre-Requisites for Linux](./NIX/NIXGenRequisites.md) to ensure you have the information you need.
1. [**Connect** to your instance using SSH](./Windows/WSL/ConnectingWSL.md)
2. [**Transfer** files to Your Linux Instance using SCP](./Windows/WSL/TransferringWSL.md)

### Installing Git and Docker on Your Instance
1. Connect to your machine, using the methods above.
2. When at the command prompt, enter the following commands:
```
#Get the most up to date packages for your instance:
sudo yum update -y

#Install git in your EC2 instance:
sudo yum install git -y

#If not installed correctly, this will produce an error:
git version
```
3. Now, install the most recent Docker community edition
```
sudo amazon-linux-extras install docker
```
4. Start the docker service
```
sudo service docker start
```
5. Add the default user to the Docker user list
```
sudo usermod -a -G docker ec2-user
```
6. Log out of the instance, then reconnect to your instance.
7. Ensure Docker was successfully installed
```
docker info
```
8. Using git, get the latest copy of Seelab's MaxEnt Application
```
git clone https://github.com/tpcolson/maxent-docker.git
```
9. If everything is done correctly, the Directory containing the files should be in the home Directory, run `ls` to list the files.
  * If everything is correct, `ls` will show a folder named `maxent-docker`
  * use cd to open the `maxent-docker` directory
  ```
  cd maxent-docker
  ```
  * `ls` to show the contents of the directory
  
  ```
  # the contents should be:
  mountdata/
  windows-helper/
  Dockerfile
  LICENSE
  README.md
  npsdocker.sh
  ```
10. Transfer an `ENVIRONMENTS.zip` to the `maxent-docker/mountdata` directory using a method defined above. [**Transfer** with PuTTY/WinSCP](./Windows/PuTTY/WinSCP.md), [**Transfer** with Windows and WSL](./Windows/WSL/TransferringWSL.md), [**Transfer** with Linux](./Windows/WSL/TransferringWSL.md) 

# Seelab Server
