* Add NodeSource yum repository
```
curl -sL https://rpm.nodesource.com/setup_10.x | sudo bash -
```

* Install Node.js and npm
```
sudo yum install nodejs
```

* Verify Installation
```
node --version
```

* Install NVM (Node Version Manager)
```
curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.11/install.sh | bash
```

* Install Development tools
```
sudo yum install gcc-c++ make
```