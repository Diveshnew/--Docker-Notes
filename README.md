# Docker-Learning

## `Installation of Docker`

Download Docker form [here](https://docs.docker.com/get-docker/)

After downloading you will get a docker icon on Your desktop click it! and create id in docker and then you are good to go.

## 1. Docker Basics

KeyTerms to Remember in this section:
```
Client/server architecture
Containers
Dockerfiles
Docker daemon (engine)
Docker registries
Hypervisors 
Images
Kernel
Process
Virtual machines
```
Docker is a platform for consistently building, running, and shipping applications.

A virtual machine is an abstraction of hardware resources. Using hypervisors we can 
create and manage virtual machines. The most popular hypervisors are VirtualBox, 
VMware and Hyper-v (Windows-only).

A container is an isolated environment for running an application. It’s essentially an 
operating-system process with its own file system.

Virtual machines are very resource intensive and slow to start. Containers are very 
lightweight and start quickly because they share the kernel of the host (which is already 
started).

A kernel is the core of an operating system. It’s the part that manages applications and 
hardware resources. Different operating system kernels have different APIs. That’s 
why we cannot run a Windows application on Linux because under the hood, that 
application needs to talk to a Windows kernel.

Windows 10 now includes a Linux kernel in addition to the Windows kernel. So we can 
run Linux applications natively on Windows.

Docker uses client/server architecture. It has a client component that talks to the server 
using a RESTful API. The server is also called the Docker engine (or daemon) runs in 
the background and is responsible for doing the actual work.

Using Docker, we can bundle an application into an image. Once we have an image, we 
can run it on any machine that runs Docker.

An image is a bundle of everything needed to run an application. That includes a
cutdown OS, a runtime environment (eg Node, Python, etc), application files, thirdparty libraries, environment variables, etc.

To bundle an application into an image, we need to create a Dockerfile. A Dockerfile 
contains all the instructions needed to package up an application into an image.

We can share our images by publishing them on Docker registries. The most popular 
Docker registry is Docker Hub.

#

## 2. The Linux Command Line

Linux Distribution (linux distros) : linux is a open source software and for this reason many individuals and communities
have created their own version of linux called Linux distributions.
Each of these distributions is made to fit specialized needs like running servers, desktop computer, mobile phones and so on...

### `Distros`
```
Ubuntu
Debian
Alpine
Fedora
CentOS
```
We are going to use `Ubuntu`

See here the Ubuntu image [here](https://hub.docker.com/_/ubuntu)

Now, go to the teminal and you should open the terminal in Your folder like `~/Desktop/hello-docker` where you want to set up all the things!
### `Terminal`

```
docker run ubuntu
```
```
docker ps
```
```
docker ps -a
```
```
docker run -it ubuntu
```
Now, A shell Prompt will come. A shell is a program that takes our commands and passes them to the Operating sustem for execution.
looks like this:-
```
root@2f759e6886e3:/#
```
You can run these programs in this shell prompt:
```
echo hello
```
```
whoami
```
```
echo $0
```
```
history
```
```
!2
```

## Package Managers
These days most operating systems and Development platforms come with a package manager
```
npm
yarn
pip
NuGet
```

Here in Ubuntu we also have a package manager called `apt`. Which is short for advanced package tool.

```
apt
```
```
apt list
```
```
apt update
```
```
apt install nano
```
Nano is installed!

```
nano
```
to exit `ctrl + x `

```
apt remove nano
```
