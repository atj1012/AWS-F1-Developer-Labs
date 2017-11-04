# Lab Setup - SC17

In this section, we will setup our instance, connect to it and download the Lab files and instructions.

## Start a preconfigured EC2 F1 instance

For this event, each participant has been attributed an EC2 F1 instance, a user name and password.

The user name and password were communicated through an email message sent a couple of days before the event.
The message contains a URL that will help you access an EC2 F1 instance.
```
If you have not received that email, please contact a staff member at the beginning of the lab session.
```
- Retrieve and navigate to that URL, it points to the AWS EC2 console management page.
- Enter the Account ID communicated by the staff.
- Click "Next"
- Enter the IAM user name received in the email mentioned above and the password.
- Click "Sign In"

You should see one stopped EC2 F1 instance.
Start the instance (click on the "actions" pulldown button and select "start").
Allow some time for the instance to start...
Once the instance is running, the EC2 console gives you information relative to the **public IP address** of the instance.
You will use that IP address for the next step.

## \"Remote desktop\" to the instance

The instance just started is preconfigured with remote desktop protocol (RDP) services.
- From your local machine, start a remote desktop protocol client
   - On Windows: press the Windows key and type "remote desktop".  You should see the "Remote Desktop Connection" show in the list of programs.  (Alternatively you could also directly invoke mstsc.exe)
   - On Linux: any RDP client such a Remmina or Vinagre are suitable
   - On macOS: Microsoft Remote Desktop from the Mac App Store
- In the RDP client, enter the **public IP address** you obtained from the EC2 console page into the 'Computer' text entry field of the client
- Click **Connect**
This should bring up a message about connection certificates. 
- Click **Yes** to proceed.
The Remote Desktop Connection window opens with a login prompt. 
- Log in with the following credentials:
   - User: **user name from the email message**
   - Password: **xilinx_sc17**
- Click **Ok**
You should now be connected to the instance.

## Configure the Xilinx SDAccel environment and load the workshop files

* Open a terminal window, execute the following commands to setup the SDAccel environment (AWS_FPGA_REPO_DIR and XILINX_SDX are predefined)
```  
cd $AWS_FPGA_REPO_DIR                                         
source sdaccel_setup.sh
source $XILINX_SDX/settings64.sh 
```

* Get the SC17 developer lab Github repository to copy the necessary files
```
cd /home/centos
git clone https://github.com/Xilinx/SC17_Developer_Lab
```