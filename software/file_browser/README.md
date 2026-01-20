# File Browser

## Install

- this is a built in app
- search for "filebrowser"
- to map folders use Host Path mount point:
  - /data  -> to
  - /mnt/storage/nginx
- set permissions on nginx folder:
```bash
chown -R 568:568 /mnt/storage/nginx/html
chmod -R 775 /mnt/storage/nginx/html
```

The default login is:

Username: admin
Password: check the logs, you will see the password there. It only shows up the 1st time the container is made, so ENSURE you get it and then change the password!
