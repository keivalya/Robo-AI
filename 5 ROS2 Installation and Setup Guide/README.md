# ROS2 Installation

## Which ROS2 distribution to use?

There are many ROS2 distributions that you can pick from. From 2020 there is a new distribution every year in May, and it's quite easy to know what's the order because it simply follows the alphabetical order.

You can check all of them out at [ROS2 Distribution](https://docs.ros.org/en/rolling/Releases.html).

We will be using [Humble Hawksbill](https://docs.ros.org/en/rolling/Releases/Release-Humble-Hawksbill.html) throughout this course, and I recommend you to install the same with me to follow along.

## Install Ubuntu 22.04 on Virtual Machine (VirtualBox)

### Step 1 : Download the ISO Image of Ubuntu 22.04
Go to [https://releases.ubuntu.com/jammy/](https://releases.ubuntu.com/jammy/) and Download the **Desktop Image** by clicking on **64-bit PC (AMD64) desktop image**

Shortcut Click [here](https://releases.ubuntu.com/jammy/ubuntu-22.04.4-desktop-amd64.iso).

It is a 4.7 GB file, hence it may take a LOT of time.

In the mean time, lets move on.

### Step 2 : Download VirtualBox Installer
Now, do to [https://www.virtualbox.org/wiki/Downloads](https://www.virtualbox.org/wiki/Downloads), and choose your VirtualBox Platform Binary depending on the OS you are using currently.

### Step 3 : Install VirtualBox
Open the Installer, and follow the simple steps of VirtualBox Installation.

## Create Virtual Machine
Now, open the **Oracle VM VirtualBox Manager** and click on a button on the top bar that says "New" (this may resemble a star with many points)

Use the following Description (you may change it, but I recommend this):

+ Name : Ubuntu_2204_ROS2
+ Machine Folder : *keep it unchanged, or move it to a drive with more space*
+ Type : Linux
+ Version : Ubuntu (64-bit)

Next - 
Memory Size (RAM) : *depends on your Computer; for instance a quick rule is: do not give more than half of your PC RAM. I have expanded my RAM to 16 GB, hence I have allocated **8 GB** of RAM to my VM. 6GB would also work well.*

Hard Disk : Select *Create a virtual hard disk now*

Hard Disk File Type : VDI

Storage on Physical Hard Disk : ***Dynamically Allocated***

File Location and Size : ***25 GB***

Now - 

After all the hardwork, Click on the VM that you just created and then go to its **Settings > Storage**

Then, click on "Empty" which is below *Controller: IDE*, and then click on a disk-like looking icon near **Optical Drive** under **Attributes**

There, **Choose a disk file...** and select the Ubuntu22.04 ISO file that we downloaded in Step 1!

Click on ***OK*** to save the Settings.

Now LAUNCH the Virtual Machine, by simply clicking on ***Start***.

Don't congratulate yourself just yet. We are still supposed to Install Ubuntu on the VM.

## Installing Ubuntu on VM
Click **Try or Install Ubuntu** from GNU GRUB Menu.

Click on "Install Ubuntu" > Keyboard Layout "English"

Updates and other software, what apps would you like to install to start with? - select **Minimal Installation**. *Keep everything else as-it-is*

Installation type > **Erase disk and install Ubuntu** > *Install Now* > Continue

Who are You? > you may use any username or password. *Just one suggestion, keep passwork as short/weak as possible. You will thank me later.* > Check **Log in automatically**

Click on **Continue**


Now, ***CONGRATULATIONS!!!** Ubuntu Installation is finished.*

## First-things-first
Right after installation, open Terminal and run the following commands

> sudo apt update

> sudo apt upgrade

You will *almost always* run these commands after any new installation, or updates.

> sudo apt autoremove

> sudo apt install build-essential gcc make perl dkms

### I will be using some Programming tools (which are completely optional for you to install)

> sudo apt install terminator

In ROS/ROS2, one has to deal with multiple terminals (or sessions) simultaneously. This application helps in managing them very well.

> sudo snap install --classic code

We will need a *noice* code editor. VSCode is my personal favourite. However, one may prefer coding on a notepad also, *I will not be offended*.

> sudo apt install python3-pip

## ROS2 Installation *(finallyyy)*
To avoid repetation of instructions, I recommend you to go through [ROS2 official installation documentation](https://docs.ros.org/en/humble/Installation/Ubuntu-Install-Debians.html) and follow it along.

It is truly simple.

After successful installation, you will need to run this command on every new shell you open to have access to the ROS2 commands.

> source /opt/ros/humble/setup.bash

However, it is a tedius task! So, if you don’t want to have to source the setup file every time you open a new shell, then you can add the command to your shell startup script:

> echo "source /opt/ros/humble/setup.bash" >> ~/.bashrc

To undo this, locate your system’s shell startup script and remove the appended source command.

Sourcing ROS2 setup files will set several environment variables necessary for operating ROS2. If you ever have problems finding or using your ROS2 packages, make sure that your environment is properly set up using the following command:

> printenv | grep -i ROS

The ROS2 development environment needs to be correctly configured before use. This can be done in two ways: either sourcing the setup files in every new shell you open, or adding the source command to your startup script.