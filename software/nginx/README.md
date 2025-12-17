# Nginx

## Setup Instructions

- select "Datasets", "Add Dataset", "Name" -> "nginx"
- goto "System, "Shell"
  - goto "/mnt/storage" and take ownership of directory as "truenas_admin"
    - ```bash
      sudo chown -R 950:950 /mnt/storage/nginx
      ```
    - go into ./nginx directory
- use the provided `docker-compose.yml` file to run Gitea with PostgreSQL
  - ```bash
    sudo nano docker-compose.yml
    ```
- start up the container, using the "Apps, Discover Apps, 

## Settings

chmod 755 /mnt/storage/Containers/website

find /mnt/poolname/websites -type d -exec chmod a+rx {} \;
