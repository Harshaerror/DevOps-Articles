---
title: "Contributing to Open Source"
seoTitle: "Get Started with Open Source"
seoDescription: "Contribute to open-source projects: clone, create pull requests, and enhance skills while helping the community"
datePublished: Wed Apr 30 2025 12:22:51 GMT+0000 (Coordinated Universal Time)
cuid: cma3wpjuy003w09ju07n1a4bq
slug: contributing-to-open-source
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1746471111788/da6e4815-4605-4a06-ac39-9b176d20ec60.jpeg
tags: linux, docker, github, opensource, git, 90daysofdevops, shubhamlondhe

---

Open source projects are a great way to collaborate, learn, and give back to the community. Contributing to an open source repository involves a series of steps to ensure your changes are effectively integrated. Here's a guide based on common practices:

## Steps to Contribute

1. **Clone the Repository**: Start by creating a local copy of the initial repository using git clone &lt;URL&gt;.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1746018370703/6dfd1abf-6b0a-4b4a-ba10-3c3000de61af.png align="center")

```bash


git clone "url"  
also fork this repo to your github repository to change in my side

//create folder in your instance 
mkdir git-demo
//to login with your github account
git config --global user.name "your_Github_name"
git config --global user.email "email"
ls
cd wonderlust/


//this command is to ensure on which User Branch you will work with
git remote -v
origin  https://github.com/krishnaacharyaa/wanderlust.git (fetch)
origin  https://github.com/krishnaacharyaa/wanderlust.git (push)

//work on frok repo to conduct my code so i need to open it in my repo
cd ..
ubuntu@ip-172-31-0-171:~/git-demo$ mkdir my-repo
ubuntu@ip-172-31-0-171:~/git-demo$ cd my-repo/

ubuntu@ip-172-31-0-171:~/git-demo/my-repo$ git clone https://github.com/Harshaerror/wanderlust.git
Cloning into 'wanderlust'...
remote: Enumerating objects: 3822, done.
remote: Counting objects: 100% (545/545), done.
remote: Compressing objects: 100% (78/78), done.
remote: Total 3822 (delta 493), reused 467 (delta 467), pack-reused 3277 (from 1)
Receiving objects: 100% (3822/3822), 1.57 MiB | 2.22 MiB/s, done.
Resolving deltas: 100% (2464/2464), done.


ubuntu@ip-172-31-0-171:~/git-demo/my-repo$ cd wanderlust/

ubuntu@ip-172-31-0-171:~/git-demo/my-repo/wanderlust$ ls
LICENSE  README.md  backend  frontend  package.json

ubuntu@ip-172-31-0-171:~/git-demo/my-repo/wanderlust$ git remote -v
origin  https://github.com/Harshaerror/wanderlust.git (fetch)
origin  https://github.com/Harshaerror/wanderlust.git (push)

// here's a check for my repo after forking as username mention always ensure before conduct 


```

1. **Work on Changes**: Navigate to the project directory with cd backend/, make your changes, and prepare them for a pull request (e.g., for larger changes like features or bug fixes).
    
2. **Sync with Upstream**:
    
    * Set up the original repository as a remote: git remote add upstream &lt;URL&gt;.
        
    * Fetch updates: git fetch upstream.
        
    * Checkout and merge the main branch: git checkout main followed by git merge upstream/main.
        
3. **Make Changes**:
    
    * Check the status of your changes: git status.
        
    * Review differences: git diff (press q to exit view).
        
    * Stage all changes: git add -A.
        
    * Commit with a message: git commit -m "message".
        
    * Push to your fork: git push.
        

```bash
//let assume u change something like
vim README.md 
git status 
git add README.md
git diff
    
```

1. **Create a Pull Request**:
    
    * Go to the repository page, compare your fork's commits, and submit a pull request to merge your changes back into the project.
        

## Alternative Forking Method

* Click "Fork" on the repository page.
    
* Copy and paste the URL, then use git clone &lt;URL&gt; to work locally.
    

By following these steps, you can contribute effectively to open source projects and help improve them for everyone.

