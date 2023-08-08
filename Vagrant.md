Week 1

To install Vagrant on Windows, you can follow these steps:

1. **Install VirtualBox:**
   - Vagrant often relies on virtualization providers like VirtualBox.
   - Download the latest version of [VirtualBox](https://www.virtualbox.org/wiki/Downloads) and install it.

2. **Install Vagrant:**
   - Visit the [Vagrant download page](https://www.vagrantup.com/downloads.html) and download the Windows version (.msi file).
   - Run the installer once downloaded. Follow the installation prompts and accept the default settings if you're unsure about any of the options.

3. **Verify Installation:**
   - Open the Command Prompt or Powershell.
   - Type `vagrant` and press `Enter`. You should see the Vagrant version number and a list of commands, which indicates that Vagrant was installed successfully.

4. **Initialize a Vagrant Environment:**
   - Navigate to or create a new directory where you'd like your Vagrant environment to reside.
   - In the command prompt or PowerShell, `cd` to that directory.
   - Run `vagrant init` to create a default `Vagrantfile`.
   - Review and edit the `Vagrantfile` if necessary (for example, to specify a different base box or set up shared folders, networking, etc.).

5. **Start a Vagrant Box:**
   - If you're just starting out, you might want to test using a basic box. HashiCorp provides a box named `hashicorp/bionic64` which is a standard Ubuntu 18.04 LTS box.
     ```bash
     vagrant init hashicorp/bionic64
     vagrant up
     ```
   - Once you run `vagrant up`, Vagrant will download the box (if it hasn’t been downloaded already), create a virtual machine, and provision it according to the instructions in the `Vagrantfile`.

6. **Access the Vagrant Box:**
   - After starting the box with `vagrant up`, you can SSH into it using the command:
     ```bash
     vagrant ssh
     ```

Remember, if you're on Windows, the default command line terminal might not support SSH natively. In this case, you might need to use Git Bash, Cygwin, or another terminal application that provides SSH support.

7. **Halt or Destroy the Vagrant Box:**
   - When you're done with the Vagrant box, you can shut it down with:
     ```bash
     vagrant halt
     ```
   - If you wish to completely remove the box and its associated virtual machine, use:
     ```bash
     vagrant destroy
     ```

8. **Keep Vagrant Updated:**
   - It's a good practice to keep Vagrant updated. Check for updates regularly and download newer versions from the Vagrant website.

Remember, Vagrant is an incredibly powerful tool with many features, including provisioning tools, plugins, and multiple provider support. As you get more accustomed to Vagrant, you might want to dive deeper into its documentation to unlock its full potential.


	- Create a vagrant file --> Vagrant init vagrantboxname/osname
	- To check vagrant version -> Vagrant -v
	- Create a folder -> Mkdir foldername
	- Start a vagrant box -> Vagrant up
	- SSH into a vagrant box -> vagrant ssh
	- Shutdown a vagrant box --> vagrant halt
	- Destroy a vagrant box --> vagrant destroy
	- After making a change to the vagrant file, you can reprovision a vagrant box using --> vagrant reload, then, vagrant provision
	- To view all vagrant boxes running --> vagrant box list
	- To remove a vagrant box --> vagrant box remove boxname
	- Check vagrant status -> vagrant status
	- Vagrant global status -> check all vagrant boxes
	- Help --> vagrant --help

