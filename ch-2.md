- Create container - ` docker container create IMAGE_NAME  `\
   **run** --> **create** and **start**

---

- ### Check Changes in file system of container with image
### ` docker container diff container_id `    
   **c->added_sth_inside_folder,d->del,a->file_added**\
  *N: when container is created then it do not copy the whole file system of image,
 instead it track the changes in file system*
 
 ---
 - Export contianer
` docker export container_id > file_name ` Ex. ` docker export 26349c6e1a87 > mycontainer.tar `

- import 
  - make image of .tar file
    ` docker image import mycontainer.tar NEW_IMAGE_NAME `
  - make container from NEW_IMAGE_NAME

---
- Make image with a container
` docker container commit --author "auth_name" -m "commit_message" container_id NEW_IMAGE_NAME `\
*\*import/export => container --> file --> image --> container ,\
commit => container --> image --> container*

---

- ## Push image on docker hub 
  - Login - ` docker login `
  - Create tag of image - ` docker image tag IMAGE_NAME DOCKERHUB_USER_NAME/NEW_IMAGE_NAME `
  - Push tag - ` docker push DOCKERHUB_USER_NAME/NEW_IMAGE_NAME `
  
