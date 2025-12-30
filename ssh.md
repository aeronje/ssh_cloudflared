# Establishing SSH connection via VSCode

***This instruction is applicable only if tunnel has been established from the server-side. Please disregard these instructions if no established SSH server.

**1**

***Download [cloudflared](https://developers.cloudflare.com/cloudflare-one/networks/connectors/cloudflare-tunnel/downloads/)***

**2**

***Rename the file to cloudflared.exe or cloudflared.deb to easily remember.***

**3**

***Navigate to the path or directory where you rename the file and execute it via single command***

***Just like this for Windows when you do it in PowerShell: C:\Users\userName\Downloads\cloudflared.exe access ssh --hostname ssh.hostname***

***or in Git Bash: ./cloudflared.exe access ssh --hostname ssh.hostname.com***

***Do the needful for authentication***

**4**

***Go to VSCode and install the extension for Remote Explorer developed by Microsoft***

***Click the ```Remote Window``` button from the lower left corner and click ```Connect to Host...``` from the search***
***Click ```Configure SSH Hosts...```
***Choose the one from the ```Users``` directory

***Below is the sample config which will be different from your setup***

```
Host tunnelName-ssh
    HostName ssh.hostname
    User user
    ProxyCommand "C:/Users/userName/Downloads/cloudflared.exe" access ssh --hostname %h
```

**5**

***Do the needful for authentication in the OS level and start using the Remote Explorer in VSCode***

***If you do not wish to use VSCode, you may continue the SSH via terminal by just running this command: ```ssh -o ProxyCommand="C:\Users\userName\Downloads\cloudflared.exe access ssh --hostname %h" user@ssh.hostname```
