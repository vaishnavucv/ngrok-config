# ngrok-config
#### This help user to configure ngrok to start with 3 port ready for port-forwarding..! also added files and command to create new service that can run ngrok in background 

- copy ngrok.service to systemd

    ```bash
    sudo mv ngrok.service  /etc/systemd/system/ngrok.service
    ```
- edit the username in ngrok.service accoding to your system-setup
    ```bash
    sudo nano  /etc/systemd/system/ngrok.service
    ```
- copy the ngrok.conf file to /.config/
    ```bash
    sudo mv ngrok.config  /home/($USER)/.config/ngrok/ngrok.config
    ```
