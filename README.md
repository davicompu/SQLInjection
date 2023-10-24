# Instructions and Commands


## 1. Create an IaaS machine

We will use Linode for the demonstration but feel free to set up a virtual private server (VPS) in any other IaaS (e.g., Google Cloud)


## 2. Login to your VPS over SSH

- Replace username with your user (e.g., root)
- Replace the '0.0.0.0' with the IP address of your VPS

> ssh username@0.0.0.0.0


## 3. Installing docker on Ubuntu
Link for reference https://docs.docker.com/engine/install/ubuntu/

### - Setup the docker repository

> apt-get update

> sudo apt-get install ca-certificates curl gnupg lsb-release

### - Add the GPG key

> sudo mkdir -p /etc/apt/keyrings
> curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg

### - Set up repository

> echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

## 4. Install docker-engine

> sudo apt-get update

> sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin

## 5. Install docker-compose

> sudo apt-get install docker-compose

## 6. Download the Seed lab repository and unzip its content

The link to the GitHub repository is the following: https://github.com/seed-labs/seed-labs

> wget https://github.com/seed-labs/seed-labs/archive/refs/heads/master.zip

Install unzip in the virtual machine

> apt install unzip

Then unzip the compressed file you just downloaded

> unzip master.zip


## 7. Expose the port of the web server by edition the 'docker-compose.yml'

First, you need to traverse into the directory of the SQL Injection Lab.

> cd seed-labs-master/category-web/Web_SQL_Injection/Labsetup/

Edit the 'docker-compose.yml' to enable port 80 to be exposed in port 80.

> nano docker-compose.yml

Add the following code below the 'tty: true' from the www service.

"ports:
    - 80:80 "

Press CRTL+X to exit nano and press 'y' to save changes

## 8. Finally, run the docker-compose to create a web server and a MySQL server

To start the docker containers using the 'docker-compose.yml', run the following command:

> docker-compose up -d 

To stop the docker containers, you can run the following command:

> docker-compose down

## 9. To access the server from any terminal, do not forget to add the following IP address and the domain in your local host file

> "IP_ADDRESS" www.seed-server.com

For windows, edit file with administrator privileges

c:\Windows\System32\Drivers\etc\hosts

For macOS and Linux, edit file with sudo permissions

/etc/hosts

## Examples

* boby';#
* ', salary='1' where name='boby';#
