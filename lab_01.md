**LAB 1: Docker Container Management**

**Aim**

To study Docker fundamentals, manage Docker images and containers, and perform container lifecycle operations using various Docker commands.

┌──────────────────────────────────────────────────────────────────────┐

│ • MobaXterm Personal Edition v26.3 • │

│ (SSH client, X server and network tools) │

│ │

│ ⮞ SSH session to dharan@172.27.30.24 │

│ • Direct SSH : ✓ │

│ • SSH compression : ✓ │

│ • SSH-browser : ✓ │

│ • X11-forwarding : ✓ (remote display is forwarded through SSH) │

│ │

│ ⮞ For more info, ctrl+click on help or visit our website. │

└──────────────────────────────────────────────────────────────────────┘

Welcome to Ubuntu 22.04.5 LTS (GNU/Linux 5.15.0-179-generic aarch64)

\* Documentation: https://help.ubuntu.com

\* Management: https://landscape.canonical.com

\* Support: https://ubuntu.com/pro

System information as of Thu May 28 01:30:00 PM UTC 2026

System load: 0.23 Processes: 107

Usage of /: 19.7% of 37.57GB Users logged in: 1

Memory usage: 8% IPv4 address for eth0: 172.27.30.24

Swap usage: 0%

\* Strictly confined Kubernetes makes edge and IoT secure. Learn how MicroK8s

just raised the bar for easy, resilient and secure K8s cluster deployment.

https://ubuntu.com/engage/secure-kubernetes-at-the-edge

Expanded Security Maintenance for Applications is not enabled.

67 updates can be applied immediately.

To see these additional updates run: apt list --upgradable

2 additional security updates can be applied with ESM Apps.

Learn more about enabling ESM Apps service at https://ubuntu.com/esm

New release '24.04.4 LTS' available.

Run 'do-release-upgrade' to upgrade to it.

**Step 1: Verify Docker Installation**

**Command**

docker version
docker info

**Working**

* docker version displays Docker Client and Server versions.
* docker info provides detailed information about Docker Engine, storage driver, containers, images, networks, and system resources.

**Screenshot**

**Screenshot 1:** Docker Version Output

![](data:image/png;base64...)

**Screenshot 2:** Docker Information Output

![](data:image/png;base64...)

![](data:image/png;base64...)

**Step 2: Search Docker Images from Docker Hub**

**Command**

docker search ubuntu

**Working**

This command searches Docker Hub repositories and displays available Ubuntu images along with descriptions and popularity ratings.

**Screenshot**

**Screenshot 3:** Docker Search Ubuntu

![](data:image/png;base64...)

**Step 3: Download Docker Images**

**Commands**

docker pull ubuntu:22.04
docker pull centos:8
docker pull nginx
docker pull httpd
docker pull busybox
docker pull node
docker pull python
docker pull jenkins/jenkins:lts
docker pull mysql
docker pull phpmyadmin/phpmyadmin

**Working**

The docker pull command downloads images from Docker Hub to the local system.

**Screenshot**

**Screenshot 4:** Pull Ubuntu Image

![](data:image/png;base64...)

**Screenshot 5:** Pull CentOS Image

![](data:image/png;base64...)

**Screenshot 6:** Pull Nginx Image

![](data:image/png;base64...)

**Screenshot 7:** Pull HTTPD Image

![](data:image/png;base64...)

**Screenshot 8:** Pull BusyBox Image

![](data:image/png;base64...)

**Screenshot 9:** Pull Node Image

![](data:image/png;base64...)

**Screenshot 10:** Pull Python Image

![](data:image/png;base64...)

**Screenshot 11:** Pull Jenkins Image

![](data:image/png;base64...)

**Screenshot 12:** Pull MySQL Image

![](data:image/png;base64...)

**Screenshot 13:** Pull phpMyAdmin Image

![](data:image/png;base64...)

**Step 4: View Downloaded Images**

**Command**

docker images

**Working**

Displays all downloaded Docker images with Image ID, size, and repository details.

**Screenshot**

**Screenshot 14:** Docker Images List

![](data:image/png;base64...)

