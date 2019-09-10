# AWS
## Prerequisites
Before being able to use the Seelab's MaxEnt application, it is paramount that a user is able to: 

1. Be able to **Connect** to AWS
2. Be able to **Transfer** files with AWS

To ensure this two prerequisites are satisfied, below is a set of instructions for Windows and *NIX (Mac, Linux, Unix) machines. Connecting with a Windows machine can be done with PuTTY or WSL (Windows Subsystem for Linux). Please contact your administrator to determine which route is permitted in the workplace.
### Windows
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

# Seelab Server