keep main branch as it is always remember

create different branch for our changes in my case i created branch as devops

```bash
//this cmd create an branch name and switch to that branch
git checkout -b devops 
vim README.md
git push origin devops


ubuntu@ip-172-31-0-171:~/git-demo/my-repo/wanderlust$ git checkout branch
error: pathspec 'branch' did not match any file(s) known to git
ubuntu@ip-172-31-0-171:~/git-demo/my-repo/wanderlust$ git checkout devops
error: pathspec 'devops' did not match any file(s) known to git
ubuntu@ip-172-31-0-171:~/git-demo/my-repo/wanderlust$ git checkout -b devops
Switched to a new branch 'devops'
ubuntu@ip-172-31-0-171:~/git-demo/my-repo/wanderlust$ git push origin devops
Total 0 (delta 0), reused 0 (delta 0), pack-reused 0
remote:
remote: Create a pull request for 'devops' on GitHub by visiting:
remote:      https://github.com/Harshaerror/wanderlust/pull/new/devops
remote:
To https://github.com/Harshaerror/wanderlust.git
 * [new branch]      devops -> devops
ubuntu@ip-172-31-0-171:~/git-demo/my-repo/wanderlust$ vim README.md
ubuntu@ip-172-31-0-171:~/git-demo/my-repo/wanderlust$ git checkout devops
M       README.md
Already on 'devops'
ubuntu@ip-172-31-0-171:~/git-demo/my-repo/wanderlust$ git diff
ubuntu@ip-172-31-0-171:~/git-demo/my-repo/wanderlust$ git status
On branch devops
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   README.md

ubuntu@ip-172-31-0-171:~/git-demo/my-repo/wanderlust$ git push origin devops
Everything up-to-date
ubuntu@ip-172-31-0-171:~/git-demo/my-repo/wanderlust$ vim README.md
ubuntu@ip-172-31-0-171:~/git-demo/my-repo/wanderlust$ git diff
diff --git a/README.md b/README.md
index b50086e..37819c5 100644
--- a/README.md
+++ b/README.md
@@ -1,7 +1,7 @@
 <div>
   <h1>Wanderlust</h1>
   <h2>The Ultimate Travel Blog 🌍✈️ for You </h2>
-  <h3>this branch is created by harshal name as devops for docker file <h3>
+  <h3>this branch is created by harshal name as devops for docker file </h3>
 </div>

 ![Preview Image](https://github.com/krishnaacharyaa/wanderlust/assets/116620586/17ba9da6-225f-481d-87c0-5d5a010a9538)
ubuntu@ip-172-31-0-171:~/git-demo/my-repo/wanderlust$ git pu
pull   push
ubuntu@ip-172-31-0-171:~/git-demo/my-repo/wanderlust$ git push origin devops
Everything up-to-date
ubuntu@ip-172-31-0-171:~/git-demo/my-repo/wanderlust$ git add README.md
ubuntu@ip-172-31-0-171:~/git-demo/my-repo/wanderlust$ git push origin devops
Everything up-to-date
ubuntu@ip-172-31-0-171:~/git-demo/my-repo/wanderlust$ git pull origin devops
From https://github.com/Harshaerror/wanderlust
 * branch            devops     -> FETCH_HEAD
Already up to date.
ubuntu@ip-172-31-0-171:~/git-demo/my-repo/wanderlust$ git status
On branch devops
Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   README.md

ubuntu@ip-172-31-0-171:~/git-demo/my-repo/wanderlust$ git add -A
ubuntu@ip-172-31-0-171:~/git-demo/my-repo/wanderlust$ git commit -m "README.md"
[devops 021b9a4] README.md
 1 file changed, 1 insertion(+)
ubuntu@ip-172-31-0-171:~/git-demo/my-repo/wanderlust$ git push origin devops
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 366 bytes | 366.00 KiB/s, done.
Total 3 (delta 2), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (2/2), completed with 2 local objects.
To https://github.com/Harshaerror/wanderlust.git
   778bec3..021b9a4  devops -> devops
ubuntu@ip-172-31-0-171:~/git-demo/my-repo/wanderlust$ git diff
ubuntu@ip-172-31-0-171:~/git-demo/my-repo/wanderlust$ git status
On branch devops
nothing to commit, working tree clean
```

