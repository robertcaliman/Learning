![docker-logo|100](Images/docker-logo.png)
## Docker installation 

#### The installation was done on a Linux VM (Rocky) inside Hyper-V hypervisor for Windows, so all the commands will be noted as for Linux.

```
sudo dnf update
```

```
sudo dnf install -y dnf-utils device-mapper-persistent-data lvm2
```

```
sudo tee /etc/yum.repos.d/docker-ce.repo <<EOF 
[docker-ce-stable] 
name=Docker CE Stable - $basearch baseurl=https://download.docker.com/linux/centos/8/$basearch/stable 
enabled=1 
gpgcheck=1 
gpgkey=https://download.docker.com/linux/centos/gpg 
EOF
```

```
sudo dnf install docker-ce
```

```
sudo systemctl start docker 
sudo systemctl enable docker
```
###### To add the user to docker group ( so you won't be needing to execute docker commands using `sudo` every time)

```
sudo usermod -aG docker $USER
```

###### After you execute the command above execute to logout and login again, for the group changes to take place:

```
sudo su
su your_user
```
 
###### Use this command to make sure you have the privileges 

```
docker container ls
```

## Docker images

