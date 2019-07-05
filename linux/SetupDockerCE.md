# Cent OS
## Install Docker CE
* Setup the repository:
```
sudo yum install -y yum-utils device-mapper-persistent-data lvm2
sudo yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
```

* Install Docker CE:
```
sudo yum install docker-ce
```

* Add your user to the docker group:
```
sudo usermod -aG docker $(whoami)
```

* Set Docker to start automatically at boot time:
```
sudo systemctl enable docker.service
```

* Start the Docker service:
```
sudo systemctl start docker.service
```

## Install Docker Compose

* Install Extra Packages for Enterprise Linux:
```
sudo yum install epel-release
```

* Install python-pip:
```
sudo yum install -y python-pip
```


* Install Docker Compose:
```
sudo pip install docker-compose
```

* Upgrade your Python packages on CentOS 7 to get docker-compose to run successfully:
```
sudo yum upgrade python
```

* Verify the installation:
```
docker-compose version
```
