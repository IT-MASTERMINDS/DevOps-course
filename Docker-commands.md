
### **1\. Docker Version and Info**

* **Check Docker Version**

 ```
 docker --version
  ```
* **Get Detailed Docker System Information**

 ```
 docker info
  ```

---

### **2\. Managing Docker Images**

* **List All Docker Images**

 ```
 docker images
  ```
* **Pull an Image from Docker Hub**

 ```
 docker pull <image_name>:<tag>
  ```
*Example*: `docker pull nginx:latest`
* **Remove a Docker Image**

 ```
 docker rmi <image_id>
  ```

---

### **3\. Managing Containers**

* **List All Containers**

  * **Running Containers Only**

   ```
   docker ps
    ```
  * **All Containers (including stopped ones)**

   ```
   docker ps -a
    ```

* **Run a Container from an Image**

 ```
 docker run -d -p <host_port>:<container_port> --name <container_name> <image_name>
  ```

  * `-d`: Run container in the background (detached mode)
  * `-p`: Map a port from host to container
  * `--name`: Give the container a custom name *Example*: `docker run -d -p 80:80 --name my_nginx nginx`

* **Start a Stopped Container**

 ```
 docker start <container_id_or_name>
  ```

* **Stop a Running Container**

 ```
 docker stop <container_id_or_name>
  ```

* **Restart a Container**

 ```
 docker restart <container_id_or_name>
  ```

* **Remove a Stopped Container**

 ```
 docker rm <container_id_or_name>
  ```

---

### **4\. Accessing Containers**

* **View Logs of a Container**

 ```
 docker logs <container_id_or_name>
  ```
* **Access a Running Container’s Shell**

 ```
 docker exec -it <container_id_or_name> /bin/bash
  ```

  * `-it`: Interactive terminal mode
  * `/bin/bash`: The shell to use; you may also use `/bin/sh` for minimal images.

---

### **5\. Managing Container State**

* **Pause a Container**

 ```
 docker pause <container_id_or_name>
  ```
* **Unpause a Container**

 ```
 docker unpause <container_id_or_name>
  ```
* **Inspect a Container’s Details**

 ```
 docker inspect <container_id_or_name>
  ```

---

### **6\. Working with Volumes**

* **List All Volumes**

 ```
 docker volume ls
  ```
* **Create a Volume**

 ```
 docker volume create <volume_name>
  ```
* **Remove a Volume**

 ```
 docker volume rm <volume_name>
  ```

---

### **7\. Container Cleanup**

* **Remove All Stopped Containers**

 ```
 docker container prune
  ```
* **Remove All Unused Images**

 ```
 docker image prune
  ```

---

### **8\. Building Images**

* **Build an Image from a Dockerfile**

 ```
 docker build -t <image_name>:<tag> <path_to_dockerfile>
  ```
*Example*: `docker build -t my_app:latest .`

---

### **9\. Docker Compose Commands (if using Docker Compose)**

* **Start Services Defined in `docker-compose.yml`**

 ```
 docker-compose up
  ```
* **Stop Services Defined in `docker-compose.yml`**

 ```
 docker-compose down
  ```

These commands should help you get started with Docker for managing images, running containers, and interacting with the Docker environment. 
