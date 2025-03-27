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