create personal access token to access branch

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1746077831540/43370f40-f5dd-4a18-abc7-85474acbce6b.png align="center")

after used command

```bash
git remote set-url origin https://PAT@github.com/Harshaerror/wanderlust.git
```

creating Docker file

```bash
ubuntu@ip-172-31-0-171:~/git-demo/my-repo/wanderlust/backend$ vim Dockerfile
ubuntu@ip-172-31-0-171:~/git-demo/my-repo/wanderlust/backend$ docker build -t backend
Command 'docker' not found, but can be installed with:
sudo snap install docker         # version 27.5.1, or
sudo apt  install docker.io      # version 26.1.3-0ubuntu1~24.04.1
sudo apt  install podman-docker  # version 4.9.3+ds1-1ubuntu0.2
See 'snap info docker' for additional versions.
ubuntu@ip-172-31-0-171:~/git-demo/my-repo/wanderlust/backend$ docker build -t backend .
Command 'docker' not found, but can be installed with:
sudo snap install docker         # version 27.5.1, or
sudo apt  install docker.io      # version 26.1.3-0ubuntu1~24.04.1
sudo apt  install podman-docker  # version 4.9.3+ds1-1ubuntu0.2
See 'snap info docker' for additional versions.
ubuntu@ip-172-31-0-171:~/git-demo/my-repo/wanderlust/backend$ sudo docker build -t backend .
sudo: docker: command not found
ubuntu@ip-172-31-0-171:~/git-demo/my-repo/wanderlust/backend$ sudo apt install docker.io docker-compose -y
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
The following additional packages will be installed:
  bridge-utils containerd dns-root-data dnsmasq-base pigz python3-compose python3-docker python3-dockerpty python3-docopt python3-dotenv python3-texttable
  python3-websocket runc ubuntu-fan
Suggested packages:
  ifupdown aufs-tools cgroupfs-mount | cgroup-lite debootstrap docker-buildx docker-compose-v2 docker-doc rinse zfs-fuse | zfsutils
The following NEW packages will be installed:
  bridge-utils containerd dns-root-data dnsmasq-base docker-compose docker.io pigz python3-compose python3-docker python3-dockerpty python3-docopt
  python3-dotenv python3-texttable python3-websocket runc ubuntu-fan
0 upgraded, 16 newly installed, 0 to remove and 44 not upgraded.
Need to get 78.9 MB of archives.
After this operation, 303 MB of additional disk space will be used.
Get:1 http://ap-south-1.ec2.archive.ubuntu.com/ubuntu noble/universe amd64 pigz amd64 2.8-1 [65.6 kB]
Get:2 http://ap-south-1.ec2.archive.ubuntu.com/ubuntu noble/main amd64 bridge-utils amd64 1.7.1-1ubuntu2 [33.9 kB]
Get:3 http://ap-south-1.ec2.archive.ubuntu.com/ubuntu noble-updates/main amd64 runc amd64 1.1.12-0ubuntu3.1 [8599 kB]
Get:4 http://ap-south-1.ec2.archive.ubuntu.com/ubuntu noble-updates/main amd64 containerd amd64 1.7.24-0ubuntu1~24.04.2 [37.0 MB]
Get:5 http://ap-south-1.ec2.archive.ubuntu.com/ubuntu noble-updates/main amd64 dns-root-data all 2024071801~ubuntu0.24.04.1 [5918 B]
Get:6 http://ap-south-1.ec2.archive.ubuntu.com/ubuntu noble/main amd64 dnsmasq-base amd64 2.90-2build2 [375 kB]
Get:7 http://ap-south-1.ec2.archive.ubuntu.com/ubuntu noble/universe amd64 python3-websocket all 1.7.0-1 [38.1 kB]
Get:8 http://ap-south-1.ec2.archive.ubuntu.com/ubuntu noble-updates/universe amd64 python3-docker all 5.0.3-1ubuntu1.1 [89.1 kB]
Get:9 http://ap-south-1.ec2.archive.ubuntu.com/ubuntu noble/universe amd64 python3-dockerpty all 0.4.1-5 [11.4 kB]
Get:10 http://ap-south-1.ec2.archive.ubuntu.com/ubuntu noble/universe amd64 python3-docopt all 0.6.2-6 [26.1 kB]
Get:11 http://ap-south-1.ec2.archive.ubuntu.com/ubuntu noble/universe amd64 python3-dotenv all 1.0.1-1 [22.3 kB]
Get:12 http://ap-south-1.ec2.archive.ubuntu.com/ubuntu noble/universe amd64 python3-texttable all 1.6.7-1 [11.0 kB]
Get:13 http://ap-south-1.ec2.archive.ubuntu.com/ubuntu noble/universe amd64 python3-compose all 1.29.2-6ubuntu1 [84.6 kB]
Get:14 http://ap-south-1.ec2.archive.ubuntu.com/ubuntu noble/universe amd64 docker-compose all 1.29.2-6ubuntu1 [14.0 kB]
Get:15 http://ap-south-1.ec2.archive.ubuntu.com/ubuntu noble-updates/universe amd64 docker.io amd64 26.1.3-0ubuntu1~24.04.1 [32.4 MB]
Get:16 http://ap-south-1.ec2.archive.ubuntu.com/ubuntu noble/universe amd64 ubuntu-fan all 0.12.16 [35.2 kB]
Fetched 78.9 MB in 1s (62.0 MB/s)
Preconfiguring packages ...
Selecting previously unselected package pigz.
(Reading database ... 101159 files and directories currently installed.)
Preparing to unpack .../00-pigz_2.8-1_amd64.deb ...
Unpacking pigz (2.8-1) ...
Selecting previously unselected package bridge-utils.
Preparing to unpack .../01-bridge-utils_1.7.1-1ubuntu2_amd64.deb ...
Unpacking bridge-utils (1.7.1-1ubuntu2) ...
Selecting previously unselected package runc.
Preparing to unpack .../02-runc_1.1.12-0ubuntu3.1_amd64.deb ...
Unpacking runc (1.1.12-0ubuntu3.1) ...
Selecting previously unselected package containerd.
Preparing to unpack .../03-containerd_1.7.24-0ubuntu1~24.04.2_amd64.deb ...
Unpacking containerd (1.7.24-0ubuntu1~24.04.2) ...
Selecting previously unselected package dns-root-data.
Preparing to unpack .../04-dns-root-data_2024071801~ubuntu0.24.04.1_all.deb ...
Unpacking dns-root-data (2024071801~ubuntu0.24.04.1) ...
Selecting previously unselected package dnsmasq-base.
Preparing to unpack .../05-dnsmasq-base_2.90-2build2_amd64.deb ...
Unpacking dnsmasq-base (2.90-2build2) ...
Selecting previously unselected package python3-websocket.
Preparing to unpack .../06-python3-websocket_1.7.0-1_all.deb ...
Unpacking python3-websocket (1.7.0-1) ...
Selecting previously unselected package python3-docker.
Preparing to unpack .../07-python3-docker_5.0.3-1ubuntu1.1_all.deb ...
Unpacking python3-docker (5.0.3-1ubuntu1.1) ...
Selecting previously unselected package python3-dockerpty.
Preparing to unpack .../08-python3-dockerpty_0.4.1-5_all.deb ...
Unpacking python3-dockerpty (0.4.1-5) ...
Selecting previously unselected package python3-docopt.
Preparing to unpack .../09-python3-docopt_0.6.2-6_all.deb ...
Unpacking python3-docopt (0.6.2-6) ...
Selecting previously unselected package python3-dotenv.
Preparing to unpack .../10-python3-dotenv_1.0.1-1_all.deb ...
Unpacking python3-dotenv (1.0.1-1) ...
Selecting previously unselected package python3-texttable.
Preparing to unpack .../11-python3-texttable_1.6.7-1_all.deb ...
Unpacking python3-texttable (1.6.7-1) ...
Selecting previously unselected package python3-compose.
Preparing to unpack .../12-python3-compose_1.29.2-6ubuntu1_all.deb ...
Unpacking python3-compose (1.29.2-6ubuntu1) ...
Selecting previously unselected package docker-compose.
Preparing to unpack .../13-docker-compose_1.29.2-6ubuntu1_all.deb ...
Unpacking docker-compose (1.29.2-6ubuntu1) ...
Selecting previously unselected package docker.io.
Preparing to unpack .../14-docker.io_26.1.3-0ubuntu1~24.04.1_amd64.deb ...
Unpacking docker.io (26.1.3-0ubuntu1~24.04.1) ...
Selecting previously unselected package ubuntu-fan.
Preparing to unpack .../15-ubuntu-fan_0.12.16_all.deb ...
Unpacking ubuntu-fan (0.12.16) ...
Setting up python3-dotenv (1.0.1-1) ...
Setting up python3-texttable (1.6.7-1) ...
Setting up python3-docopt (0.6.2-6) ...
Setting up dnsmasq-base (2.90-2build2) ...
Setting up runc (1.1.12-0ubuntu3.1) ...
Setting up dns-root-data (2024071801~ubuntu0.24.04.1) ...
Setting up bridge-utils (1.7.1-1ubuntu2) ...
Setting up pigz (2.8-1) ...
Setting up containerd (1.7.24-0ubuntu1~24.04.2) ...
Created symlink /etc/systemd/system/multi-user.target.wants/containerd.service → /usr/lib/systemd/system/containerd.service.
Setting up python3-websocket (1.7.0-1) ...
Setting up python3-dockerpty (0.4.1-5) ...
Setting up ubuntu-fan (0.12.16) ...
Created symlink /etc/systemd/system/multi-user.target.wants/ubuntu-fan.service → /usr/lib/systemd/system/ubuntu-fan.service.
Setting up python3-docker (5.0.3-1ubuntu1.1) ...
Setting up docker.io (26.1.3-0ubuntu1~24.04.1) ...
info: Selecting GID from range 100 to 999 ...
info: Adding group `docker' (GID 113) ...
Created symlink /etc/systemd/system/multi-user.target.wants/docker.service → /usr/lib/systemd/system/docker.service.
Created symlink /etc/systemd/system/sockets.target.wants/docker.socket → /usr/lib/systemd/system/docker.socket.
Setting up python3-compose (1.29.2-6ubuntu1) ...
Setting up docker-compose (1.29.2-6ubuntu1) ...
Processing triggers for dbus (1.14.10-4ubuntu4.1) ...
Processing triggers for man-db (2.12.0-4build2) ...
Scanning processes...
Scanning candidates...
Scanning linux images...

