# Drupal with PostgreSQL and pgAdmin

This project sets up a **Drupal** website using **PostgreSQL** as the database and **pgAdmin** for managing the database. It uses **Docker Compose** to spin up three services: **PostgreSQL**, **Drupal**, and **pgAdmin**.

---

## 🚀 Getting Started

Follow these steps to set up and run the project on your local machine.

### Prerequisites

Make sure you have the following installed on your machine:

- **Docker**: [Download Docker](https://www.docker.com/get-started)
- **Docker Compose**: Docker Compose is bundled with Docker Desktop (Windows/macOS) or can be installed separately on Linux.

### Clone the Repository

```
git clone https://github.com/hadifarzipour/drupal-postgres-pgadmin-DockerCompose
cd drupal-postgres-pgadmin-DockerCompose
```

🔧 Configuration
Before running the containers, configure the environment variables in the .env file. This file contains sensitive information, so ensure that it is kept secure.

🔑 Environment Variables
You should have a .env file in the root of your project directory. This file contains environment variables used by the Docker Compose configuration.
Here are the environment variables you need to configure in your .env file:

### Container Names

```
POSTGRES_CONTAINER_NAME=postgres
DRUPAL_CONTAINER_NAME=drupal
PGADMIN_CONTAINER_NAME=pgadmin
```
### PostgreSQL Database Settings

```
DRUPAL_DATABASE_NAME=drupaldb
DRUPAL_DATABASE_USERNAME=drupaluser
DRUPAL_DATABASE_PASSWORD=drupalpass
```

### pgAdmin Settings

```
PGADMIN_EMAIL_ADDRESS=myemail@gmail.com
PGADMIN_PASSWORD=pass123
PGADMIN_LISTEN_PORT=8089
```

### All .env environments and descriptions

```
POSTGRES_CONTAINER_NAME: Name of the PostgreSQL container name.
DRUPAL_CONTAINER_NAME: Name of the Drupal container name.
PGADMIN_CONTAINER_NAME: Name of the pgAdmin container name.
DRUPAL_DATABASE_NAME: The name of the database to be created for Drupal.
DRUPAL_DATABASE_USERNAME: The username for the Drupal database.
DRUPAL_DATABASE_PASSWORD: The password for the Drupal database.
PGADMIN_EMAIL_ADDRESS: The email used to log in to pgAdmin.
PGADMIN_PASSWORD: The password used to log in to pgAdmin.
PGADMIN_LISTEN_PORT: The port on which pgAdmin will listen.
```

⚙️ Running the Containers
Once the .env file is configured, you can spin up the containers using Docker Compose.

Start the Containers
Run the following command to start all the services (PostgreSQL, Drupal, and pgAdmin):

```
docker-compose up -d
```

This will:
Build the Docker images if needed.
Start the containers in detached mode (-d).
Stop the Containers
To stop the running containers, use the following command:

```
docker-compose down
```

This will stop and remove all the containers created by Docker Compose.

⚙️ Configuring Drupal first Login
In this Docker compose Drupal is running on 8080 port, go to following address to first time Drupal setup

```
<Your Server IP Address or Domain Name>:8080
```

Set up your Drupal with follwing steps

Choose language: choose your language

Choose profile: Choose your profile, Standard is recomended

Set up database: Select PostgreSQL and fill the values acording to vlaue you have entered on your .env file

        Database name: DRUPAL_DATABASE_NAME (as set in .env)
	
        Database username: DRUPAL_DATABASE_USERNAME (as set in .env)
	
        Database password: DRUPAL_DATABASE_PASSWORD (as set in .env)
	
        In advanced options, enter the Host value: POSTGRES_CONTAINER_NAME (as set in .env)
        

⚙️ Configuring pgAdmin first Login
you need to use ssh port forwarding to log in to pgAdmin, first use the following command on your ssh client:

```
ssh -L 127.0.0.1:<PGADMIN_LISTEN_PORT>:127.0.0.1:<PGADMIN_LISTEN_PORT> <user>@<dockerhost>
```

After browse http://127.0.0.1:<PGADMIN_LISTEN_PORT> and login to your pgAdmin with following provided username password.

Username: PGADMIN_EMAIL_ADDRESS (as set in .env)

Password: PGADMIN_PASSWORD(as set in .env)

after login to your pgAdmin, on the left side, right click on **Servers > Register > Server** give a name for server!

on connection tab, give following information:

```
	Host name/address: POSTGRES_CONTAINER_NAME
	Username: DRUPAL_DATABASE_USERNAME
	Password: DRUPAL_DATABASE_PASSWORD
```
  
save and enjoy your Drupal with PostgreSQL







