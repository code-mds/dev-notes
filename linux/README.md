# Get Environment information
* Print Linux Distribution: `cat /etc/os-release`
* Print process status: `ps aux`
* List open file handles: `find . -type f | wc -l`
* Print last 20 rows and wait for updates `tail -n 20 -f /appdata/node1.log`
* Stop Docker Service `sudo service docker stop` 
* Start Docker Service `sudo service docker start`

# Firewall
```
sudo firewall-cmd --list-all
sudo firewall-cmd --zone=public --add-port=8080/tcp --permanent
sudo firewall-cmd --reload
```

# YUM
* Find which package contain a command (e.g. ifconfig)
```
yum provides <command>
yum install net-tools
```
* Update all packages
```
yum update
```
* Update a package
```
yum update <packagename>
```

# Remote Authorization with public key
* Define the authorized keys on the remote machine. 
```
scp ~/.ssh/id_rsa.pub <username>@<public_ip>
```
* create an .ssh folder on the remote server with permission: 700 
```
mkdir ~/.ssh
chmod 700 ~/.ssh/
cat id_rsa.pub >> ~/.ssh/authorized_keys
chmod 600 ~/.ssh/authorized_keys
```

# Create Symbolic link
ln -s ~/source_folder ~/dest_folder

# Setup on Cent OS
* [Setup Git](SetupGit.md)
* [Setup Node.js and NPM](SetupNPM.md)
* [Setup MySQL Client](SetupMySQLClient.md)
* [Setup Docker CE](SetupDockerCE.md)
