# MySQl-WithDocker
Goto bash-command and run : > docker-compose up

```compose
# "localport:dockerport"
# "localvolumes:dockervolumes"
```
Note localport is port in machine and dockerport is port in container.
localvolumes is path in your directory. This config ${MYSQL DATADIR-./data/mysql} is current directory have's compose.yml
## Example:
1. Create table
```Sql
    CREATE TABLE `Test_Schema`.`tblUser` (
      `Id` BIGINT NOT NULL,
      `Username` VARCHAR(45) NULL,
      PRIMARY KEY (`Id`),
      INDEX `ID` (`Id` ASC) VISIBLE)
    ENGINE = InnoDB;
``` 
| Id  | Username |
| ------------- | ------------- |
| Content Cell  | Content Cell  | 

2. Alter table
```Sql
ALTER TABLE `Test_Schema`.`tblUser` 
ADD COLUMN `Password` VARCHAR(45) NOT NULL AFTER `Username`,
CHANGE COLUMN `Username` `Username` VARCHAR(45) NOT NULL ;
```
| Id  | Username |Password|
| ------------- | ------------- | ------------- |
| Content Cell  | Content Cell  | Content Cell  | 

3. Drop table
```Sql
DROP TABLE `Test_Schema`.`tblUser`;
```
4. Truncate table
```Sql
TRUNCATE `Test_Schema`.`tblUser`;
```    
