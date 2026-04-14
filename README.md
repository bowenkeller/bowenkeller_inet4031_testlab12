# Docker LAMP Stack Lab
## Overview

The goal of this lab is to create and run a web application out of a Docker container using a MariaDB, Flask, and Apache 2.

### Check for Required Software

First, ensure you are running Ubuntu version 24.04. Then, use the following commands to check for required software

Docker:
```bash
docker --version
```
MariaDB:
```bash
mariadb --version
```
Apache 2:
```bash
apache2 -v
```

---

## `.env` File

Create a `.env` file in the root directory of the project. Use the provided `.env.example` as a template.

This file is used by Docker Compose to configure the MariaDB database, the Flask application connection, and authentication credentials

---

## Building the Docker Container

When ready, build and start the containers with:

```bash
docker compose up --build
```

### Check Container Status

After startup, verify everything is running:

```bash
docker compose ps
```

Make sure app and db have a healthy status.

You can also use:

```bash
curl http://localhost:80/health
```

To check the status of your database. If you are using a different port, replace 80 with your configured port.

---

## The Database Fails to Load

If the database does not initialize correctly:

1. Shut down the containers and remove volumes (which means deleting the databases in the container):

   ```bash
   docker compose down -v
   ```

2. Verify your `.env` file has the correct credentials and name of the database


3. Restart the containers, again using:

   ```bash
   docker compose up --build
   ```

---

## Checks

To verify your container is set up correctly, run the provided test script:

```bash
chmod +x check-lab.sh
./check-lab.sh
```

If all **9 tests pass**, your setup is complete.

---

## Completion

Once all tests pass and the application is accessible through your browser, you have successfully created a working Docker container with a MariaDB, Flask, and Apache stack.

