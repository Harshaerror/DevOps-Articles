---
title: "Contributing to Open Source"
datePublished: Wed Apr 30 2025 12:22:51 GMT+0000 (Coordinated Universal Time)
cuid: cma3wpjuy003w09ju07n1a4bq
slug: contributing-to-open-source

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
        
4. **Create a Pull Request**:
    
    * Go to the repository page, compare your fork's commits, and submit a pull request to merge your changes back into the project.
        

## Alternative Forking Method

* Click "Fork" on the repository page.
    
* Copy and paste the URL, then use git clone &lt;URL&gt; to work locally.
    

By following these steps, you can contribute effectively to open source projects and help improve them for everyone.