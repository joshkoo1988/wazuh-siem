# Wazuh Server Install Guide (via ProxMox VM)

## Description
In this guide, I will walk through how to install a **Wazuh all-in-one server** inside a virtual machine (VM) on ProxMox. Wazuh is an open-source security platform that provides threat detection, incident response, integrity monitoring, and compliance management.

---

## Program Walk-through

1. **Create a ProxMox VM**:
   - Follow the [ProxMox VM Install Guide](https://github.com/joshkoo1988/vm-install)
   - Use Ubuntu Server 22.04 LTS (recommended)

2. **Update and install required packages** inside the VM:
   ```bash
   sudo apt update && sudo apt upgrade -y
   sudo apt install curl unzip apt-transport-https lsb-release gnupg -y

3. **Download the Wazuh quickstart installer script**:
   - Be sure to check official documentation for most updated [install shell script](https://documentation.wazuh.com/current/quickstart.html)
   ```
   curl -sO https://packages.wazuh.com/4.12/wazuh-install.sh && sudo bash ./wazuh-install.sh -a
   
4. Access the Wazuh web interface with https://<WAZUH_DASHBOARD_IP_ADDRESS> and your credentials:
   
    Username: admin
    Password: <ADMIN_PASSWORD>

    - You can find the generated password with the following command
    ```
    sudo tar -O -xvf wazuh-install-files.tar wazuh-install-files/wazuh-passwords.txt

5. [download appropriate agent installer and follow the steps to link agent to the server that was installed](https://documentation.wazuh.com/current/installation-guide/wazuh-agent/index.html)
