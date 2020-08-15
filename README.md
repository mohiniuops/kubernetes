# kubernetes
Steps to Install MiniCube

Installing Minikube on Linux

Let's learn how to install Minikube v1.0.1 on Ubuntu Linux 18.04 LTS with VirtualBox v6.0 specifically.

NOTE: For other versions, the installation steps may vary! Check the Minikube installation!

Install the VirtualBox hypervisor
Add the source repository for the bionic distribution (Ubuntu 18.04), download and register the public key, update and install:

$ sudo bash -c 'echo "deb https://download.virtualbox.org/virtualbox/debian bionic contrib" >> /etc/apt/sources.list'
$ wget -q https://www.virtualbox.org/download/oracle_vbox_2016.asc -O- | sudo apt-key add -
$ sudo apt-get update
$ sudo apt-get install -y virtualbox-6.0

Install Minikube
We can download the latest release from the Minikube release page. At the time the course was written, the latest Minikube release was v1.0.1. Once downloaded, we need to make it executable and add it to our PATH:

$ curl -Lo minikube https://storage.googleapis.com/minikube/releases/v1.0.1/minikube-linux-amd64 && chmod +x minikube && sudo mv minikube /usr/local/bin/

NOTE: Replacing /v1.0.1/ with /latest/ will always download the latest version.

Start Minikube
We can start Minikube with the minikube start command (disregard "Unable to read.../docker/config..." and "No matching credentials..." warnings):

$ minikube start


Check the status
With the minikube status command, we display the status of Minikube:

$ minikube status
host: Running
kubelet: Running
apiserver: Running
kubectl: Correctly Configured: pointing to minikube-vm at 192.168.99.100

Stop minikube
With the minikube stop command, we can stop Minikube:

$ minikube stop
Stopping "minikube" in virtualbox ...
"minikube" stopped.
