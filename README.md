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
docker run ubuntu             # pull this image and then start a container
```
```
docker ps                     # list of running processes or running containers
```
```
docker ps -a                  # stopped containers as well
```
```
docker run -it ubuntu         # to start a container and interact with it.
```
Now, A shell Prompt will come. A shell is a program that takes our commands and passes them to the Operating system for execution.
looks like this:-
```
root@2f759e6886e3:/#
```
You can run these programs in this shell prompt:
```
echo hello              # will print hello on the terminal
```
```
whoami                  # this will show the current user
```
```
echo $0                 # location of this shell program
```
```
history                 # all the commands we have executed lately
```
```
!2                      # by using exclamation mark (!) we can execute the previous command
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
apt                         # Can see the most used commands
```
```
apt list                    # See all the packages in this database
```
```
apt update                  # to update the package database
```
```
apt install nano            # This will install nano
```
Nano is installed!

```
nano                        # To run nano
```
to exit `ctrl + x `

```
apt remove nano             # To Remove nano form the database
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

## `Editing and Viewing Files`
```
nano file.txt                   # to edit file.txt
```
```
cat file.txt                    # to view file.txt
```
```
more /etc/adduser.conf          # to view page by page
```
```
less file.txt                   # to view with scrolling capabilities
apt install less                # if don't have less command install it
```
```
head file.txt                   # to view the first 10 lines
```
```
head -n 5 file.txt              # to view the first 5 lines 
```
```
tail file.txt                   # to view the last 10 lines 
```
```
tail -n 5 file.txt              # to view the last 5 lines
```

## `Redirection`
Concept of standard input and output, Standard Input represents the keyboard and Standard output represents the screen. But we can always change the source of input and output this is called `Redirection`.
```
cat file1.txt > file2.txt                      # cat will read the content from the first file and write to the second file
```
```
cat file1.txt file2.txt                        # cat will read data from both the files and print it in the terminal
```
```
cat file1.txt file2.txt > combined.txt         # will combine both the files in one
```
```
echo hello > hello.txt                         # hello.txt which now contains "hello"
```
```
ls -l /etc > files.txt                         # long listening of all the files in a file
```

## `Searching for text`
grep: global regular expression print
```
grep hello file.txt                      # to search for hello in file.txt
```
```
grep -i hello file.txt                   # case-insensitive search 
```
```
grep -i hello file*.txt                  # to search in files with a pattern
```
```
grep -i -r hello .                       # to search in the current directory
```

## `Finding files and directories`
```
find                                    # to list all files and directories
```
```
find -type d                            # to list directories only
```
```
find -type f                            # to list files only
```
```
find -name “f*”                         # to filter by name using a pattern
```
```
find -type f -name "f*"                 # find all the files whose name start with f
```
```
find -type f -iname "F*"                # find all the files whose name start with f, i makes it case insensitive
```
```
find / -type f -name "*.py" > python-files.txt
```


## `Chaining Commands`
```
mkdir test ; cd test ; echo done               # execute all the commands in one go
```
```
mkdir test && cd test && echo done             # if one commands fail, other commands will not get executed
```
```
mkdir test || echo "directory exists"          # if first executes, second will not execute and vice versa
```
```
ls /bin | less                                 # what comes out of first command, goes into second command
```
```
ls /bin | head -n 5
```
```
mkdir hello;\
cd hello;\
echo done                                      # Breaking a long command into different lines
```

## `Managing environment variables`
Just like we have variables in our programming languages. In linux, We have environment variables Which we can set for storing configuration settings for our applications. So, our applications can read configuration settings from these envirnoment variables.

```
printenv                                       # to list all variables and their value
```
```
printenv PATH                                  # to view the value of PATH
```
```
echo $PATH                                     # to view the value of PATH
```
```
export name=bob                                # to set a variable in the current session
```

To start the previously closed container
```
docker ps                         # to see all the docker processes or container
```
```
docker ps -a                      # to see all the containers including stopped container
```
```
docker start -i 2f7               # to start the container again: "2f7" first few letters of container id
```

## `Managing processes`
A Process is an instance of a running program.

```
ps                                 # to list the running processes
```
```
kill 37                            # to kill the process with ID 37
```

## `Managing users and groups`
```
useradd -m john                              # to create a user with a home directory
```
```
cat /etc/passwd                              # we can look at the user
```
```
usermod -s /bin/bash john                    # to modify
```
```
cat /etc/shadow                              # only root user can access it
```
```
docker exec -it -u john 2f759e6886e9 bash    # login as john, not as a root user
```
```
adduser john                                 # to add a user interactively
```
```
usermod                                      # to modify a user
```
```
userdel                                      # to delete a user
```
```
groupadd devs                                # to create a group 
```
```
groups john                                  # to view the groups for john
```
```
groupmod                                     # to modify a group
```
```
groupdel                                     # to delete a group
```

## `File permissions`
```
chmod u+x deploy.sh                      # give the owning user execute permission
```
```
chmod g+x deploy.sh                      # give the owning group execute permission
```
```
chmod o+x deploy.sh                      # give everyone else execute permission
```
```
chmod ug+x deploy.sh                     # to give the owning user and group
                                         # execute permission
```
```
chmod ug-x deploy.sh                     # to remove the execute permission from 
                                         # the owning user and group 
```
