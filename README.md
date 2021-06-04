# zookeeper-redhat7-rpm
A set of scripts to package zookeeper into an rpm.
Requires CentOS/RedHat 7.

# Setup

    sudo yum install make rpmdevtools

# Building

    make rpm

or use Docker

    docker build -t zookeeper-build . && docker run -ti -v $(pwd)/RPMS:/root/RPMS zookeeper-build

Resulting RPM will be avaliable at $(shell pwd)/RPMS/x86_64

# Installing and operating

    sudo yum install zookeeper*.rpm
    sudo systemctl start zookeeper
    sudo systemctl enable zookeeper

# Default locations

binaries: /opt/zookeeper/bin
data:     /opt/zookeeper/data 
logs:     /opt/zookeeper/logs  
configs:  /opt/zookeeper/conf, /etc/sysconfig/zookeeper  
