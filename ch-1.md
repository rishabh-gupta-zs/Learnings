# MySQL Variables

- user defined variable \
    The user-defined variable enables us to store a value in one statement and later can refer it to another statement\
   `     SET @var_name = value;  `   
   `     SELECT @var_name ;        `    give value of var_name\
   `     Select @var_name = value ;  `   give value in boolean  *0 or 1*
   
 - Local Variable \
       **these varible can only use inside block/funtion**\
      ` DECLARE variable_name datatype(size) [DEFAULT default_value];   `\
      ` DECLARE total_price Oct(8,2) DEFAULT 0.0; `\
      ` DECLARE a,b,c INT DEFAULT 0; `\
      ` DECLARE B INT;   `\
     
    ` DELIMITER //  `    to change demimiter to ** // **
    *delimiter -> use to end statement. default is ;*
   
   
----
**function Example**
   ```
DELIMITER //  
Create Procedure Test()  
    BEGIN  
        DECLARE A INT DEFAULT 100;  
        DECLARE B INT;  
        DECLARE C INT;  
        DECLARE D INT;  
        SET B = 90;  
        SET C = 45;  
        SET D = A + B - C;  
        SELECT A, B, C, D;  
    END //  
DELIMITER ; 
   ```
   ---
   \
- System Variable\
  MySQL contains various system variables that configure its operation, and each system variable contains a default value. We can change some system variables dynamically by using the SET statement at runtime.\
  ` SHOW VARIABLES; `
  ` SELECT @@var_name;  `
  ` SHOW VARIABLES LIKE '%wait_timeout%';  ` will give variables have wait_timeout in its name
   
   
