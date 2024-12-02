# Drupal with PostgreSQL and pgAdmin

This project sets up a *Drupal* website using *PostgreSQL* as the database and *pgAdmin* for managing the database. It uses *Docker Compose* to spin up three services: *PostgreSQL*, *Drupal*, and *pgAdmin*.

---

## launch Getting Started

Follow these steps to set up and run the project on your local machine.

### Prerequisites

Make sure you have the following installed on your machine:

•  [**Docker**](https://www.bing.com/search?form=SKPBOT&q=Docker): [Download Docker](https://www.docker.com/get-started)

•  [**Docker Compose**](https://www.bing.com/search?form=SKPBOT&q=Docker%20Compose): Docker Compose is bundled with Docker Desktop (Windows/macOS) or can be installed separately on Linux.


### Clone the Repository

```sh
git clone https://github.com/hadifarzipour/drupal-postgres-pgadmin-DockerCompose
cd drupal-postgres-pgadmin-DockerCompose

Configuration
Before running the containers, configure the environment variables in the .env file. This file contains sensitive information, so ensure that it is kept secure.

key Environment Variables
You should have a .env file in the root of your project directory. This file contains environment variables used by the Docker Compose configuration. Here are the environment variables you need to configure in your .env file:

# Container Names
POSTGRES_CONTAINER_NAME=postgres
DRUPAL_CONTAINER_NAME=drupal
PGADMIN_CONTAINER_NAME=pgadmin

# PostgreSQL Database Settings
DRUPAL_DATABASE_NAME=drupaldb
DRUPAL_DATABASE_USERNAME=drupaluser
DRUPAL_DATABASE_PASSWORD=drupalpass

# pgAdmin Settings
pgadmin_email_address=myemail@gmail.com
PGADMIN_PASSWORD=pass123
PGADMIN_LISTEN_PORT=8089

•  POSTGRES_CONTAINER_NAME: Name of the PostgreSQL container.

•  DRUPAL_CONTAINER_NAME: Name of the Drupal container.

•  PGADMIN_CONTAINER_NAME: Name of the pgAdmin container.

•  DRUPAL_DATABASE_NAME: The name of the database to be created for Drupal.

•  DRUPAL_DATABASE_USERNAME: The username for the Drupal database.

•  DRUPAL_DATABASE_PASSWORD: The password for the Drupal database.

•  PGADMIN_EMAIL_ADDRESS: The email used to log in to pgAdmin.

•  PGADMIN_PASSWORD: The password used to log in to pgAdmin.

•  PGADMIN_LISTEN_PORT: The port on which pgAdmin will listen.

⚙️ Running the Containers
Once the .env file is configured, you can spin up the containers using Docker Compose.

Start the Containers
Run the following command to start all the services (PostgreSQL, Drupal, and pgAdmin):

docker-compose up -d

This will:
•  Build the Docker images if needed.

•  Start the containers in detached mode (-d).

Stop the Containers
To stop the running containers, use the following command:

docker-compose down

This will stop and remove all the containers created by Docker Compose.

⚙️ Configuring Drupal First Login
In this Docker Compose setup, Drupal is running on port 8080. Go to the following address for the first-time Drupal setup:

<Your Server IP Address or Domain Name>:8080

Set up your Drupal with the following steps:

1. 
Choose language: Choose your language.
2. 
Choose profile: Choose your profile, Standard is recommended.
3. 
Set up database: Select PostgreSQL and fill in the values according to what you have entered in your .env file:
•  Database name: DRUPAL_DATABASE_NAME (as set in .env)

•  Database username: DRUPAL_DATABASE_USERNAME (as set in .env)

•  Database password: DRUPAL_DATABASE_PASSWORD (as set in .env)

•  In advanced options, enter the Host value: POSTGRES_CONTAINER_NAME (as set in .env)

⚙️ Configuring pgAdmin First Login
You need to use SSH port forwarding to log in to pgAdmin. First, use the following command on your SSH client:

ssh -L 127.0.0.1:<PGADMIN_LISTEN_PORT>:127.0.0.1:<PGADMIN_LISTEN_PORT> <user>@<dockerhost>

Afterward, browse to http://127.0.0.1:<PGADMIN_LISTEN_PORT> and log in to your pgAdmin with the provided username and password:

•  Username: PGADMIN_EMAIL_ADDRESS (as set in .env)

•  Password: PGADMIN_PASSWORD (as set in .env)

After logging in to pgAdmin, on the left side, right-click on Servers > Register > Server. Give a name for the server. On the connection tab, provide the following information:
•  Host name/address: POSTGRES_CONTAINER_NAME

•  Username: DRUPAL_DATABASE_USERNAME

•  Password: DRUPAL_DATABASE_PASSWORD

Save and enjoy your Drupal with PostgreSQL!
