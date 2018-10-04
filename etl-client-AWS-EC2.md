#### If using AWS EC2 for etl then follow the steps below to prepare EC2 

Once machine is ready, then go back and install the etl-docker client 

```
sudo yum update -y

sudo yum install git

sudo yum install -y docker

sudo usermod -a -G docker ec2-user

sudo curl -L https://github.com/docker/compose/releases/download/1.22.0/docker-compose-`uname -s-uname -m` | sudo tee /usr/local/bin/docker-compose > /dev/null

sudo chmod +x /usr/local/bin/docker-compose

sudo service docker start

sudo chkconfig docker on

exit

```
