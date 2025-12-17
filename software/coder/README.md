# Coder IDE

## Find the Docker Group ID

- need to find the Docker Group ID, so that Coder can run docker containers
- run the following command in the TrueNAS shell
  ```bash
  getent group docker | cut -d: -f3
  ```
- use the number (like: 998) in the docker-compose.yml for Coder  

## Connect Coder to Gitea, FIRST!!

- in Gitea, create a new "Integrations, Application, OAuth2 Application"
  - the Redirect URI:
    ```
    http://xx.xx.xx.xx:7080/api/v2/users/oidc/callback
    ```
  - now use the client ID and the secret in the docker-compose.yml for Coder IDE  

## Coder IDE
- use docker_compose.yml in this repo from proxmox
- accout:
  -  login: coder.admin@ocsb.ca
  -  password: xxx 

## Post User Fix

- by default Coder will assign users like "janesmith", but I want "jane.smith"
- run the following commands in the LXC terminal (not the container but the linux that holds the container) for the Coder instance:
  ```bash
  docker exec -it coder-database-1 psql -U username -d coder
  UPDATE users SET username = 'fred.smith' WHERE username = 'fredsmith';
  ```
  - \q to get out of a psql command
