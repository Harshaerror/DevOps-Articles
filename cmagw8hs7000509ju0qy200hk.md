---
title: "Getting Started with Docker and Docker Compose"
seoTitle: "Docker & Docker Compose"
seoDescription: " how to use Docker and Docker Compose to simplify your development workflow "
datePublished: Fri May 09 2025 14:30:36 GMT+0000 (Coordinated Universal Time)
cuid: cmagw8hs7000509ju0qy200hk
slug: getting-started-with-docker-and-docker-compose
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1746799658140/93982e17-6a24-4a9f-8c1b-013eb250a235.png
tags: docker, web-development, mongodb, nodejs, reactjs, devops, 90daysofdevops

---

Docker has transformed how developers build, ship, and run applications, making them portable and efficient. If you're new to containerization or a seasoned developer, mastering Docker and Docker Compose can simplify your workflow. This blog explores what Docker and Docker Compose are, their history, why they’re essential, and how to use them with a hands-on example. Let’s get started!

## What is Docker?

Docker is an open-source platform that uses **containerization** to package applications and their dependencies into lightweight, portable units called **containers**. Unlike virtual machines, containers share the host operating system’s kernel, making them faster and more resource-efficient.

### A Brief History of Docker

Docker began as dotCloud in 2010, founded by Kamel Founadi, Solomon Hykes, and Sebastien Pahl. Initially an internal project at dotCloud, a platform-as-a-service company, Docker drew inspiration from Linux container technologies like LXC. In March 2013, it debuted at PyCon and was released as open-source, gaining rapid popularity. By 2014, Docker replaced LXC with its own libcontainer and launched Docker Compose to manage multi-container setups. Docker Hub’s introduction enabled easy image sharing. By 2015, Docker was valued at over $1 billion, becoming a unicorn company. Today, Docker is a cornerstone of containerization, driving modern software development.

### Why Use Docker?

* **Consistency**: Ensures identical environments across development, testing, and production.
    
* **Portability**: Containers run seamlessly across different machines or cloud platforms.
    
* **Isolation**: Each container operates independently, preventing dependency conflicts.
    
* **Scalability**: Easily scale applications by deploying multiple containers.
    

## What is Docker Compose?

Docker Compose is a tool for defining and managing multi-container Docker applications. Using a YAML file, you can configure services, networks, and volumes, launching them with a single command.

### Why Use Docker Compose?

* **Simplified Management**: Orchestrates multiple containers as a unified application stack.
    
* **Local Development**: Mimics production environments on your local machine.
    
* **Reproducibility**: Share Compose files for consistent setups across teams.
    

## Prerequisites

To follow along, you’ll need:

* Docker and Docker Compose installed (Docker's official site).
    
* Basic command-line knowledge.
    

## A Practical Example: Building a Web App with Docker Compose

Let’s build a web application stack with a **Node.js backend**, **MongoDB database**, and **Nginx web server** using Docker Compose. This example showcases their combined power.

### Step 1: Project Structure

Create a directory named my-web-app with this structure:

```powershell
my-web-app/
├── backend/
│   ├── index.js
│   ├── package.json
│   └── Dockerfile
├── nginx/
│   ├── nginx.conf
│   └── Dockerfile
└── docker-compose.yml
```

### Step 2: Create the Node.js Backend

In backend/package.json:

```json
{
  "name": "backend",
  "version": "1.0.0",
  "dependencies": {
    "express": "^4.17.1",
    "mongodb": "^4.1.0"
  },
  "scripts": {
    "start": "node index.js"
  }
}
```

In backend/index.js:

```javascript
const express = require('express');
const { MongoClient } = require('mongodb');

const app = express();
const port = 3000;

app.get('/', async (req, res) => {
  const client = new MongoClient('mongodb://mongo:27017');
  await client.connect();
  const db = client.db('test');
  const message = await db.collection('messages').findOne({ id: 'welcome' });
  res.send(`Hello from Docker! Message: ${message.text}`);
  await client.close();
});

app.listen(port, () => {
  console.log(`Backend running on port ${port}`);
});
```

In backend/Dockerfile:

```dockerfile
FROM node:16
WORKDIR /app
COPY package.json .
RUN npm install
COPY . .
EXPOSE 3000
CMD ["npm", "start"]
```

### Step 3: Configure Nginx

In nginx/nginx.conf:

```nginx
server {
    listen 80;
    location / {
        proxy_pass http://backend:3000;
        proxy_set_header Host $host;
    }
}
```

In nginx/Dockerfile:

```dockerfile
FROM nginx:alpine
COPY nginx.conf /etc/nginx/conf.d/default.conf
```

### Step 4: Write the Docker Compose File

In docker-compose.yml:

```yaml
version: '3.8'
services:
  backend:
    build: ./backend
    ports:
      - "3000:3000"
    depends_on:
      - mongo
  mongo:
    image: mongo:latest
    ports:
      - "27017:27017"
    volumes:
      - mongo-data:/data/db
  nginx:
    build: ./nginx
    ports:
      - "80:80"
    depends_on:
      - backend
volumes:
  mongo-data:
```

### Step 5: Initialize the Database

Insert a sample document into MongoDB:

```bash
docker run -it --rm --network my-web-app_default mongo mongosh mongodb://mongo:27017/test --eval 'db.messages.insertOne({ id: "welcome", text: "Welcome to Docker Compose!" })'
```

### Step 6: Run the Application

In the my-web-app directory, run:

```bash
docker-compose up --build
```

Visit http://localhost in your browser to see: Hello from Docker! Message: Welcome to Docker Compose!

### Step 7: Clean Up

Stop the application with Ctrl+C and remove resources:

```bash
docker-compose down --volumes
```

## Key Takeaways

* **Docker** packages applications into portable containers.
    
* **Docker Compose** orchestrates multi-container applications effortlessly.
    
* This example demonstrated a Node.js, MongoDB, and Nginx stack.
    

## What's Next?

* Explore Docker Hub for pre-built images.
    
* Kubernetes for orchestration.
    
* Experiment with CI/CD pipelines for automated Docker deployments.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1746800046494/c0060ba8-1d61-4d7f-8b8f-6992865cd921.png align="center")