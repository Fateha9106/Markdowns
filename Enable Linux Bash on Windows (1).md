# Install Linux Subsystem on Windows


1. Settings> Update and Security> For Developers> Developer Mode> On.
2. Control Panel> Programs and Features> Turn Off or On Windows Features> Check Windows Subsystem for Linux.
3. Reboot
4. Open Command Prompt and write
    
```sh
lxrun /install
```
Or, you can install Linux from Microsoft Store [Search: Ubuntu 18.04]

Ok. Now you have installed Linux Subsystem in Windows.

# Install Ruby
1. Open Ubuntu Bash and write following commands

```sh
sudo apt-get update
    
sudo apt-get install git-core curl zlib1g-dev build-essential libssl-dev libreadline-dev libyaml-dev libsqlite3-dev sqlite3 libxml2-dev libxslt1-dev libcurl4-openssl-dev software-properties-common libffi-dev
```    
> Installing with **rbenv** is a simple two step process. First you install **rbenv**, and then **ruby-build** 




```sh
cd
git clone https://github.com/rbenv/rbenv.git ~/.rbenv
echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bashrc
echo 'eval "$(rbenv init -)"' >> ~/.bashrc
exec $SHELL
```

```sh
git clone https://github.com/rbenv/ruby-build.git ~/.rbenv/plugins/ruby-build
echo 'export PATH="$HOME/.rbenv/plugins/ruby-build/bin:$PATH"' >> ~/.bashrc
exec $SHELL
```
```sh
rbenv install 2.5.3
rbenv global 2.5.3 
```
2. The last step is to install Bundler  

```sh
gem install bundler
rbenv rehash
```



# Configure Git

```sh
git config --global color.ui true
git config --global user.name "name"
git config --global user.email "email.example.com"
```

# Install MySql
```sh
sudo apt-get install mysql-server mysql-client libmysqlclient-dev
```

# Install Rails
Run the following commands in cmd- 
```sh
curl -sL https://deb.nodesource.com/setup_8.x | sudo -E bash -
sudo apt-get install -y nodejs
gem install rails -v 5.2.1
rbenv rehash
rails -v
cd /mnt/c
mkdir -p rbprojects
rails new myapp -d mysql
cd myapp
rails s
```
> Now you are Done. Hit with http://localhost:3000