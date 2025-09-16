### **Prerequisites**

* WSL2 with Ubuntu already installed (done ✅)
* AWS account created and verified
* GitHub (or GitLab/Bitbucket) account created

---

## **Lesson 1 – Introduction to DevOps**

* **Goal:** Understand what DevOps means (culture + tools + automation).
* **Topics to Cover:**

  * What DevOps is (collaboration between Dev & Ops).
  * Local dev environments vs. remote servers.
  * Key tools in the DevOps toolbox (Git, CI/CD, Containers, Configuration Management, Cloud).

---

## **Lesson 2 – Git Basics & Version Control**

* **Goal:** Learn how to use Git for version control in WSL.
* **Steps:**

  1. Install Git on WSL:

     ```bash
     sudo apt update && sudo apt install git -y
     ```
  2. Configure Git:

     ```bash
     git config --global user.name "Your Name"
     git config --global user.email "your@email.com"
     ```
  3. Generate SSH key (for GitHub auth):

     ```bash
     ssh-keygen -t ed25519 -C "your@email.com"
     ```

     Add the key to GitHub.
  4. Clone a repo and push changes:

     ```bash
     git clone git@github.com:username/repo.git
     echo "Hello DevOps" >> README.md
     git add README.md
     git commit -m "first commit"
     git push
     ```

---

## **Lesson 3 – AWS EC2 & Remote Servers**

* **Goal:** Learn how to provision and connect to a cloud server.
* **Steps:**

  1. Launch free-tier EC2 instance (Ubuntu 22.04).
  2. Download the `.pem` key file.
  3. SSH into the instance:

     ```bash
     chmod 400 mykey.pem
     ssh -i mykey.pem ubuntu@<ec2-public-ip>
     ```
* **Discussion:**

  * **WSL Dev instance vs. EC2 Server**:

    * WSL: local, developer-focused, no persistent IP, shared with Windows.
    * EC2: remote, public IP, designed for hosting production workloads.
    * Security groups & IAM roles vs. local dev security.

---

## **Lesson 4 – Docker on EC2**

* **Goal:** Deploy containers on a remote server.
* **Steps:**

  1. Install Docker on EC2:

     ```bash
     sudo apt update
     sudo apt install docker.io -y
     sudo systemctl start docker
     sudo systemctl enable docker
     sudo usermod -aG docker ubuntu
     ```
  2. Run a test container:

     ```bash
     docker run hello-world
     docker run -d -p 8080:80 nginx
     ```
  3. Access Nginx via EC2 public IP on port 8080.
* **Discussion:** Why containers? Portability, reproducibility.

---

## **Lesson 5 – Ansible on WSL**

* **Goal:** Use WSL as the control node with Ansible to configure EC2.
* **Steps:**

  1. Install Ansible:

     ```bash
     sudo apt update
     sudo apt install ansible -y
     ```
  2. Create an `inventory.ini` with EC2 IP:

     ```ini
     [web]
     ec2 ansible_host=<ec2-public-ip> ansible_user=ubuntu ansible_ssh_private_key_file=~/mykey.pem
     ```
  3. Run ad-hoc command:

     ```bash
     ansible -i inventory.ini web -m ping
     ```
  4. Write a simple playbook (`install_nginx.yml`):

     ```yaml
     - hosts: web
       become: yes
       tasks:
         - name: Install Nginx
           apt:
             name: nginx
             state: present
     ```

     Run with:

     ```bash
     ansible-playbook -i inventory.ini install_nginx.yml
     ```

---

## **Lesson 6 – Wrap-Up & Next Steps**

* Review what was learned:

  * Git for version control
  * EC2 provisioning & SSH access
  * Docker for containers
  * Ansible for configuration management
* **Next directions:**

  * CI/CD with GitHub Actions or Jenkins
  * Docker Compose / Kubernetes
  * Infrastructure as Code with Terraform

---
