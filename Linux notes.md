Installing a Linux virtual machine using Oracle VirtualBox:

### 1. Install VirtualBox:
1. Go to the [VirtualBox download page](https://www.virtualbox.org/wiki/Downloads).
2. Download the version of VirtualBox appropriate for your operating system.
3. Install VirtualBox by following the on-screen prompts.

### 2. Download a Linux Distribution:
For this guide, let's use Ubuntu as an example.
1. Go to the [Ubuntu download page](https://ubuntu.com/download/desktop).
2. Download the desired version. For most users, the latest LTS (Long Term Support) version is recommended.

### 3. Set up the Virtual Machine in VirtualBox:
1. Open VirtualBox and click on the "New" button.
2. Enter a name for your VM, select the type as "Linux", and the version as "Ubuntu" (or another version if you've downloaded something different).
3. Allocate RAM to your VM. A minimum of 2GB is recommended for Ubuntu, but you can allocate more based on your system's resources.
4. Create a virtual hard disk. Choose "VDI (VirtualBox Disk Image)" and then decide whether it should be dynamically allocated or a fixed size. For most purposes, a dynamic allocation is fine. Set the size you'd like to allocate (20GB or more is a good starting point for Ubuntu).

### 4. Configure VM Settings:
1. With the VM highlighted, click on "Settings."
2. In the "System" section, ensure that the boot order has "Optical" before "Hard Disk."
3. Under the "Storage" tab, click on the "Empty" optical drive icon. Then click the small CD/DVD icon on the right, and choose "Choose/Create a Virtual Optical Disk File." Navigate to and select the Ubuntu ISO file you downloaded earlier.
4. If you want better graphics performance, under the "Display" section, increase the Video Memory.

### 5. Install Linux (Ubuntu):
1. Start the VM by selecting it and clicking "Start."
2. You should boot into the Ubuntu setup. Choose "Install Ubuntu" and follow the installation prompts. When asked about disk options, choose "Erase disk and install Ubuntu." This will format the virtual hard disk you've created, not your actual computer's disk.
3. Complete the installation process by setting your timezone, keyboard layout, user name, and password.


Types:
	- Sh (Bourne shell)
	- Bash (Bourne-Again shell)
	- Korn Shell (Ksh)
	- Zsh

Knowing where you are:
	- Root directory --> /
	- Home directory --> ~ or $HOME
	- Pwd --> Present working directory

/home --> all user home directories are located
/mnt --> all file systems are mounted
/var /log --> for logging


	- $ uname -a --> to identify OS
	- $ date --> system date and time
	- $ uptime --> how long the system has been up
	- $ whoami --> who is the logged in user
	- $ export VAR=VALUE --> export to set a variable
	- $ echo $VAR --> display values
	- $ ps --> to view running process
	- $ top --> get information about running processes
	- $ df - h --> details about storage
	- $ pwd --> present working directory
	- $ cd --> change directory
	- $ ls --> list contents of a directory

Commands for File operations
	- mkdir DIR --> to create a new directory
	- Rmdir DIR -> to remove a dire
	- Touch FILE --> create an empty file with touch
	- cp FILE FILE --> copy files
	- mv FILE FILE --> move or cut and paste files and also to rename files
	- rm FILE --> delete a file
	- cat FILE --> display content of a file
	- head FILE --> view top of the file
	- tail FILE --> view bottom of the file


How to edit files
	- Two types of editors vim and nano
	- To use vim, vi filename.fileextension
		○ In vim, I is to edit
		○ Escape key to leave edit mode
		○ W to write
		○ Q! to quit
	- To use nano, nano filename.fileextension

To get help on a command
	- Man COMMAND
	- COMMAND -h
	- COMMAND -help


	- Users in linux are stored in cat /etc/passwd
	- Add a user -> useradd username
	- Set a user password -> passwd username
	- Create a user with Home directory -> useradd -m username
	- Create user with login group -> useradd -g users username
	- Confirm user IDs -> id username
	- Create user with a specified shell -> useradd -s /usr/bin/zsh username

You need to switch to the root user to create and manage users
	- Sudo su

	- Create new group -> groupadd groupname 
	- Add user to groups -> usermod -a -G groupa,groupb username
	- Rename Group -> groupmod -n newname oldname
	- Delete group -> groupdel groupname
	- Contains list of all groups -> /etc/group

	- To create a user and add that user to a group --> usermod -a -G mygroup myuser


	- To set which user owns a file -> chown user:group FILENAME
	- To set permissions -> chmod [OPTIONS] targetuser[ugoa] action[-+=]permission[r,w,x] FILE
	- Symbolic and numeric method to set permissions
		○ Symbolic --> use target user, actions (+ - =) and permissions (r, w, x) to set permissions
	- Number --> calculate permissions using 4 = read, 2 = write, 1 = execute and - = 0 no permission

	- Sudoers (Sudo) --> admin account that has all permissions
	- Add a user to sudo group -> usermod -g sudo vagrant


SSH
	- SSH = secure shell for remote access
	- Public keys are stored in the authorize_key file on the server
To generate SSH keys -> Ssh-keygen


	- Process is a program currently being executed
	- Foreground(fg) & background(bg / &)
	- Foreground processes will prevent you from performing any other action until it is complete
	- To force a process in the background, append &
	- Init is the first process to start and all other processes originate from it
	- Types of process -> parent, child, orphaned, zombie, daemon
	- Process commands,
		○ Ps -> to check running processes
		○ Ps aux -> list processes with extended information
		○ Ps -ef - list processes from all users with extended info
		○ Ps euxf - list processes from all users with extended tree info
		○ Top - more detailed info about running processes
		○ Htop - 
		○ Kill - end any process
		○ Sleep - pause all processes

	- File system determines how files are handled
	- EXT file system is the most common
	

Mounting Extra Storage
	• Using the mount command:  mount DEVICE_NAME DIRECTORY
	• Using fstab: /etc/fstab
	• Df -h --> shows different file systems and where they are mounted
	

Finding External Storage
	• dmesg : Displays messages from the Kernel including loaded drives and devices
	• lsblk : List block devices

Linux Memory
	• /proc/memfile to show virtual memory, resident memory and swap file
	• top : Running Processes with Memory info
free : Memory usage

Linux application packaging and Distribution:
	• DEB packaging
	• RPM packaging
	• Tarball / Source code
Package Managers
	• apk (Alpine Systems)
	• apt (Debian Systems)
	• dpkg (Debian Systems)
	• snap (Ubuntu Systems)
	• yum (RPM Systems)
Package Index
Package index is a database of available packages
	• /etc/apt/sources.list
	• /etc/apt/sources.list.d (Directory)
Package Managers
apt
	• Update Package Index: apt update
	• Install package: apt install <application>
	• Uninstall package: apt remove <application>
	• Upgrade packages: apt upgrade
dpkg
dpkg – Debian systems and doesn’t automatically download packages
	• List packages: dpkg -l
	• Install package using file: dpkg -i <application.deb>
	• Uninstall package: dpkg -r <application>
Source Installation
	• Most applications provide makefiles for installation
	• A makefile contains instructions for how an application should be compiled
	• Systemd can then be used to tell the OS how the compiled application should be started and run