Pending kernel upgrade!
Running kernel version:
  6.8.0-1024-aws
Diagnostics:
  The currently running kernel version is not the expected kernel version 6.8.0-1027-aws.

Restarting the system to load the new kernel will not be handled automatically, so you should consider rebooting.

Restarting services...

Service restarts being deferred:
 /etc/needrestart/restart.d/dbus.service
 systemctl restart networkd-dispatcher.service
 systemctl restart systemd-logind.service
 systemctl restart unattended-upgrades.service

No containers need to be restarted.

User sessions running outdated binaries:
 ubuntu @ session #136: sshd[4468]
 ubuntu @ user manager service: systemd[4473]

No VM guests are running outdated hypervisor (qemu) binaries on this host.
ubuntu@ip-172-31-0-171:~/git-demo/my-repo/wanderlust/backend$ docker build -t backend .
DEPRECATED: The legacy builder is deprecated and will be removed in a future release.
            Install the buildx component to build images with BuildKit:
            https://docs.docker.com/go/buildx/

permission denied while trying to connect to the Docker daemon socket at unix:///var/run/docker.sock: Post "http://%2Fvar%2Frun%2Fdocker.sock/v1.45/build?buildargs=%7B%7D&cachefrom=%5B%5D&cgroupparent=&cpuperiod=0&cpuquota=0&cpusetcpus=&cpusetmems=&cpushares=0&dockerfile=Dockerfile&labels=%7B%7D&memory=0&memswap=0&networkmode=default&rm=1&shmsize=0&t=backend&target=&ulimits=%5B%5D&version=1": dial unix /var/run/docker.sock: connect: permission denied
ubuntu@ip-172-31-0-171:~/git-demo/my-repo/wanderlust/backend$ sudo docker build -t backend .
DEPRECATED: The legacy builder is deprecated and will be removed in a future release.
            Install the buildx component to build images with BuildKit:
            https://docs.docker.com/go/buildx/

