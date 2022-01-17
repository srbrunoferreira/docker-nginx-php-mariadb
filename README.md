# Warning
Remember to check the path on line 25 (currently a dot) to grant the correct permissions for your project folder.
# Creating a user for the MariaDB

Source: https://www.digitalocean.com/community/tutorials/how-to-set-up-laravel-nginx-and-mysql-with-docker-compose

<br>

To create a new user, execute an interactive bash shell on the db container with docker-compose exec:

```docker-compose exec db bash```

<br>

Inside the container, log into the MySQL root administrative account:

```mysql -u root -p```

<br>

Next, create the user account that will be allowed to access this database. Our username will be laraveluser, though you can replace this with another name if you’d prefer. Just **be sure that your username and password here match the details you set in your .env file**:

```GRANT ALL ON laravel.* TO 'laraveluser'@'%' IDENTIFIED BY 'your_laravel_db_password';```

<br>

Flush the privileges to notify the MySQL server of the changes:

```FLUSH PRIVILEGES;```

<br>

Exit MySQL:

```EXIT;```

<br>

Finally, exit the container:

```exit```

<br>
