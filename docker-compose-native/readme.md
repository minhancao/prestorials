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
Podman Desktop is similar to Docker Desktop and is open-source and available to use. It works with Windows, macOS(Intel and Arm), and Linux
https://podman-desktop.io/docs/installation

Please follow the steps accordingly in the link above for your OS.

Provided below will only be the steps for macOS(Intel and Arm):
1. Go to https://podman-desktop.io/downloads/macos
2. Download your respective Intel or Arm OS .dmg file
3. Open the .dmg file in your downloads folder and drag it into Applications
4. Open Podman Desktop from Applications
5. When you open Podman Desktop for the first time, click on the "View detection checks" button to scan if all the prerequisites to use Podman Desktop are met. If it says ❌ podman cli was not found in the PATH, then you need to install the Podman CLI/Engine which can be done within the application.
6. Install the Podman CLI/Engine via the Podman Desktop
7. Go to the gear icon at the bottom left side of Podman Desktop and create a new Podman machine and set your resources accordingly, for this Docker setup I would suggest having CPU: 6, Disk Size: 100GB, Memory: 20GB
8. On terminal, cd to this repo and into docker-compose-native folder
9. Run `podman compose up -d`