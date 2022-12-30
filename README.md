# Installing maven

```sh
cd /opt

wget https://downloads.apache.org/maven/maven-3/3.6.3/binaries/apache-maven-3.6.3-bin.tar.gz

tar -xvzf apache-maven-3.6.3-bin.tar.gz

mv apache-maven-3.6.3 maven
```

# Installing JAVA

```sh
sudo apt update

sudo apt install openjdk-8-jdk
```

# Exporting the path

```sh
vi ~/.bash_profile
```



# Add the following configuration 

```sh
#bash_profile
#get the aliases and functions

if [ -f ~/.bashrc ]; then

. ~/.bashrc

fi

#user specific environment and startup programs

export JAVA_HOME=/usr/lib/jvm/java-1.8.0-openjdk-amd64

export M2_HOME=/opt/maven

export M2=/opt/maven/bin

export PATH=$PATH:$HOME/bin/:$JAVA_HOME:$M2:$M2_HOME

export PATH
```


# Save the bashrc 

:wq!

source  ~/.bashrc

# Now go to Jenkins and download the following plugins

1. Maven integration 

2. Maven invoker


# Go to global tool configuration 

Go to maven and uncheck install-automatically and update the maven home directory path and save 


 Go to new the iteam and create a maven job


 # Installing docker 

 ```sh
   sudo apt-get install docker.io -y
```

 # Installing ansible 
 
```sh
   sudo apt-get install ansible -y
```

**#Email notification on jenkins
**
```sh
1. create a identity on aws and verify it
2. create a smts crendtials
   SES > smtp setting > create credentails
3. On jenkins configure the email 
   Configure > Extended email notification > add smtp servername name and ports as 587
   Add credentials of smtp in jenkins and set as tls 
 
 4. configure the email notification
    add smtp server name > give the authentication credentails as smtip username and password > set port as 587 and enable tls
    and test the connection.
```
  


  








