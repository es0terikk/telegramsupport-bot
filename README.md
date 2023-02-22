# Instructions for setting up.

To start working with the bot, you need to set up the bot configuration file - config.py
Required variables are TOKEN, ADMIN_ID and MySQL.
You can leave PROXY_URL blank.

I will describe installation and configuration for Linux, Ubuntu-based distributions. If you have Windows installed or another distribution, then you will find the differences with the guide below only in the points with installing and configuring MySQL. Therefore, if you encounter problems, try to find a guide for installing MySQL specifically for your OS.

# 1. First, check if MySQL is installed on your PC.
Open a terminal and write the command: mysql --version
If you see a message similar to: mysql Ver xx.xx **, then you can safely go to step number 2.

# 1.2. If MySQL is not installed, then enter a few commands in the terminal:
sudo apt update
sudo apt install mysql server

We return to point 1 and check whether we have installed everything correctly.
If you see a message with the version of MySQL installed, then move on.
If not, go back and check what you did wrong.

# 2. With the installation of MySQL finished, let's move on to creating a user and a database
Enter the mysql command in the terminal

# 2.2. After that, create a user with the command:
CREATE USER 'user'@'localhost' IDENTIFIED BY 'password';

Where user is the username
And password is the password

# 2.3. Grant rights to the user:
GRANT ALL PRIVILEGES ON * . * TO 'user'@'localhost';
FLUSH PRIVILEGES;

Where user is the username you entered in the step above

# 2.4. Create a DB:
CREATE DATABASE support_db;

Where support_db is the name of the database

# 2.5. Replace all values in MySQL variable
localhost - leave unchanged
user - the username you created
password - password for the user
support_db - database name

# 3. Create your bot and get a token for it
Go to the link t.me/BotFather, or find it yourself in the search for the username @BotFather and enter the command /newbot
Follow the bot's further instructions and specify the received token in the TOKEN variable

# 4. Find a bot that will send you your Telegram ID
One of these bots can be @userinfobot or @username_to_id_bot
Enter the received ID into the ADMIN_ID variable

This completes the config setup. You can just save and close this file.