**Step 5: Run an Nginx Container**

**Command**

docker run -d --name nginx-container -p 8080:80 nginx

**Working**

* Creates a container named nginx-container.
* Maps host port 8080 to container port 80.
* Runs Nginx in detached mode.

**Screenshot**

**Screenshot 15:** Nginx Container Creation

![](data:image/png;base64...)

**Step 6: Run an Apache HTTPD Container**

**Command**

docker run -d --name httpd-container-new -p 8081:80 httpd

**Working**

Creates and runs an Apache HTTP Server container.

**Screenshot**

**Screenshot 16:** HTTPD Container Creation

![](data:image/png;base64...)

**Step 7: Run a BusyBox Container**

**Command**

docker run -dit --name busybox-container busybox

**Working**

Starts a lightweight Linux container in interactive detached mode.

**Screenshot**

**Screenshot 17:** BusyBox Container Creation

![](data:image/png;base64...)

**Step 8: Run a Node.js Container**

**Command**

docker run -dit --name node-container node

**Working**

Creates a Node.js runtime container.

**Screenshot**

**Screenshot 18:** Node Container Creation

![](data:image/png;base64...)

**Step 9: Run a Python Container**

**Command**

docker run -dit --name python-container python

**Working**

Creates a Python runtime container.

**Screenshot**

**Screenshot 19:** Python Container Creation

![](data:image/png;base64...)

**Step 10: Run Jenkins Container**

**Command**

docker run -d --name jenkins-container -p 8082:8080 -p 50000:50000 jenkins/jenkins:lts

**Working**

Runs Jenkins CI/CD server with required port mappings.

**Screenshot**

**Screenshot 20:** Jenkins Container Creation

![](data:image/png;base64...)

**Step 11: Run MySQL Container**

**Command**

docker run -d \
--name mysql-container \
-e MYSQL\_ROOT\_PASSWORD=root123 \
-p 3306:3306 \
mysql

**Working**

Creates a MySQL database server with root password configuration.

**Screenshot**

**Screenshot 21:** MySQL Container Creation

![](data:image/png;base64...)

**Step 12: Run phpMyAdmin Container**

**Command**

docker run -d \
--name phpmyadmin-container \
--link mysql-container:db \
-p 8083:80 \
phpmyadmin/phpm yadmin

**Working**

Creates phpMyAdmin and connects it to the MySQL container.

**Screenshot**

**Screenshot 22:** phpMyAdmin Container Creation

![](data:image/png;base64...)

**Step 13: View Running Containers**

**Commands**

docker ps
docker ps -a
docker ps -l

**Working**

* docker ps → Running containers.
* docker ps -a → All containers.
* docker ps -l → Most recently created container.

**Screenshot**

**Screenshot 23:** Docker PS Output

![](data:image/png;base64...)

**Screenshot 24:** Docker PS -A Output

**Screenshot 25:** Docker PS -L Output

**Step 14: Access Nginx Container**

**Command**

docker exec -it nginx-container bash

**Commands Executed Inside Container**

hostname
pwd
ls
cat /etc/os-release
nginx -v

**Working**

Verifies:

* Container hostname
  + hostname
* Working directory
  + pwd
* File system
  + ls
* Operating System
  + cat /etc/os-release
* Nginx Version
  + Nginx -v

**Screenshot**

**Screenshot 26:** Nginx Container Inspection

![](data:image/png;base64...)

![](data:image/png;base64...)

**Step 15: Access Apache Container**

**Command**

docker exec -it httpd-container-new bash

**Commands Executed**

hostname
httpd -v

**Working**

Checks Apache server details and container information.

**Screenshot**

**Screenshot 27:** Apache Container Inspection

![](data:image/png;base64...)

![](data:image/png;base64...)

**Step 16: Access BusyBox Container**

**Command**

docker exec -it busybox-container sh

**Commands Executed**

hostname
pwd
ls
ps
date
uname -a

cat /etc/os-release

**Working**

Verifies BusyBox environment and system information.

**Screenshot**

**Screenshot 28:** BusyBox Container Inspection

![](data:image/png;base64...)

