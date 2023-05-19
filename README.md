<div align="center">
    <a href="https://github.com/zigbee2mqtt/hassio-zigbee2mqtt">
        <img width="150" height="150" src="logo.png">
    </a>
    <br>
    <br>
    <div style="display: flex;">
        <a href="https://github.com/zigbee2mqtt/hassio-zigbee2mqtt/actions?query=workflow%3ACI">
            <img src="https://github.com/zigbee2mqtt/hassio-zigbee2mqtt/workflows/CI/badge.svg">
        </a>
        <a href="https://github.com/zigbee2mqtt/hassio-zigbee2mqtt/releases">
            <img src="https://img.shields.io/github/release/zigbee2mqtt/hassio-zigbee2mqtt.svg">
        </a>
        <a href="https://github.com/zigbee2mqtt/hassio-zigbee2mqtt/stargazers">
            <img src="https://img.shields.io/github/stars/zigbee2mqtt/hassio-zigbee2mqtt.svg">
        </a>
        <a href="https://discord.gg/dadfWYE">
            <img src="https://img.shields.io/discord/556563650429583360.svg">
        </a>
        <a href="http://zigbee2mqtt.discourse.group/">
            <img src="https://img.shields.io/discourse/https/zigbee2mqtt.discourse.group/status.svg">
        </a>
    </div>
    <h1>Official Zigbee2MQTT Home Assistant addon</h1>
</div>

## Installation
1. If you don't have an MQTT broker yet; in Home Assistant go to **[Settings → Add-ons → Add-on store](https://my.home-assistant.io/redirect/supervisor_store/)** and install the **[Mosquitto broker](https://my.home-assistant.io/redirect/supervisor_addon/?addon=core_mosquitto)** addon.
1. Go back to the **Add-on store**, click **⋮ → Repositories**, fill in</br>  `https://github.com/gluoncompany/gluon-hassio-zigbee2mqtt` and click **Add → Close** or click the **Add repository** button below, click **Add → Close** (You might need to enter the **internal IP address** of your Home Assistant instance first).  
[![Open your Home Assistant instance and show the add add-on repository dialog with a specific repository URL pre-filled.](https://my.home-assistant.io/badges/supervisor_add_addon_repository.svg)](https://my.home-assistant.io/redirect/supervisor_add_addon_repository/?repository_url=https%3A%2F%2Fgithub.com%2Fgluoncompany%2Fgluon-hassio-zigbee2mqtt)
3. The repository includes proxy plugins.
4. Click on the addon and press **Install** and wait till the addon is installed.
5. Click on **Configuration**
    - If you are **not** using the Mosquitto broker addon fill in your MQTT details (leave empty when using the Mosquitto broker addon). Format can be found [here](https://www.zigbee2mqtt.io/guide/configuration/mqtt.html#server-connection), but skip the initial `mqtt:` indent. e.g.: <br>
        ```yaml
        server: mqtt://localhost:1883
        user: my_user
        password: my_password
        ```
    - Fill in the serial details (e.g. port of your USB coordinator). Format can be found [here](https://www.zigbee2mqtt.io/guide/configuration/adapter-settings.html#adapter-settings), but skip the initial `serial:` indent. e.g.: <br>
        ```yaml
        port: /dev/ttyUSB0
        ```
    - If you don't know the port and you have just one USB device connected to your machine try `/dev/ttyUSB0`. Else use the [Home Assistant CLI](https://www.home-assistant.io/common-tasks/os#home-assistant-via-the-command-line) and execute `ha hardware info` to find out. 
    - Click **Save**
    - **Tip:** it is possible to refer to variables in the Home Assistant `secrets.yaml` file (not the Zigbee2MQTT one!) by using e.g. `password: '!secret mqtt_pass'`
1. Start the addon by going to **Info** and click **Start**
1. Wait till Zigbee2MQTT starts and press **OPEN WEB UI** to verify Zigbee2MQTT started correctly.
    - If it shows `502: Bad Gateway` wait a bit more and refresh the page.
    - If this takes too long (e.g. 2 minutes +) check the **Log** tab to see what went wrong.


## Credits
- [danielwelch](https://github.com/danielwelch)
- [ciotlosm](https://github.com/ciotlosm)
- [Koenkk](https://github.com/Koenkk)