Sending build context to Docker daemon  116.7kB
Step 1/7 : FROM node:"21"
21: Pulling from library/node
c6cf28de8a06: Pull complete
891494355808: Pull complete
6582c62583ef: Pull complete
bf2c3e352f3d: Pull complete
2b542796ccab: Pull complete
4684276225df: Pull complete
08750d53428e: Pull complete
5d3106ce01c3: Pull complete
Digest: sha256:4b232062fa976e3a966c49e9b6279efa56c8d207a67270868f51b3d155c4e33d
Status: Downloaded newer image for node:21
 ---> 5c8697e82213
Step 2/7 : WORKDIR /app
 ---> Running in 7b1ba611f159
 ---> Removed intermediate container 7b1ba611f159
 ---> d6fda89e39c1
Step 3/7 : COPY . .
 ---> d7f243cd0e55
Step 4/7 : RUN npm i
 ---> Running in e258a3f23bd4
npm WARN deprecated inflight@1.0.6: This module is not supported, and leaks memory. Do not use it. Check out lru-cache if you want a good and tested way to coalesce async requests by a key value, which is much more comprehensive and powerful.
npm WARN deprecated @types/mongoose@5.11.97: Mongoose publishes its own types, so you do not need to install this package.
npm WARN deprecated @types/redis@4.0.11: This is a stub types definition. redis provides its own type definitions, so you do not need this installed.
npm WARN deprecated @types/ioredis@5.0.0: This is a stub types definition. ioredis provides its own type definitions, so you do not need this installed.
npm WARN deprecated glob@7.2.3: Glob versions prior to v9 are no longer supported
npm WARN deprecated superagent@8.1.2: Please upgrade to v9.0.0+ as we have fixed a public vulnerability with formidable dependency. Note that v9.0.0+ requires Node.js v14.18.0+. See https://github.com/ladjs/superagent/pull/1800 for insight. This project is supported and maintained by the team at Forward Email @ https://forwardemail.net
npm notice
npm notice New major version of npm available! 10.5.0 -> 11.3.0
npm notice Changelog: <https://github.com/npm/cli/releases/tag/v11.3.0>
npm notice Run `npm install -g npm@11.3.0` to update!
npm notice

