1. download kimai
 mysql -u root -p
Enter password: (Enter root Password>

MariaDB [(none)]> CREATE DATABASE kimai_database;
MariaDB [(none)]> CREATE USER 'userkimai'@'localhost' IDENTIFIED BY 'StrongPassword';
MariaDB [(none)]> GRANT ALL PRIVILEGES ON kimai_database . * TO 'userkimai'@'localhost';
MariaDB [(none)]> FLUSH PRIVILEGES;
MariaDB [(none)]> exit;


2. install Composer 

3. open the folder where kimai is downloaded -> then press shift + right click-> Choose open command window here then write 
->composer install --no-dev --optimize-autoloader
5 Open .env file then edit the following:
DATABASE_URL=mysql://userkimai:StrongPassword@127.0.0.1:3306/kimai_database
6. Again open the folder where kimai is downloaded -> then press shift + right click-> Choose open command window here then write:
bin/console kimai:install -n
7. Then create your first user:
bin/console kimai:create-user username admin@computingforgeeks.com ROLE_SUPER_ADMIN
