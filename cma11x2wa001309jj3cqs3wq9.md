---
title: "GitLab's Inception: Tracing the Start of a Powerful Tool - part 1"
seoTitle: "GitLab's Beginnings: The Rise of a Tool"
seoDescription: "Explore GitLab's CI/CD, project management, and deployment features. Compare with GitHub and Bitbucket in this detailed analysis"
datePublished: Mon Apr 28 2025 12:25:22 GMT+0000 (Coordinated Universal Time)
cuid: cma11x2wa001309jj3cqs3wq9
slug: gitlabs-inception-tracing-the-start-of-a-powerful-tool-part-1
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1745842938757/7c9bf691-b334-4a07-a207-d56fb6dbf81b.jpeg

---

GitLab is an all-in-one DevOps platform that lets you manage your repositories, CI/CD pipelines, secrets, runners, and deployments—everything under one roof.

## **📌 What You'll Learn**

* What is GitLab?
    
* How is GitLab different from GitHub/Bitbucket?
    
* How to use GitLab?
    
* Creating and managing projects & groups
    
* Building pipelines with `.gitlab-ci.yml`
    
* Secrets, Variables, and Artifacts
    
* Self-hosted vs SaaS Runners
    
* Deploying projects via GitLab CI/CD
    

## **🔰 What is GitLab?**

GitLab is a web-based Git repository manager with features for issue tracking, CI/CD, and more. It allows you to **plan, build, test, and deploy** in one unified platform—perfect for DevOps workflows.

## **🔄 GitLab vs GitHub vs Bitbucket**

| **Feature** | **GitLab** | **GitHub** | **Bitbucket** |
| --- | --- | --- | --- |
| CI/CD | Built-in | Third-party (e.g., Actions) | Integrated |
| Self-hosting | Yes | Limited (via GitHub Enterprise) | Yes |
| Free Private Repos | Yes | Yes | Yes |
| DevOps Lifecycle | Complete platform | Limited to code & actions | Partial |

## **🛠️ Getting Started with GitLab**

**1\. Create EC2 instance** and set up your local machine.

2.Learn how **Groups and Projects** (Repos) are structured.

`URL:` [`gitlab.com/group_name`](http://gitlab.com/harsh/node-tod-cicd)`/project_name`

`Example:` [`gitlab.com/harsh/node-tod-cicd`](http://gitlab.com/harsh/node-tod-cicd)

3.Connect to EC2 using an **SSH key**.

4.Understand how to **import GitHub repos** into GitLab using the project URL.

## **🔁 GitLab CI/CD Basics**

To set up CI/CD, create a file named `.gitlab-ci.yml` in the root of your repo.

This YAML file defines:

* **Pipeline** ➝ List of stages
    
* **Stages** ➝ Sequence of execution (e.g., build, test)
    
* **Jobs** ➝ Tasks executed inside stages
    

Sample Pipeline Flow

```yaml
stages:
  - build
  - test
  - push
  - deploy

build-job:
  stage: build
  script:
    - echo "Building..."

test-job:
  stage: test
  script:
    - echo "Running tests..."

push-job:
  stage: push
  script:
    - echo "Pushing code..."

deploy-job:
  stage: deploy
  script:
    - echo "Deploying..."
```

## **🏃 Runners in GitLab**

Runners are the agents that execute your CI/CD jobs.

* GitLab provides **shared runners** by default.
    
* You can also **self-host your own runners**.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1745584199986/a337ab23-8031-4d59-84a8-199a382e5ddf.png align="left")

you can copy and paste this script given at top right corner inside your server with after

```yaml
sudo su 
// gives you super user access
//after this cmd copy that scrpit provided by how to install gitlab runners? inside Register runners
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1745585930651/7a24defa-8179-435c-a92e-7667fa5df678.png align="left")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1745587662921/dca02450-e934-4251-8896-8e4bff16f764.png align="left")

## **🔐 Variables & Secrets**

* GitLab supports both **inbuilt** and **user-defined variables**.
    
* Secrets can be masked and encrypted for safe usage.
    
* Use these variables in your `.gitlab-ci.yml` for dynamic configurations.
    

## **📦 Artifacts**

Artifacts are the **outputs of your CI/CD jobs**.

Examples:

* Logs
    
* Reports
    
* Compiled binaries
    

They can be shared between jobs and stages for better traceability.

## **🔖 Branching Strategy & Tagging**

you can follow a simple branching model:

> main → dev → prod → feature

You can also **create tags** during pipeline runs to mark versions based on releases or environments.