![](data:image/png;base64...)

**Step 17: Access Node Container**

**Command**

docker exec -it node-container bash

**Commands Executed**

node -v
npm -v

**Working**

Checks installed Node.js and NPM versions.

**Screenshot**

**Screenshot 29:** Node Container Inspection

![](data:image/png;base64...)

**Step 18: Access Python Container**

**Command**

docker exec -it python-container bash

**Commands Executed**

python --version
pip --version

**Working**

Verifies Python interpreter and package manager.

**Screenshot**

**Screenshot 30:** Python Container Inspection

root@dharan:~# docker exec -it python-container bash

root@5cc5a7fe9729:/#

![](data:image/png;base64...)

**Step 19: Access Jenkins Container**

**Command**

docker exec -it jenkins-container bash

**Commands Executed**

java -version
ps -ef

**Working**

Checks Java Runtime Environment and Jenkins process status.

**Screenshot**

**Screenshot 31:** Jenkins Container Inspection

![](data:image/png;base64...)

![](data:image/png;base64...)

**Step 20: Access MySQL Container**

**Command**

docker exec -it mysql-container bash

**Commands Executed**

mysql -u root -p
show databases;

**Working**

Connects to MySQL server and displays available databases.

**Screenshot**

**Screenshot 32:** MySQL Login

![](data:image/png;base64...)

**Screenshot 33:** Show Databases Output

![](data:image/png;base64...)

**To Exit From mysql**

**Run:**

exit

**Then exit from the container also:**

exit

**After returning to:**

root@dharan:~#

![](data:image/png;base64...)

**Step 21: View Container Logs**

**Commands**

docker logs nginx-container
docker logs jenkins-container

**Working**

Displays application logs generated by containers.

**Screenshot**

**Screenshot 34:** Nginx Logs

![](data:image/png;base64...)

**Screenshot 35:** Jenkins Logs

![](data:image/png;base64...)

**Step 22: Stop Containers**

**Commands**

docker stop nginx-container
docker stop httpd-container-new

**Working**

Gracefully stops running containers.

**Screenshot**

**Screenshot 36:** Container Stop Operation

![](data:image/png;base64...)

**Step 23: Start Containers**

**Commands**

docker start nginx-container
docker start httpd-container-new

**Working**

Restarts previously stopped containers.

**Screenshot**

**Screenshot 37:** Container Start Operation

![](data:image/png;base64...)

**Step 24: Restart Container**

**Command**

docker restart nginx-container

**Working**

Stops and starts the container in a single operation.

**Screenshot**

**Screenshot 38:** Container Restart Operation

![](data:image/png;base64...)

**Step 25: Kill Container**

**Command**

docker kill busybox-container

**Working**

Forcefully terminates the running container.

**Screenshot**

**Screenshot 39:** Container Kill Operation

![](data:image/png;base64...)

**Step 26: Remove Containers**

**Commands**

docker rm busybox-container
docker rm -f nginx-container httpd-container-new node-container
docker rm -f python-container

**Working**

Deletes containers from Docker host.

**Screenshot**

**Screenshot 40:** Remove Containers

![](data:image/png;base64...)

**Step 27: Remove Images**

**Commands**

docker rmi nginx
docker rmi httpd busybox node python
docker rmi -f httpd

**Working**

Removes Docker images from local storage.

**Screenshot**

**Screenshot 41:** Remove Images

![](data:image/png;base64...)

![](data:image/png;base64...)

![](data:image/png;base64...)

**Step 28: Cleanup Docker Environment**

**Commands**

docker container prune
docker image prune
docker system prune -a

**Working**

* Removes stopped containers.
* Removes unused images.
* Cleans Docker system resources.

**Screenshot**

**Screenshot 42:** Container Prune

![](data:image/png;base64...)

**Screenshot 43:** Image Prune

![](data:image/png;base64...)

**Screenshot 44:** System Prune

![](data:image/png;base64...)

**Result**

Successfully performed Docker image management, container creation, execution, inspection, logging, lifecycle management, and Docker cleanup operations using various Docker commands on Ubuntu Linux.