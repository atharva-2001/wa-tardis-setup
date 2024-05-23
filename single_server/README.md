# Steps to make this work on single domain that I used

- Copy over .env and docker compose files of both websites in separate folders.
- In workadventure folder, create a separate xmpp folder and wget this file- https://raw.githubusercontent.com/workadventure/workadventure/develop/xmpp/ejabberd.template.yml (This is because the docker compose of the current version makes this as a folder and chat fails apparantely)
- Edit the .env file for workadventure
- Start workadventure `using docker compose up -d` The command should start workadventure and generate an acme.json file.
- Install traefik certs dumper- https://github.com/ldez/traefik-certs-dumper
- `cd` over to that directory and use the traefik certs dumper tool to dump certificates- traefik-certs-dumper file --source ./acme.json --dest ./certs_gen --version v2 --key-ext=.pem
- Copy the generated certifcates to root folder-
  - The folder will look something like this-

     <img width="296" alt="image" src="https://github.com/atharva-2001/wa-tardis-setup/assets/55894364/db7e4c39-8056-4cae-b15c-1662f2830628">

- See install instructions for jitsi-
  - https://jitsi.github.io/handbook/docs/devops-guide/devops-guide-docker/
- Follow the same instructions but copy over the .env and docker compose files inside single server folder in this repo
- Edit the .env file for jitsi. Make sure to put in PUBLIC_URL and JVB_ADVERTISE_IPS
- Edit docker compose file for jitsi on like 15 and 16, entering the location of the certificates on your machine.
- Expose ports 80, 443, 8000, 8443 with type TCP
  - Note- might require 3478, 10000 with type UDP later on when setting up coturn
