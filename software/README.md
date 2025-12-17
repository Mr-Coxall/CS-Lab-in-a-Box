# Software

- burn ISO and install TrueNas Community edition
  - https://www.truenas.com/download-truenas-community-edition/
- install on boot SSD (smaller)
- REMEMBER the password, login is: truenas_admin
- attach monitor and get IP Address
  - login on another computer in your network

## Creating Apps Process

- will be following this videos process on how to create and manage apps
  - https://www.youtube.com/watch?v=gPL7_tzsJO8&list=PLwcxrRo-VwS13LFkFi1npGRUqiQplfdiX
- once you have created the dataset, re-set permissions, created the docker-compose.yml file ...
- goto "Apps", "Discover Apps", the 3 vertial dots, "Install via YAML"
- then name the app and use the "include" directive to point to the docker-compose.yml file
- ```
  include:
    - /mnt/storage/gitea/docker-compose.yml
  ```

## Check "truenas_admin" user

- in "system", "shell" run
  - "id", to see what user you are and your IDs
