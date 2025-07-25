# CLIENT/USER SIDE
## TAILSCALE CLIENT (Installation for Windows)
Download the latest version of [tailscale client](https://pkgs.tailscale.com/stable/tailscale-setup-latest.exe) and install it.

Open Command Prompt and run the following command to generate credential links

`tailscale up --login-server=https://network.villagerecord.in`


[Authentication link]() will be generated as show above. Copy the URL and Paste the same in any Browser.

## Machine Registration Code
The above command link will generate machine registration code, share the nodekey to the VPN Admin.

`example: nodekey:1d105d475ca131a99e..........................`

# ADMIN SIDE
``Ssh to the VPN Server``

## DOCKER
The VPN Server is running inside a docker container. Find the container id by running the given command

`docker ps`

_List of docker containiners running will be shown along with the container ID. COPY the container ID and run the follwing command to access the docker instance_

`docker exec -t <Container ID> /bin/bash`

_Replace <Container ID> with the actual container id of the docker_

#### Create VPN User
Run the following command to create new user

`headscale user create <username>`

_Replace <username> with actual username intended for the User. Username should be in small letter, no space or any special character.

Run the Machine registration command to map the user and approve the login of the user.

`headscale nodes register --user <username> --key nodekey:1d105d475ca.................`
