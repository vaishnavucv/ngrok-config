# ngrok-config

### this repo is under WIP

#### This help user to configure ngrok to start with 3 port ready for port-forwarding..! also added files and command to create new service that can run ngrok in background 

- Clone the repo
    ```bash
    git clone https://github.com/vaishnavucv/ngrok-config/
    cd ngrok-config
    chmod +x *
    ```
- Install ngrok
    ```bash
    sudo apt-get update
    sudo apt-get install snap -y
    sudo snap install ngrok
    ```
- Run the following command to add your authtoken to ngrok.yml
    ```bash
    /snap/bin/ngrok config add-authtoken 26bEfSIlR1IcEEayMpRQlj0ttGw_3hrWetKnHZ4FMXc9hDt3Q
    ```
- copy ngrok.service to systemd

    ```bash
    sudo mv ngrok.service  /etc/systemd/system/ngrok.service
    ```
- replace the username in ngrok.service accoding to your system username
    ```bash
    sudo sed -i 's/^User=.*/User=justuser/'  /etc/systemd/system/ngrok.service
    ```
- copy the ngrok.conf file to /.config/
    ```bash
    mv ngrok  /home/$USER/.config/
    ```
- Change username in ngrok.yml, replace justuser with your username
    ```bash
    sed -i 's/^User=.*/User=justuser/'  /home/$USER/snap/ngrok/174/.config/ngrok/ngrok.yml
    ```
- Start ngrok.service and check status
    ```bash
    sudo systemctl daemon-reload
    sudo systemctl start ngrok.service
    sudo systemctl enable ngrok.service
    sudo systemctl status ngrok.service
    ```
- 