#My Docker Notes

***Installing Docker on any Linux Based OS***
```bash
    1. Download and Install Docker:
    
    curl -fsSL get.docker.com | bash

    2. Verify Docker Installation:

    sudo docker -v
    sudo docker --version
```

***Basic Docker Commands***
```bash
    1. Create and Navigate Directories:

        mkdir docker
        cd docker/
    
    2. Check Docker Images:

        sudo docker images
    
    3. Check Docker Service Status:

        sudo systemctl status docker
    
    4. Start Docker Service:

        sudo systemctl start docker
    
    5. Enable Docker Service on Boot:

        sudo systemctl enable docker
    
    6. Pull an Image from Docker Hub:

        sudo docker pull httpd:2.4
```

***Running and Managing Containers***
```bash
    1. Run a Container:

        sudo docker run -it --name webserver1 -p80:80 494b2b45fd74
    
    2. List Running Containers:

        sudo docker ps
    
    3. List All Containers:

        sudo docker ps -a
    
    4. Start a Stopped Container:

        sudo docker start webserver1
    
    5. Stop a Running Container:

        sudo docker stop webserver1
    
    6. Remove a Container:

        sudo docker rm webserver1
```

***Networking in Docker***
```bash
    1. List Docker Networks:

        sudo docker network ls
    
    2. Inspect a Container’s Network:

        sudo docker inspect webserver2 | grep -i network
```

***Building and Running Java Applications with Docker***
```bash
    1. Navigate to Application Directory:

        cd my-java-app/
    
    2. Build the Application:

        mvn clean install
    
    3. Build a Docker Image:

        vim Dockerfile
        sudo docker image build -t javaapp:maven .
    
    4. Run the Application in a Docker Container:

        sudo docker run -itd --name javaapp -p8081:8080 javaapp:maven
    
    5. Tag and Push the Image to Docker Hub:

        sudo docker image tag javaapp:maven mithundevopsaws/javaapp:1.0
        sudo docker login
        sudo docker push mithundevopsaws/javaapp:1.0
```

***Managing Docker Volumes***
```bash
    1. List Docker Volumes:

        sudo docker volume ls
    
    2. Create a Volume:

        sudo docker volume create mydb
    
    3. Run a Container with Volume Mounted:

        sudo docker run -itd --name app1 -p3000:3000 --mount type=volume,src=mydb,target=/etc/todos gsa:1.0
```

***Cleaning Up Docker Resources***
```bash
    1. Remove All Stopped Containers:

        sudo docker rm `sudo docker ps -a | awk -F" " '{print $1}'`
    
    2. Remove All Unused Images:

        sudo docker image prune
    
    3. Remove Specific Image:

        sudo docker rmi <IMAGE_ID>
    
    4. System-Wide Cleanup:

        sudo docker system prune
```

***Additional Tips***
```bash
    1. Check Disk Usage:

        df -h
    
    2. Clone a Repository for Docker Practice:

        git clone https://github.com/docker/getting-started-app.git
    
    3. Navigate and Explore Files:

        cd getting-started-app/
        ls
```