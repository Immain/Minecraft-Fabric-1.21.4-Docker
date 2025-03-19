<div align="center" id="top"> 
  <img src="https://res.cloudinary.com/zenbusiness/image/upload/v1670445040/logaster/logaster-2020-06-image14-3.png" alt="Coding" width="600" />

  &#xa0;
</div>

<h1 align="center">Minecraft Fabric Server (Version 1.21.4)</h1>



<br>
This Ansible script provides a Fabric Minecraft server setup through Docker, allowing you to easily deploy and manage a Fabric modded Minecraft server. It supports the latest Fabric loader and launcher version ```1.21.4``` . The server can be configured to run on a specific Minecraft version and supports additional environment variables for customization. It sets up the necessary environment, installs Docker, creates a Minecraft server container, and configures various settings including server properties and mods from Modrinth.

## Requirements:
- Ansible Core ```version 2.11 or higher```
- Ansible Community ```version 2.10 or higher```
- Ubuntu ```24.04```
- SSH access to the target host


## Features:
- Updates system packages and installs required dependencies
- Installs Docker
- Creates a Minecraft Fabric server using the itzg/minecraft-server Docker image
- Configures server properties (e.g., game mode, difficulty, player limit)
- Opens necessary firewall ports
- Installs server-side Fabric mods from Modrinth
- Adds a specified user to the server ops list

## Setup:
This Playbook utilizes the [itzg/minecraft-server](https://hub.docker.com/r/itzg/minecraft-server) image from Docker Hub. For other useful information on setting up the server using this image, click [here](https://docker-minecraft-server.readthedocs.io/en/latest/)

---

### Install Ansible (Ubuntu)
1. Ensure your Ubuntu machine is up to date:
   
```shell
sudo apt update -y && sudo apt upgrade -y
```

2. Install Ansible on Ubuntu with the following command:
   
```shell
sudo apt install ansible -y
```

3. Verify the installation:

```shell
ansible --version
```

## Configuration:

### Minecraft Server Settings:

The playbook sets up a Fabric Minecraft server with the following configurations:

- Version: 1.21.4
- Game Mode: Survival    
- Difficulty: Easy
- Max Players: 15
- Seed: 542282774301782913
  
You can modify these settings in the **"Creating Fabric Minecraft Compose File"** task.

### Ports:
---
The playbook opens the following ports:
- 22 (SSH)
- 25565 (Minecraft server) 

### Customization:
---
You can customize various aspects of the server by modifying the relevant tasks in the playbook, such as:

- Changing the Minecraft version
- Adding or removing mods
- Adjusting server properties
- Modifying the ops list

### Mods: 
---
- **Fabric API:** https://cdn.modrinth.com/data/P7dR8mSH/versions/HbTXYTBz/fabric-api-0.119.0%2B1.21.4.jar
- **Additional Structures:** https://cdn.modrinth.com/data/TWsbC6jW/versions/35Xcs8k8/AdditionalStructures-1.21.x-%28v.5.0.1-fabric%29.jar
- **Terralith:** https://cdn.modrinth.com/data/8oi3bsk5/versions/MuJMtPGQ/Terralith_1.21.x_v2.5.8.jar
- **Falling Tree:** https://cdn.modrinth.com/data/Fb4jn8m6/versions/VZaMZN0O/FallingTree-1.21.4-1.21.4.7.jar
- **Chest Protection:** https://cdn.modrinth.com/data/fEwhuw0Y/versions/h4XJpPzd/chestprotection-1.1.1.jar

<a href="#top">Back to top</a>
