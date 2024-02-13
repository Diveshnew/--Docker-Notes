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

## `Linux File System`

In Linux just like windows our files and directories are organized in a Tree. In a Hierarchical Structure.

So, In windows we have a structure like this:-
```
• C:\
    • Program Files
    • Windows
```

In Linux, We have the root directory on top  of the Hierarchy, below that we have bunch of standard directories.

```
• /
    • bin    • root
    • boot   • lib
    • dev    • var
    • etc    • var
    • home
```

In Linux everything is a file!
Including devices, directories, Network socket, pipes and so on..

## `Navigating the file system`
```
pwd       # to print the working directory
```
```
ls        # to list the files and directories
```
```
ls -l     # to print a long list 
```

```
cd /      # to go to the root directory
```
```
cd bin    # to go to the bin directory
```
```
cd ..     # to go one level up
```

### `Absolute and Relative Path`
A path is a way of specifying the location of a file or a folder in a file system. A path consists of a sequence of directories and filenames, separated by slashes (/).

An `absolute path` is a path that starts from the `root directory (/)` and describes every step you must take to reach the target file or folder. An absolute path is the same regardless of your current location in the file system.

For example, `/home/user/documents/report.txt` is an absolute path that tells you to start from the `root directory (/)`, then go to the home directory, then the user directory, then the documents directory, and finally the `report.txt` file.

A `relative path` is a path that starts from your `current directory` and describes the steps you must take to reach the target file or folder. A relative path depends on your current location in the file system and may change if you move to a different directory.

For example, `documents/report.txt` is a relative path that tells you to go to the documents directory and then the `report.txt` file, assuming that you are already in the user directory.

To write a relative path, you can use two special symbols:

`. (a single dot)` represents the current directory.
For example, `./report.txt` is equivalent to `report.txt`.

`.. (two dots)` represents the parent directory.
For example, `../pictures/photo.jpg` tells you to go up one level and then to the pictures directory and the `photo.jpg` file.

You can use the pwd command to print your current directory, and the realpath command to print the absolute path of a file or folder1.

Here is a simple example of using absolute and relative paths in Linux:
```Linux
# Suppose you are in the /home/user directory
$ pwd
/home/user

# To access the report.txt file, you can use either the absolute path
$ cat /home/user/documents/report.txt
This is a report.

# Or the relative path
$ cat documents/report.txt
This is a report.

# To access the photo.jpg file, you can use either the absolute path
$ display /home/user/pictures/photo.jpg
# This will open the image in a viewer

# Or the relative path
$ display ../pictures/photo.jpg
# This will also open the image in a viewer

```

## `Manipulating files and directories`
```
mkdir test              # to create the test directory
```
```
mv test docker          # to rename a directory 
```
```
touch file.txt          # to create file.txt
```
```
mv file.txt hello.txt   # to rename a file 
```
```
rm hello.txt            # to remove a file 
```
```
rm -r docker            # to recursively remove a directory
```
