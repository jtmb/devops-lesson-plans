<h1 align="center">
  <a href="https://github.com/jtmb">
    <img src="https://avatars.githubusercontent.com/u/86915618?v=4" alt="Logo" width="" height="125">
  </a>
</h1>

<div align="center">
  <b>DevOps 101 Learning Path</b> – A guided introduction to DevOps fundamentals.
  <br />
  <br />
  <a href="https://github.com/jtmb/devops-101/issues/new?assignees=&labels=bug&title=bug%3A+">Report a Bug</a>
  ·
  <a href="https://github.com/jtmb/devops-101/issues/new?assignees=&labels=enhancement&template=02_FEATURE_REQUEST.md&title=feat%3A+">Request a Feature</a>
</div>
<br>

<details open="open">
<summary>Table of Contents</summary>

- [About](#about)
- [Prerequisites](#prerequisites)
- [Learning Roadmap](#learning-roadmap)
    - [WSL Setup](#wsl-setup)
    - [Git & Version Control](#git--version-control)
    - [AWS EC2](#aws-ec2)
    - [Docker](#docker)
    - [Ansible](#ansible)
- [What is DevOps?](#what-is-devops)
- [Contributing](#contributing)
- [License](#license)

</details>
<br>

---

### <h1>About </h1>

This repository is a **beginner-friendly DevOps learning project**.  
It provides a structured way to learn core DevOps skills by setting up:

- A local development environment with **WSL (Ubuntu)**
- Source control with **Git & GitHub**
- A remote server with **AWS EC2**
- Containerization with **Docker**
- Configuration management with **Ansible**

It also includes reference material explaining **what DevOps is**, with diagrams, resources, and best practices.

---

### <h1>Prerequisites</h1>

Before starting, ensure you have:

- **Windows 10/11** with WSL2 installed (Ubuntu preferred)  
- A **GitHub account**  
- An **AWS account** (for EC2 free tier)  
- Basic command-line familiarity  

---

### <h1>Learning Roadmap <span style="color: yellow;">(Under construction 🚧)</span></h1>

#### WSL Setup
- Install Ubuntu via WSL2
- Learn differences between local (WSL) and cloud (EC2) environments

#### Git & Version Control
- Install Git on WSL
- Configure Git with SSH keys
- Clone, commit, and push to a repository

#### AWS EC2
- Launch a free-tier Ubuntu EC2 instance
- Connect with SSH
- Compare EC2 with WSL environments

#### Docker
- Install Docker on EC2
- Run test containers (`hello-world`, `nginx`)
- Expose ports and access services

#### Ansible
- Install Ansible on WSL
- Create an inventory file with EC2 IP
- Run ad-hoc commands
- Write a basic playbook to install Nginx

---

### <h1>What is DevOps?</h1>

DevOps is a **culture, set of practices, and collection of tools** that bridge software development (Dev) and IT operations (Ops).  

📚 [See the DevOps Packet](docs/what-is-devops.md) for diagrams, examples, and links to resources.  

---

### <h1>Contributing</h1>

Contributions, feedback, and suggestions are welcome!  
Feel free to open an [issue](https://github.com/jtmb/devops-101/issues) or submit a pull request.

---

### <h1>License</h1>

Distributed under the MIT License.  
See [LICENSE](LICENSE) for details.
