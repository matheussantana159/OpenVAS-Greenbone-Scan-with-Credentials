# OpenVAS-Greenbone Scan with Credentials
Using Greenbone Community Edition to scan a network with Credentialed user.

<h2>Prerequisites</h2>

One VM each with the following OS.

  - Windows 10 ISO
  - Kali Linux

<h2>Installation</h2>

1. After starting up both VM's and updating to latest versions, on kali download latest Greenbone version. 

  ```bash
  sudo apt install gvm
  ```

2. Configure Community Edition and *NOTE DOWN* the provided Admin password from output.
  
  ```bash
  sudo gvm-setup
  ```

3. Check installation status.

  ```bash
  gvm-check-setup
  ```

When running it for the first time check the IP:PORT it defaults to in the web browser, loggin in after the session you can use the commands to start and stop 

```bash
sudo gvm-start
sudo gvm-stop
```

<h2>Setting up scans</h2>

Optionally Adjust groups and permissions according to requirements.

  ```bash
  sudo useradd -r -M -U -G sudo -s /usr/sbin/nologin gvm
  
  ```

1. Before starting up scans check the feed status and make sure they are up to date. 
    - Once logged in, top menu bar under *Administration -> Feed Status*
    - If any of them are old (NVT/SCAP/CERT/GVMD-DATA) in terminal run the following commands to force updates.

  ```bash
  sudo greenbone-feed-sync --type NVT
  sudo greenbone-feed-sync --type SCAP
  sudo greenbone-feed-sync --type CERT
  sudo greenbone-feed-sync --type GVM-DATA
  ```

<h2>Configuring a Network Scan</h2>
  
  1. Login
    - Navigate to *Scans > Tasks*
  2. Creating a Task
     - Click *New Task* and input a recognizable name (e.g., IP Network Scan).
     - Scan Targets, create one or more targets and add respective IP addresses
     - Scanning, ensure *OpenVAS Defualt* or *OpenVAS Scanner* is selected
     - Scan config, make sure to pick the scan you want *Full and Fast*, *Full and very deep*, *Host Discovery*, or even a custom scan.
  3. Schedule (Optional)
  4. Credentials (Optional, one was set up for the network)
     - Configuration > Credentials
         - Set up new with corrisponding username and password.
     - If performing an auth scan check SSH/SMB/ESXi under credential scanning on task scan.
  5. Start the Task

<h2>Review and Fine-Tune Scan Results</h2>

  - After each scan a report will generate and will typically have reccomended solution or patches.

<h2>Advanced Configurations</h2>

  - Custom port lists
  - Performace Tuning
  - Alert and Notifications



















