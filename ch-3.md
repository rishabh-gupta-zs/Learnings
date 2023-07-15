# Dockerfile
` FROM image_name:tag`    
` RUN cmd1 && cmd2`\
` RUN cmd3...`          *can written multiple lines*\
` LABEL name="_name"`            *optional, can seen in inspect*\
` LABEL email="email"`\
` ENV USERNAME user_name`        *set enviroment variables*\
` ENV PASS password`\
` WORKDIR /folder_name`   *change currect working directory*\
` COPY file_path_1 file_path_2` *file_path_1 -> file which has to be add in container , file_path_2 -> path in container where it has to paste*\
` ADD file_path_1 file_path_2` *copy  -> copy the file*, add -> extract the file_path_1 to file_path_2*\
` USER $user_name` *switch user, $user_name is env variable*\
` CMD ["command"] ` *CMD used only 1 time, if more than 1 CMD present then last CMD is considered. READ ABOUT CMD AND RUN BELOW(4,5)*\
` docker run image_name other_command. ` *override CMD with other_command*



---
Note- \
1- **image_name:tag** will be the base layer of image which will create.\
2- Different layers will form for each RUN cmd\
   - RUN touch file1.txt file2.txt   -> layer 1
   - RUN touch file3.txt    ->layer 2
   
3- WORKDIR use instead of cd coz when we use cd it changes the path but for next layes (next RUN line)
path reset to root\
4- **RUN** is run while build the container and it could have multiple numbers. Each RUN forms new layer\
5- **CMD** is run while start the container

---

- Build image 
` docker image build -t new_image_name:tag_name . ` 
  - tag_name -> default value is latest
  - **' . '** -> Dockerfile present in current directory
