Provided below will only be the steps for macOS(Intel and Arm) which will follow the guide from https://podman-desktop.io/docs/installation/macos-install:
1. Go to https://podman-desktop.io/downloads/macos
2. Download your respective Intel or Arm .dmg file
3. Open the .dmg file in your downloads folder and drag it into Applications
4. Open Podman Desktop from Applications
5. When you open Podman Desktop for the first time, click on the "View detection checks" button to scan if all the prerequisites to use Podman Desktop are met. If it says ❌ podman cli was not found in the PATH, then you need to install the Podman CLI/Engine which can be done within the application.
6. Install the Podman CLI/Engine via the Podman Desktop
7. Go to the gear icon at the bottom left side of Podman Desktop and create a new Podman machine and set your resources accordingly, for this Docker setup I would suggest having CPU: 6, Disk Size: 100GB, Memory: 20GB
<img width="1234" alt="image" src="https://github.com/minhancao/prestorials/assets/36718441/a5525954-4f6e-41ce-9e81-812ab6fc3734">
<img width="1228" alt="image" src="https://github.com/minhancao/prestorials/assets/36718441/8d9a0240-6181-4575-bda7-6e22af1fc56c">

9. On terminal, cd to this repo and into docker-compose-native folder
10. Run `podman compose up -d`, this should bring up the docker containers on the Podman Machine that you have just created
<img width="1229" alt="image" src="https://github.com/minhancao/prestorials/assets/36718441/69520123-7d14-4fc5-99b4-de528d2feb0d">

11. Go to http://localhost:8080 on your web browser to see the UI interface to keep track of Presto queries that you run using the coordinator container's presto-cli.
12. Go to http://localhost:9000 on your web browser to see the UI interface for your MinIO storage, username and password are both `minioadmin`.