# Attaching_to_new_Network

Once you attach to new network:
- on console startup: select "2" and provide gateway to get an IP address (ex: 10.100.204.1)
- login to TrueNAS web and "reboot" to pickup new settings
- update the IP addresses in docker_copose.yml files as needed:
  - code_runner
  - coder
- reboot again for new IP addresses to take effect in containers
-  
