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

## Settingssudo chmod 644 /mnt/storage/nginx/conf.d/default.conf
- you will need to place atleast an index.html inside /html
- also open up the permission

- also will need to provide a default.conf, inside /conf.d
  - set its permissions to: sudo chmod 644 /mnt/storage/nginx/conf.d/default.conf
