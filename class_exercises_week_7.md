
# Arch Package Management
the following section talks about package management in ubuntu and other debian systems, but I use Garuda, which is arch based, so heres some notes on using that

- `yay` - yet another yoghurt
	- `yay` is an AUR helper,  it acts as an intermediary between the Arch User Repository, and `pacman`
		- `yay` gives you an interactive way to select which version of a package to install from the AUR or its alternatives, like Chaotic-AUR
	- Installing a package
		- install a package with `yay <package name>`
		- select which package you want by entering the listed number
			- can install multiple at a time by listing multiple numbers
		- you will be prompted for sudo password after selecting the package
		- some packages will open up a changelog in `less`
			- can be exited with `q`
	- updating
		- for Garuda, use `garuda-update`
		- otherwise, `yay -Syu`
			- `-S` `--sync` sync packages from remotes
			- `-y` `--refresh` download a fresh master package database from server
			- `-u` modifier for `-S`, upgrades all packages
	- removing
		- `yay -r <package>`
# Linux Package Management
Bill Newman & Gemini - updated 08/17/2025

Linux package management systems simplify the process of installing, updating, configuring, and removing software. They achieve this through a combination of packages, repositories, and package managers.

**Packages**: A package is an archive file containing the application's executable files, libraries, configuration files, and metadata about the package, including its dependencies. Common package formats include .deb for Debian-based systems (like Ubuntu) and .rpm for Red Hat-based systems (like Fedora, CentOS).

**Repositories**: Software repositories are centralized locations (servers) where packages are stored and maintained. They contain a vast collection of software, along with information about package versions and their dependencies. When you install or update software, your package manager retrieves the necessary packages from these configured repositories.

**Package Managers**: These are command-line or graphical tools that interact with the repositories to perform package management operations. Examples include:

**APT (Advanced Package Tool)**: Used on Debian-based systems (e.g., apt, apt-get, aptitude).

**YUM (Yellowdog Updater, Modified) / DNF (Dandified YUM)**: Used on Red Hat-based systems (e.g., Fedora, CentOS).

**Pacman**: Used on Arch Linux.

How they work:

Dependency Resolution: A key function of package managers is dependency resolution. If a software package requires other packages or libraries to function correctly, the package manager automatically identifies and installs these dependencies along with the main package, preventing compatibility issues.

Installing: When you request to install a package (e.g., sudo apt install firefox), the package manager first consults its local index of packages from the configured repositories. It then identifies the requested package and any required dependencies. It downloads these packages from the repositories and installs them on your system, placing files in the correct locations and handling any necessary configurations.

Here's an example installing [nmap](https://nmap.org/):

`sudo apt install nmap`

Always use sudo before the apt install command, as installing packages requires root privileges.

Run sudo apt update before installing a package to ensure that the package list is up-to-date and to avoid potential issues during installation.

Updating: To update installed software, you typically update the package manager's local index of available packages from the repositories (e.g., sudo apt update). This ensures your system knows about the latest versions. This step does not install or upgrade any software; it only updates the "catalog" of available packages on your system.

After updating the package index, sudo apt upgrade is used to install the newest versions of all packages currently installed on your system. It retrieves and upgrades packages where newer versions are available in the repositories, based on the information gathered by apt update. apt upgrade will not remove any currently installed packages or install new packages that are not already present, unless they are required dependencies for an upgrade.

It is generally recommended to run sudo apt update before sudo apt upgrade to ensure you are upgrading to the latest available versions based on current repository information. This can be combined into a single command:

`sudo apt update && sudo apt upgrade`

Removing: When you remove a package (e.g., `sudo apt remove firefox`), the package manager removes the associated files and configuration. It can also identify and remove any dependencies that were installed solely for that package and are no longer needed (e.g., `sudo apt autoremove`).

### apt vs apt-get
apt and apt-get are both command-line tools used for managing packages on Debian-based Linux distributions, such as Ubuntu. While apt-get is the older, more established tool, apt is a newer, more user-friendly wrapper that combines the most commonly used functionalities of apt-get and apt-cache.  Below are some key differences:

User Experience: apt offers a more streamlined and visually appealing interface for interactive use, including features like a progress bar during installations and updates. apt-get provides a more basic output, generally preferred for scripting due to its stable and predictable output.

Command Consolidation: apt consolidates various commands that were previously separate in apt-get and apt-cache. For example, apt update replaces apt-get update, and apt show replaces apt-cache show.

Upgrade Behavior: apt upgrade can install new packages if they are required to satisfy dependencies of upgradable packages, and it also removes older versions of packages to prevent clutter. In contrast, apt-get upgrade will not install new packages and will leave older versions of packages on the system. For a full system upgrade, apt-get requires apt-get dist-upgrade, while apt uses apt full-upgrade.

Scripting vs. Interactive Use:

apt-get is generally recommended for use in scripts due to its stable interface and predictable output, which is less likely to change between versions. apt is designed for interactive use by end-users and its output and interface may evolve in future versions.

In summary: For daily interactive use and general package management, apt is the recommended choice: due to its improved user experience and consolidated commands.

For scripting and automation, apt-get is often preferred: because of its stable interface and predictable output, ensuring compatibility across different system versions.
  

For more info, see [An Overview of Package Management in Linux by Linode](https://www.linode.com/docs/guides/linux-package-management-overview/) and [Understanding Package Managers and systemctl](https://www.geeksforgeeks.org/linux-unix/understanding-package-managers-and-systemctl/) and [A Beginner’s Guide to Package Management in Linux](https://www.r-bloggers.com/2024/12/a-beginners-guide-to-package-management-in-linux/)

## nmap

nmap, short for Network Mapper, is a versatile network scanning tool used for discovering hosts and services on a computer network. It's widely employed by security professionals, system administrators, and ethical hackers to map networks, identify open ports and services, detect operating systems, and assess vulnerabilities. 

Key functionalities:

Network Discovery: Nmap can identify devices connected to a network, including their IP addresses and hostnames.

Port Scanning: It helps determine which ports are open on a target host, indicating which services are running. 

Service and Version Detection: Nmap can identify the type of service running on an open port and even the version of the software. 

Operating System Detection: It can infer the operating system of a target machine through OS fingerprinting. 

Vulnerability Scanning: By identifying open ports and services, Nmap can help pinpoint potential vulnerabilities that could be exploited.

Network Mapping: Nmap creates a visual representation of the network, showing the connections between devices and their services. 

### Who uses Nmap?

Security Professionals: Nmap is a crucial tool for penetration testing, vulnerability assessments, and network auditing. 

System Administrators: They use Nmap for network inventory, troubleshooting, and security monitoring.

Network Engineers: Nmap helps them understand network topology and troubleshoot network issues.

Ethical Hackers: Nmap is a powerful tool for reconnaissance and identifying potential weaknesses in a system.

In essence, Nmap is a versatile tool that empowers users to understand and secure their networks by providing comprehensive information about connected devices and their services.

DON'T USE NMAP ON SERVERS/SITES WITHOUT AUTHORIZATION - We can use nmap on our own servers to detect vulnerabilities, but we should only use nmap on sites on which we have permission to run scans.  Here's some info from nmap themselves on [Legal Issues](https://nmap.org/book/legal-issues.html#:~:text=Network%20probing%20or%20port%20scanning,any%20reason%2C%20is%20strictly%20prohibited.)

Example:
`nmap scanme.nmap.org`
```
Starting Nmap 7.94SVN ( https://nmap.org ) at 2025-08-18 00:47 UTC

Nmap scan report for scanme.nmap.org (45.33.32.156)

Host is up (0.025s latency).

Other addresses for scanme.nmap.org (not scanned): 2600:3c01::f03c:91ff:fe18:bb2f

Not shown: 996 closed tcp ports (conn-refused)

PORT      STATE SERVICE

22/tcp    open  ssh

80/tcp    open  http

9929/tcp  open  nping-echo

31337/tcp open  Elite

  

Nmap done: 1 IP address (1 host up) scanned in 0.56 seconds
```
