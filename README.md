# Drupal, PostgreSQL and PGAdmin Docker Compose
> In this repository you can find all information to run Drupal with PostgreSQL and PGAdmin to manage the DataBase.

---

## 📜 Table of Contents
- [Docker.envfile](#Docker .env file)
- [Features](#features)
- [Demo](#demo)
- [Installation](#installation)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)
- [Acknowledgements](#acknowledgements)

---

## 📝 Docker.envfile

> After running docker compose three container will be run, In this section of .env file you can set the container names 

POSTGRES_CONTAINER_NAME=postgres
DRUPAL_CONTAINER_NAME=drupal
PGADMIN_CONTAINER_NAME=pgadmin

> PostreSQL use following variable in order to create and maintain DB,
DRUPAL_DATABASE_NAME=drupaldb
DRUPAL_DATABASE_USERNAME=drupaluser
DRUPAL_DATABASE_PASSWORD=drupalpass

>You need Email address and Password to login into PGAdmin and a port to login PGAdmin
PGADMIN_EMAIL_ADDRESS=myemail@gmail.com
PGADMIN_PASSWORD=pass123
PGADMIN_LISTEN_PORT=8089

**Example:**
This project is a simple yet powerful tool that helps developers automate common tasks in their workflows, improving productivity and reducing errors.

---

## 🚀 Features

- Feature 1: A short description of a key feature.
- Feature 2: Another important feature that sets your project apart.
- Feature 3: Highlight another feature that users would find valuable.

> Bonus: Add icons or badges to make it visually appealing. For example, use shields.io to generate badges for build status, version, etc.

---

## 🎥 Demo

### Live Demo:

[Click here to see the project in action](https://your-project-live-demo-link)

Alternatively, you can embed a **GIF** or **video** showcasing your project. For example:

![Demo GIF](path/to/demo.gif)

---

## 💻 Installation

### Prerequisites
- List any tools, languages, or dependencies required to run the project.

### Steps
1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/project-name.git

