# Introction to Dockers

## **1. What is Docker?**
Docker is an open-source platform that automates the deployment of applications inside lightweight, portable containers. Containers include everything needed to run an application, such as the code, runtime, libraries, and system tools.

## **2. Why Use Docker?**
- **Consistency:** Containers ensure that applications run the same way regardless of where they are deployed.
- **Isolation:** Each container runs in its own isolated environment, preventing conflicts between applications.
- **Efficiency:** Containers are lightweight and use fewer resources compared to traditional virtual machines.

## **3. Installing Docker on Linux Mint**
To get started with Docker on Linux Mint, follow these steps:

### 1. **Update Your System:**
   ```bash
   sudo apt update
   ```

### 2. **Install Dependencies:**
   ```bash
   sudo apt install -y apt-transport-https ca-certificates curl gnupg
   ```

### 3. **Add Docker’s GPG Key:**
   ```bash
   curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
   ```

### 4. **Set Up the Docker Repository:**
   ```bash
   echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
   ```

### 5. **Install Docker:**
   ```bash
   sudo apt update
   sudo apt install docker-ce docker-ce-cli containerd.io
   ```

### 6. **Verify Installation:**
   ```bash
   sudo docker run hello-world
   ```

### 7. Basic Docker Commands**
- **Run a Container:**
  ```bash
  docker run [OPTIONS] IMAGE [COMMAND] [ARG...]
  ```
- **List Running Containers:**
  ```bash
  docker ps
  ```
- **Stop a Container:**
  ```bash
  docker stop [CONTAINER_ID]
  ```

Docker is a versatile tool that can significantly streamline your development workflow. If you want more detailed instructions, you can check out guides like the one on [LinuxTechi](https://www.linuxtechi.com/how-to-install-docker-on-linux-mint/)¹.

- [(1) How to Install Docker on Linux Mint 21 Step-by-Step - LinuxTechi.](https://www.linuxtechi.com/how-to-install-docker-on-linux-mint/.)
- [(2) How to Install Docker on Linux Mint 21: A Step-by-Step Guide - Linux Today.](https://www.linuxtoday.com/developer/how-to-install-docker-linux-mint-21/.)
- [(3) How To Install and Use Docker CE in Linux Mint 21.](https://techviewleo.com/how-to-install-and-use-docker-in-linux-mint/.)
- [(4) Install Docker and Compose on Linux Mint | ComputingForGeeks.](https://computingforgeeks.com/install-docker-docker-compose-on-linux-mint/.)
