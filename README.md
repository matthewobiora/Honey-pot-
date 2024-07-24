# Honeypot Project

## Introduction
A honeypot is a security mechanism that creates a decoy system to attract cyber attackers. It serves as a trap to detect, deflect, or study hacking attempts and gather valuable information about cyber threats.

## Project Overview
In this project, I have set up a honeypot using T-Pot on a cloud server provided by Vultr. T-Pot is an all-in-one multi-honeypot platform. This README will guide you through the steps to deploy the honeypot and provide an overview of the features available in T-Pot.

## Deployment Steps

### Sign up for Vultr
Go to [Vultr](https://my.vultr.com/) and create an account.

### Deploy a New Server
1. Click on **Deploy** to create a new server.
2. Select **Cloud Compute - Shared CPU**.
   ![Cloud Compute - Shared CPU](https://github.com/matthewobiora/Risk-Assessment-Report/blob/main/1.png?raw=true) <!-- Replace with your actual image path -->
3. Choose a server location closest to you (e.g., New York).
   ![Select Server Location](https://github.com/matthewobiora/Risk-Assessment-Report/blob/main/2.png?raw=true) <!-- Replace with your actual image path -->
4. Select an operating system (e.g., Ubuntu).
   ![Select Server Image](https://github.com/matthewobiora/Risk-Assessment-Report/blob/main/3.png?raw=true) <!-- Replace with your actual image path -->
5. Choose the server plan (e.g., Regular Cloud Compute).
6. Select the 160GB SSD.
   ![Select Server Plan](https://github.com/matthewobiora/Risk-Assessment-Report/blob/main/4.png?raw=true) <!-- Replace with your actual image path -->
7. Name your server and click **Deploy Now**.
   ![Name and Deploy Server](https://github.com/matthewobiora/Risk-Assessment-Report/blob/main/8.png?raw=true) <!-- Replace with your actual image path -->
8. Wait until the server status is **Running**.
   ![Server Running](https://github.com/matthewobiora/Risk-Assessment-Report/blob/main/7.png?raw=true) <!-- Replace with your actual image path -->
9. Click on the **View Console** icon to access your server.
   ![View Console](https://github.com/matthewobiora/Risk-Assessment-Report/blob/main/9.png?raw=true) <!-- Replace with your actual image path -->

### Configure Firewall
1. Click on **Settings** and create a new firewall group.
   ![Create Firewall Group](https://github.com/matthewobiora/Risk-Assessment-Report/blob/main/10.png?raw=true) <!-- Replace with your actual image path -->
2. Go back to the firewall section, select the newly created firewall group, and update it to restrict access temporarily.
   ![Update Firewall](https://github.com/matthewobiora/Risk-Assessment-Report/blob/main/11.png?raw=true) <!-- Replace with your actual image path -->

### Install T-Pot
1. Clone the T-Pot GitHub repository:
   ```bash
   git clone https://github.com/telekom-security/tpotce
