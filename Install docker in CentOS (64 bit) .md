# Install docker in CentOS (64 bit)

For details check - https://docs.docker.com/install/linux/docker-ce/centos/
### Login to the server

```sh
$ sudo ssh root@192.168.1.22
```
Enter the password 
### Installation
First you need to update the system packages and install the required dependencies:

```sh
$ sudo yum update
$ sudo yum install yum-utils device-mapper-persistent-data lvm2
```

Next, run the following command which will add the Docker stable repository to your system:

```sh
$ sudo yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
```
Now that the Docker repository is enabled, install the latest version of Docker CE (Community Edition) using yum by typing:

```sh
$ sudo yum install docker-ce
```
Add your user to the docker group with the following command.
```sh
sudo usermod -aG docker $(whoami)
```
Once the Docker package is installed, start the Docker daemon and enable it to automatically start at boot time:
```sh
$ sudo systemctl start docker
$ sudo systemctl enable docker
```
To verify that the Docker service is running type:
```sh
$ sudo systemctl status docker
```
Now you can check the version of your installed docker with 
```sh
$ docker -v
```

Wohooo you have successfully installed docker in your system. Now you have to install mysql. Lets start.......

### Install MySql

Download and add the repository, then update.

```sh
$ wget http://repo.mysql.com/mysql-community-release-el7-5.noarch.rpm
$ sudo rpm -ivh mysql-community-release-el7-5.noarch.rpm
$ yum update
```
Install MySQL as usual and start the service. During installation, you will be asked if you want to accept the results from the .rpm file’s GPG verification. If no error or mismatch occurs, enter y.
```sh
$ sudo yum install mysql-server
$ sudo systemctl start mysqld
```
Run the mysql_secure_installation script to address several security concerns in a default MySQL installation.
```sh
$ sudo mysql_secure_installation
```
You will be given the choice to change the MySQL root password, remove anonymous user accounts, disable root logins outside of localhost, and remove test databases. It is recommended that you answer yes to these options. You can read more about the script in the MySQL Reference Manual.
```sh
sudo grep 'temporary password' /var/log/mysqld.log
```

**If I doesn't start normally, run this -
```sh
$ systemctl status mysqld.service
```
If no errors show up, try this:
```sh
$ systemctl restart mysqld.service
$ systemctl status mysqld.service
```

Now Everything is done. YOLO.













