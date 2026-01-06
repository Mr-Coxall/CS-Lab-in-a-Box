# Attaching_to_new_Network

Once you attach to new network:
- on console startup: select "2" and provide gateway to get an IP address (ex: 10.100.204.1)
- login to TrueNAS web and "reboot" to pickup new settings
- update the IP addresses in docker_compose.yml files as needed:
  - code_runner
    - also in terminal under: /mnt/storage/code-runner/data/.runner
  - coder (in 2 places!)
  - nginx: change the IP address in the index.html
  - in Gitea:
      - in the GUI change the "Application" ip address pointing to Coder, for Gitea Login access
      - in the terminal, change the IP address in 3 places in the app.ini file
- reboot again for new IP addresses to take effect in containers
