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