added 720 packages, and audited 721 packages in 4m

122 packages are looking for funding
  run `npm fund` for details

3 low severity vulnerabilities

To address all issues, run:
  npm audit fix

Run `npm audit` for details.
 ---> Removed intermediate container e258a3f23bd4
 ---> 4d8879ca78c7
Step 5/7 : COPY .env.sample .env
 ---> 812a39a944ee
Step 6/7 : EXPOSE 5000
 ---> Running in 727f21a89a76
 ---> Removed intermediate container 727f21a89a76
 ---> 48854f9cddce
Step 7/7 : CMD ["NPM" , "START"]
 ---> Running in 64e4fee4d6c4
 ---> Removed intermediate container 64e4fee4d6c4
 ---> 73a3a6c008f5
Successfully built 73a3a6c008f5
Successfully tagged backend:latest
ubuntu@ip-172-31-0-171:~/git-demo/my-repo/wanderlust/backend$ docker run -d -p 27017:27017 --name mongo mongo:latest
docker: permission denied while trying to connect to the Docker daemon socket at unix:///var/run/docker.sock: Head "http://%2Fvar%2Frun%2Fdocker.sock/_ping": dial unix /var/run/docker.sock: connect: permission denied.
See 'docker run --help'.
ubuntu@ip-172-31-0-171:~/git-demo/my-repo/wanderlust/backend$ sudo docker run -d -p 27017:27017 --name mongo mongo:latest
Unable to find image 'mongo:latest' locally
latest: Pulling from library/mongo
2726e237d1a3: Pull complete
4113c9f6bc12: Pull complete
6bd25e6544db: Pull complete
114959114e76: Pull complete
74e29de52e16: Pull complete
a7aa415a3894: Pull complete
b4c1b5279c53: Pull complete
2d3498acb5d9: Pull complete
Digest: sha256:cc62438c8ef61ce02f89b4f7c026e735df4580e8cd8857980d12e0eae73bf044
Status: Downloaded newer image for mongo:latest
65375d8dc1815fa7175b7b288f7da935b80cdbb126c35db04bb4af42b5cc047a
ubuntu@ip-172-31-0-171:~/git-demo/my-repo/wanderlust/backend$ docker ps
permission denied while trying to connect to the Docker daemon socket at unix:///var/run/docker.sock: Get "http://%2Fvar%2Frun%2Fdocker.sock/v1.45/containers/json": dial unix /var/run/docker.sock: connect: permission denied
ubuntu@ip-172-31-0-171:~/git-demo/my-repo/wanderlust/backend$ sudo docker ps
CONTAINER ID   IMAGE          COMMAND                  CREATED          STATUS          PORTS                                           NAMES
65375d8dc181   mongo:latest   "docker-entrypoint.s…"   48 seconds ago   Up 47 seconds   0.0.0.0:27017->27017/tcp, :::27017->27017/tcp   mongo
ubuntu@ip-172-31-0-171:~/git-demo/my-repo/wanderlust/backend$

