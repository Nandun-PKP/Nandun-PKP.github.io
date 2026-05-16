---
layout: default
title: Blog Posts
---

[⬅️ Back to Home](index.md)

# 📝 Technical Blog Posts

### ☁️ Understanding Port Mapping: How to Connect to a Remote Cloud Server
A simplified guide on how communication works between your laptop and a server in the USA, covering Port Mapping and Firewalls.
* **Tags:** #Cloud #Networking #Docker
* [Read Full Article](#article-1)

---

### 🛡️ How to Start Ethical Hacking?
A beginner's guide on how to enter the world of Cyber Security.
*(Coming Soon)*

---

<a name="article-1"></a>
## ☁️ How "Ports" Work When Connecting to a Real Cloud Server 🖥️

Have you ever wondered what actually happens when you connect to a server located in the USA from your laptop? Today, we are diving deep into how this communication is handled using **Port Mapping** and **Firewalls**.

In professional Cloud environments like **AWS, Azure, or Google Cloud**, security and management are handled through two primary methods:

### 1. Building a "Secure Bridge" via Firewall (The Gateway) 🛡️
Every Cloud server sits behind a Firewall or a Security Group. To enhance security, we often use a strategy like this:
* Inside the server, the **SSH service** might be running on the standard **Port 22**.
* However, we only expose **Port 2222** to the outside world.
* When someone connects via Port 2222 over the internet, the Firewall silently redirects that connection to the internal Port 22. This keeps the actual service port hidden from automated bots.

### 2. Using Docker Containers (Microservices) 📦
Imagine you are running 10 different Ubuntu instances using **Docker** inside a single server. Each instance wants to use Port 22 for SSH. How do you connect to a specific one?
* We assign different external ports (e.g., 2221, 2222, 2223) on the **Host** machine.
* Each host port is then **"mapped"** to Port 22 of the corresponding container.

### How does this work internally? 🤔
This process is powered by **Network Address Translation (NAT)**. We provide a specific instruction to the server's routing table: 
> *"Any traffic arriving at Port 2222 must be redirected to Port 22."*

### Why go through all this trouble? 🤷‍♂️
* **Security:** You can keep common ports like 22 closed to the public to prevent brute-force attacks.
* **Scalability:** You can manage multiple services or servers through a single public IP address.
* **Organization:** It allows for much cleaner network administration.

If you are currently building a Docker lab on your laptop, you are practicing the exact same technology used by the world's largest cloud providers! 🚀

**#CloudComputing #CyberSecurity #Docker #DevOps #Networking #CloudEngineering #WebDevelopment**
