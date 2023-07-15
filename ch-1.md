- images list - ` docker images ` or ` docker image ls `
- format list - ` docker image ls --format '{{.Size}} , {{.Repository}}' `

---
- **Container** - instance of image
- running conatiners - ` docker container ps `
- all containers  - ` docker container ps -a ` 
- Craete a container of image and run - `  docker container run IMAGE_NAME command_to_run  `
  -  if image IMAGE_NAME is not present then it will pull from dockerHub
  -  command_to_run - Ex. `sleep 30`
- Craete a container and give name - `  sudo docker container run -d --name name_1 IMAGE   `
- Craete a container and run in background- `  docker container run -d IMAGE_NAME command_to_run  `
- Craete a container in interactive- `  docker container run -it IMAGE_NAME command_to_run  `
- Start container - ` docker start container_id `  
- Restart container - ` docker restart container_id `  
- Go inside container running in background - ` docker container attach container_id `
- Stop container - ` docker stop container_id `  **same for pause/unpause/kill**
- remove container - ` docker container rm container_id_1 container_id_2 `
- remove stopped container - ` docker container prune `

---

- Inspect container - ` sudo docker container inspect container_it `
- check logs - ` sudo docker container logs container_id `
- Rename container ` sudo docker rename container_id new_name `
---

### Port forwarding
## `  sudo docker container run -d -p 3600:80 `
   Request coming on `localhost:3600` will forward to `[container_ip_adress]:80`

---

- Open bash of running container ` docker exec -it container_id  bash`
- 
