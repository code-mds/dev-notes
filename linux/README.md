# Get Environment information
* Print Linux Distribution: `cat /etc/os-release`

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

# Setup
[Setup Docker on Cent OS](SetupDocker.md)