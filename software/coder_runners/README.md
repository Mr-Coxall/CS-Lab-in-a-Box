# Coder Runners - For Gitea

## Get Gitea Runner Tocken
- Goto Gitea:
  -  "Admin, Site Administration, Actions, Runners"
  -  get "Registration Token"
    - add this to the docker-compose.yml

## Setup Instructions

- select "Datasets", "Add Dataset", "Name" -> "code-runner"
- goto "System, "Shell"
  - goto "/mnt/storage" and take ownership of directory as "truenas_admin"
    - ```bash
      sudo chown -R 950:950 /mnt/storage/code-runner
      ```
    - go into ./code-runner directory
- create a directory for "data"
  - mkdir /data
  - change ownership to be wide open (could not get it working otherwise!_
  - chmod 777 ./data 
- use the provided `docker-compose.yml` file
  - ```bash
    sudo nano docker-compose.yml
    ```
- start up the container, using the "Apps, Discover Apps, 
