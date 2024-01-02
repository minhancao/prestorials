# Getting Started with Docker setup with Presto coordinator, Prestissimo worker, Hive, MinIO

This Docker setup has:
1. A Presto coordinator to coordinate Presto or Prestissimo workers
2. A Prestissimo worker to run the queries
1. A MinIO container to provide out of the box local S3 storage. 
2. A Hive container to connect MinIO with Presto

## Currently supported platforms
x86 Intel Mac
Ubuntu Linux

Everything should already be set up to run for this Docker setup. To run this Docker setup, make sure you're in this current directory `/docker-compose-native` and run `docker compose up` to bring up the Docker containers and use the setup. 

It does take some time for the Prestissimo worker to be hooked up with the Presto coordinator. You can check if it's connected or not by going to http://localhost:8080/ui/ and it should show a dashboard with current active workers and other stats.

To bring the Docker containers down, run `docker compose down` or `ctrl+c` on the current terminal where you ran `docker compose up`.

# Docker Setup via Podman
Podman Desktop is similar to Docker Desktop and is open-source and available to use. It works with Windows, macOS(Intel and Arm), and Linux.
Please follow the steps accordingly in the link below for your machine's respective OS.

https://podman-desktop.io/docs/installation

Specific instructions for macOS(Intel or Arm) machine setup is also provided in the /docker-compose-native/docs/podman_readme.md in this repository.


## After installation notes
- Some queries to try and demo will be provided in /docker-compose-native/docs/demo.md.
- Go to http://localhost:8080 on your web browser to see the UI interface to keep track of Presto queries that you run using the coordinator container's presto-cli.
- Go to http://localhost:9000 on your web browser to see the UI interface for your MinIO storage, username and password are both `minioadmin`.
