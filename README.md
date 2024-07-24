# Honeypot Project

## Introduction
A honeypot is a security mechanism designed to create a decoy system that attracts cyber attackers. It functions as a trap to detect, deflect, or study hacking attempts, and helps gather valuable information about cyber threats.

## Project Overview
In this project, I have set up a honeypot using T-Pot on a cloud server provided by Vultr. T-Pot is an all-in-one multi-honeypot platform. This README will guide you through the steps to deploy the honeypot and provide an overview of the features available in T-Pot.

## Deployment Steps

### Sign Up for Vultr
1. Visit [Vultr](https://my.vultr.com/) and create an account.

### Deploy a New Server
1. Click on **Deploy** to create a new server and select on **cloud compute - shared CPU**.

   ![Cloud Compute - Shared CPU](https://github.com/matthewobiora/Risk-Assessment-Report/blob/main/1.png?raw=true) <!-- Replace with your actual image path -->

2.  Choose a server location closest to you (e.g., New York).

   ![Select Server Location](https://github.com/matthewobiora/Risk-Assessment-Report/blob/main/2.png?raw=true) <!-- Replace with your actual image path -->

3. Select an operating system (e.g., Ubuntu).

   ![Select Server Image](https://github.com/matthewobiora/Risk-Assessment-Report/blob/main/3.png?raw=true) <!-- Replace with your actual image path -->

4. Choose the server plan (e.g., Regular Cloud Compute) and go for the 160GB SSD.
   ![Select Server Plan](https://github.com/matthewobiora/Risk-Assessment-Report/blob/main/4.png?raw=true) <!-- Replace with your actual image path -->


5.Name your server and click **Deploy Now**.


   ![Name and Deploy Server](https://github.com/matthewobiora/Risk-Assessment-Report/blob/main/servername.png?raw=true) <!-- Replace with your actual image path -->

6.  Wait until the server status is **Running**.

   ![Server Running](https://github.com/matthewobiora/Risk-Assessment-Report/blob/main/7.png?raw=true) <!-- Replace with your actual image path -->

7.Click on the **View Console** icon to access your server.

   ![View Console](https://github.com/matthewobiora/Risk-Assessment-Report/blob/main/8.png?raw=true)    ![View Console](https://github.com/matthewobiora/Risk-Assessment-Report/blob/main/9.png?raw=true)<!-- Replace with your actual image path -->

 CONFIGURE FIREWALL
1. Click on **Settings** and create a new firewall group and then click on (manage) to create a new firewall

   ![Create Firewall Group](https://github.com/matthewobiora/Risk-Assessment-Report/blob/main/10.png?raw=true) <!-- Replace with your actual image path -->


2. Go back to the firewall section, select the newly created firewall group, and then click on it so as to update it with some rules of your choice.

   ![Update Firewall](https://github.com/matthewobiora/Risk-Assessment-Report/blob/main/11.png?raw=true) ![Update Firewall](https://github.com/matthewobiora/Risk-Assessment-Report/blob/main/firewall%20rules.png?raw=true)<!-- Replace with your actual image path -->




## Installation

### Clone the T-Pot GitHub Repository
1. Open a terminal and run:
    ```bash
    git clone https://github.com/telekom-security/tpotce
    ```

### Navigate to the `tpotce` Directory
2. Change into the `tpotce` directory:
    ```bash
    cd tpotce
    ```

### Run the Installer
3. Execute the installation script:
    ```bash
    ./install.sh
    ```

   ⚠️ **Installer Details:**
   Depending on your Linux distribution, the installer will:
   - Change the SSH port to `tcp/64295`
   - Disable the DNS Stub Listener to avoid port conflicts with honeypots
   - Set SELinux to Monitor Mode
   - Set the firewall target for the public zone to `ACCEPT`
   - Add Docker's repository and install Docker
   - Install recommended packages
   - Remove packages known to cause issues
   - Add the current user to the Docker group (allow Docker interaction without `sudo`)
   - Add `dps` and `dpsw` aliases (`grc docker ps -a`, `watch -c "grc --colour=on docker ps -a"`)
   - Add `la`, `ll`, and `ls` aliases (for `exa`, an improved `ls` command)
   - Add `mi` (for `micro`, a great alternative to `vi` and/or `nano`)
   - Display open ports on the host (compare with T-Pot required ports)
   - Add and enable `tpot.service` to `/etc/systemd/system` so T-Pot can automatically start and stop

   Follow the installer instructions; you will have to enter your user (sudo or root) password at least once. Check the installer messages for errors and open ports that might cause port conflicts.

### Reboot Your Server
4. Reboot the server to complete the installation:
    ```bash
    sudo reboot
    ```

## Access the Honeypot

After the reboot, T-Pot will present you with the IP, web, and admin details. Access the web interface using the provided IP and port via HTTPS. Bypass the warning page by clicking Advanced and use your credentials to log in.

## Modifying Firewall Rules

To allow public access to your honeypot, update the firewall rules to permit traffic to the necessary ports.

## T-Pot Features Overview
![Create Firewall Group](https://github.com/matthewobiora/Risk-Assessment-Report/blob/main/12.png?raw=true)

### Attack Map
![Create Firewall Group](https://github.com/matthewobiora/Risk-Assessment-Report/blob/main/14.png?raw=true)

- Visualizes the origin of attacks, the honeypots capturing the data, and provides insights into the top hits.

### CyberChef
![Create Firewall Group](https://github.com/matthewobiora/Risk-Assessment-Report/blob/main/15.png?raw=true)
- A web-based tool for analyzing and decoding data. It simplifies complex data transformations.

### Elasticvue
![Create Firewall Group](https://github.com/matthewobiora/Risk-Assessment-Report/blob/main/16.png?raw=true)
- A GUI for managing and inspecting Elasticsearch indices, offering a user-friendly interface for data analysis.

### Kibana
![Create Firewall Group](https://github.com/matthewobiora/Risk-Assessment-Report/blob/main/17.png?raw=true)
- Provides dynamic dashboards and visualizations, showing attack metrics, sources, and other critical information.
  ![Create Firewall Group](https://github.com/matthewobiora/Risk-Assessment-Report/blob/main/20.png?raw=true)  ![Create Firewall Group](https://github.com/matthewobiora/Risk-Assessment-Report/blob/main/19.png?raw=true)
  - **Discover:** Practice query skills and learn to use Kibana effectively.
  ![Create Firewall Group](https://github.com/matthewobiora/Risk-Assessment-Report/blob/main/17.png?raw=true)   ![Create Firewall Group](https://github.com/matthewobiora/Risk-Assessment-Report/blob/main/18.png?raw=true)  
  - **Dashboards:** Visualize attack data, including source IPs and attack counts.

### Spiderfoot
![Create Firewall Group](https://github.com/matthewobiora/Risk-Assessment-Report/blob/main/22.png?raw=true)
- A reconnaissance tool that automates the process of gathering intelligence on IP addresses, domain names, email addresses, and other entities.

## Conclusion

This project has significantly improved my cybersecurity skills, especially in setting up and managing honeypots, analyzing attack data, and using advanced tools like Kibana and CyberChef.
