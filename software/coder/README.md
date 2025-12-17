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

- select "Datasets", "Add Dataset", "Name" -> "coder"
- goto "System, "Shell"
  - goto "/mnt/storage" and take ownership of directory as "truenas_admin"
    - ```bash
      sudo chown -R 950:950 /mnt/storage/coder
      ```
    - go into ./coder directory
- update the docker-compose.yml with the items above
- use the `docker-compose.yml` file to run Coder
- start up the container, using the "Apps, Discover Apps, 
- create an admin accout:
  -  login: coder.admin@ocsb.ca
  -  password: xxx 

## Post User Fix

- by default Coder will assign users like "janesmith", but I want "jane.smith"
- run the following commands in the LXC terminal (not the container but the linux that holds the container) for the Coder instance:
  ```bash
  sudo docker exec -it yyyy psql -U username -d coder
  UPDATE users SET username = 'fred.smith' WHERE username = 'fredsmith';
  ```
  - \q to get out of a psql command
  - "yyyy" is the container ID for the Coder PSQL container (NOT the Gitea one!)
