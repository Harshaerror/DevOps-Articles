---
title: "Setting up an Domain for my website"
seoTitle: "Domain Setup for Website"
seoDescription: "set up a domain for your website with GitLab, Docker, and Nginx configuration"
datePublished: Fri May 09 2025 13:43:15 GMT+0000 (Coordinated Universal Time)
cuid: cmagujlw9000609jp4xhj2l6d
slug: setting-up-an-domain-for-my-website
tags: javascript, web-development, reactjs, devops, gitlab, 90daysofdevops, shubhamlondhe

---

let see what i did till now after my GitLab flow i am able to run my app globally on an ec2 instance after trying and setting up an DOCKER\_PASS AND DOCKER\_USER in creating with access token

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1746781249615/b49bf091-85e2-489b-bdb3-ad8cc5e63048.png align="center")

### I always ensure for correct commands like when to used sudo permission and each syntax

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1746780685907/821af3b0-d866-4bfb-8409-cfedc1770deb.png align="center")

### After successfully running up an .gitlab-ci.yml i can

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1746780872640/bb2a9021-b1a8-47d3-a6fe-721e539b6dac.png align="center")

Able to up and run my app on instance that i assigned it to be

Here i noticed that i had not crated an secure website to do that i obviously need to set up an domain that i already purchase it from GoDaddy configured with A record and setting up an sub domain

Following above commands to Successfully received certificate from catboat with setting up an Gmail

I already had running nginx running on port 80 which i need to be stop

```powershell
sudo certbot certonly --standalone -d gitlab.harshalthorat.blog
Saving debug log to /var/log/letsencrypt/letsencrypt.log
Enter email address (used for urgent renewal and security notices)
 (Enter 'c' to cancel): c
An e-mail address or --register-unsafely-without-email must be provided.
 sudo certbot certonly --standalone -d gitlab.harshalthorat.blog
Saving debug log to /var/log/letsencrypt/letsencrypt.log
Enter email address (used for urgent renewal and security notices)
 (Enter 'c' to cancel): harshalthorat91@gmail.com

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
Please read the Terms of Service at
https://letsencrypt.org/documents/LE-SA-v1.5-February-24-2025.pdf. You must
agree in order to register with the ACME server. Do you agree?
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
(Y)es/(N)o: y

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
Would you be willing, once your first certificate is successfully issued, to
share your email address with the Electronic Frontier Foundation, a founding
partner of the Let's Encrypt project and the non-profit organization that
develops Certbot? We'd like to send you email about our work encrypting the web,
EFF news, campaigns, and ways to support digital freedom.
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
(Y)es/(N)o: y
Account registered.
Requesting a certificate for gitlab.harshalthorat.blog

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
Could not bind TCP port 80 because it is already in use by another process on
this system (such as a web server). Please stop the program in question and then
try again.
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
(R)etry/(C)ancel: r

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
Could not bind TCP port 80 because it is already in use by another process on
this system (such as a web server). Please stop the program in question and then
try again.
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
(R)etry/(C)ancel: c

 docker stop gitlab
Error response from daemon: No such container: gitlab
ubuntu@ip-172-31-10-89:~$ docker ps
CONTAINER ID   IMAGE                              COMMAND                  CREATED        STATUS        PORTS                                       NAMES
383d9774e716   trainwithshubham/node-app:latest   "node app.js"            11 hours ago   Up 11 hours   0.0.0.0:8000->8000/tcp, :::8000->8000/tcp   node-todo-cicd-web-1
b07480350f86   nginx                              "/docker-entrypoint.…"   13 hours ago   Up 13 hours   0.0.0.0:80->80/tcp, :::80->80/tcp           pedantic_jones


docker stop pedantic_jones
pedantic_jones

docker ps
CONTAINER ID   IMAGE                              COMMAND         CREATED        STATUS        PORTS                                       NAMES
383d9774e716   trainwithshubham/node-app:latest   "node app.js"   11 hours ago   Up 11 hours   0.0.0.0:8000->8000/tcp, :::8000->8000/tcp   node-todo-cicd-web-1

sudo certbot certonly --standalone -d gitlab.harshalthorat.blog
Saving debug log to /var/log/letsencrypt/letsencrypt.log
Requesting a certificate for gitlab.harshalthorat.blog

Successfully received certificate.
Certificate is saved at: /etc/letsencrypt/live/gitlab.harshalthorat.blog/fullchain.pem
Key is saved at:         /etc/letsencrypt/live/gitlab.harshalthorat.blog/privkey.pem
This certificate expires on 2025-08-07.
These files will be updated when the certificate renews.
Certbot has set up a scheduled task to automatically renew this certificate in the background.

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
If you like Certbot, please consider supporting our work by:
 * Donating to ISRG / Let's Encrypt:   https://letsencrypt.org/donate
 * Donating to EFF:                    https://eff.org/donate-le
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
```

next configu for nginx