ubuntu@ip-172-31-0-171:~/git-demo/my-repo/wanderlust/backend$ sudo docker images
REPOSITORY   TAG       IMAGE ID       CREATED          SIZE
backend      latest    73a3a6c008f5   13 minutes ago   1.45GB
mongo        latest    6595a4d1b15f   2 weeks ago      888MB
node         21        5c8697e82213   11 months ago    1.1GB
ubuntu@ip-172-31-0-171:~/git-demo/my-repo/wanderlust/backend$ sudo docker run -d -p 5000:5000 --name:backend backend:latest
unknown flag: --name:backend
See 'docker run --help'.
ubuntu@ip-172-31-0-171:~/git-demo/my-repo/wanderlust/backend$ sudo docker run -d -p 5000:5000 --name backend backend:latest
77d0a50f8fb9e5e3d6d61a087698dfa732d5b28a9cfca295c435d17439679277
ubuntu@ip-172-31-0-171:~/git-demo/my-repo/wanderlust/backend$ sudo docker ps
CONTAINER ID   IMAGE          COMMAND                  CREATED         STATUS         PORTS                                           NAMES
65375d8dc181   mongo:latest   "docker-entrypoint.s…"   8 minutes ago   Up 8 minutes   0.0.0.0:27017->27017/tcp, :::27017->27017/tcp   mongo
ubuntu@ip-172-31-0-171:~/git-demo/my-repo/wanderlust/backend$ cd ..
ubuntu@ip-172-31-0-171:~/git-demo/my-repo/wanderlust$ ls
LICENSE  README.md  backend  frontend  package.json
ubuntu@ip-172-31-0-171:~/git-demo/my-repo/wanderlust$ cd frontend/
ubuntu@ip-172-31-0-171:~/git-demo/my-repo/wanderlust/frontend$ vim Dockerfile
ubuntu@ip-172-31-0-171:~/git-demo/my-repo/wanderlust/frontend$ sudo docker build -t frontend .
```