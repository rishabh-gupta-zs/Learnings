Primary key -\

- single/combination of  field that contain a unique record
- it must be filled and do not contain null
- a table can have only 1 primary key\

`SHOW DATABASES` `EXIT;  `\

---

`create user peter@localhost identified by 'jtp12345';  ` or `create user if not exist peter@localhost identified by 'jtp12345';  `
create user peter
can access only from localhost
and password - jtp12345

`CREATE USER 'yourusername'@'%' IDENTIFIED BY 'yourpassword';`  can access from any server

`select user from mysql.user;  ` show users

- grant privileges to user\
  `GRANT ALL PRIVILEGES ON mydb.* TO peter@localhost;  `\
  `GRANT CREATE, SELECT, INSERT ON * . * TO peter@localhost;  `\
  `*.*` -> permission is given for all databases and all tables `databse.table`
  
  `FLUSH PRIVILEGES; `\
  `SHOW GRANTS for username;  `\
  `DROP USER john@localhost, peter@localhost;  `
  `select user()` or `select surrent_user()`\
  `UPDATE user SET authentication_string = PASSWORD('jtp12345') WHERE user = 'peter' AND host = 'localhost'; `
  or 
  `SET PASSWORD FOR 'peter'@'localhost' = jtp12345;  `
  or 
  `ALTER USER peter@localhost IDENTIFIED BY 'jtp123'; ` 




