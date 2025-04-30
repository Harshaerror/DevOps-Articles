---
title: "Contributing to Open Source"
datePublished: Wed Apr 30 2025 12:22:51 GMT+0000 (Coordinated Universal Time)
cuid: cma3wpjuy003w09ju07n1a4bq
slug: contributing-to-open-source

---

Open source projects are a great way to collaborate, learn, and give back to the community. Contributing to an open source repository involves a series of steps to ensure your changes are effectively integrated. Here's a guide based on common practices:

## Steps to Contribute

1. **Clone the Repository**: Start by creating a local copy of the initial repository using git clone &lt;URL&gt;.
    
2. **Work on Changes**: Navigate to the project directory with cd backend/, make your changes, and prepare them for a pull request (e.g., for larger changes like features or bug fixes).
    
3. **Sync with Upstream**:
    
    * Set up the original repository as a remote: git remote add upstream &lt;URL&gt;.
        
    * Fetch updates: git fetch upstream.
        
    * Checkout and merge the main branch: git checkout main followed by git merge upstream/main.
        
4. **Make Changes**:
    
    * Check the status of your changes: git status.
        
    * Review differences: git diff (press q to exit view).
        
    * Stage all changes: git add -A.
        
    * Commit with a message: git commit -m "message".
        
    * Push to your fork: git push.
        
5. **Create a Pull Request**:
    
    * Go to the repository page, compare your fork's commits, and submit a pull request to merge your changes back into the project.
        

## Alternative Forking Method

* Click "Fork" on the repository page.
    
* Copy and paste the URL, then use git clone &lt;URL&gt; to work locally.
    

By following these steps, you can contribute effectively to open source projects and help improve them for everyone.