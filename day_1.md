```bash
#check the version of os
cat /etc/os_release
cat /etc/redhat_release

#Both didn't work on my rhel-server, so I had to use
cat /etc/*release

#Kernel info
uname -a
uname -r
uptime

#info of the logged-in user and their activities on the system
whoami
w

#list of the hardwares, cpu, block devices
lshw
lscpu
lsblk -h                    #in human readable format
lsblk -a
lsblk -f                    #including details sucha as UUIDs
# list of all Peripheral Component Interconnect PCI, my rhel-server is running on a hyper-v so it doesn't show anyinfo
lspci
#list all usb devices connected to the system
lsusb

#show free space #Free: memory that is completely unused by the system  #Available: memory that is available for new applications including free memory and reclaimable cached memoery
free -h
#Virtual Memory Statistics - provides real-time system performance metrics, including CPU, memory, disk, and system processes. 
vmstat     
vmstat -S M                 #show stats in memory in Mb

# show system performances 
top                         #a basic, text-based interface to view system processes, resource usage (CPU, memory, etc.)            
htop                        # more user-friendly and interactive interface of top command.

#show information about the file system disk usage space usage.  -h in human-readable version
df -h
# disk usage in human-readable version
du -h
du -sh /home/username      #size of this directory

#show information of networks
ip a
ip addr
ip address

# Measure Network Usage
# Show statistics for all networks on the system, such as info about no of packets sent and transmitted, errors, collisions
netstat -i
watch netstat -i
netstat -i eth0           #see a specific interface.
netstat -u                # shows info about UDP (User Datagram Protocol)
# Display Real-time network interface statistics
ifstat
# Monitor real-time network band-width usage on a network interface (like top but for network interfaces)
#there is no iftop on rhel-server9.3, i have to install epel first
sudo dnf install https://dl.fedoraproject.org/pub/epel/epel-release-latest-9.noarch.rpm                          #EPEL Extra Packages for Enterprise Linux
sudo dnf repolist          # The list of enabled repositories on the system. A repo is a collection of software packages that the package manager (yum or dnf) can download and install from. 
sudo dnf install iftop
iftop
sudo iftop -i <interface>
sudo iftop -i eth0



```
