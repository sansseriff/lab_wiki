After a power outage, the Skynet microserver will not start automatically. This can bring many lab operations to a halt because the data drive, lab wiki (Wikijs), DNS, and wireguard VPN all run on Skynet. 

Skynet does not automatically start because the boot hard drive is encrypted and a password must be entered to star the machine. 

### 1: Start with Skynet off. 

If Skynet appears to be on (the power button is lit up) but is not responding to ssh, hold the power button for 10 seconds to fully turn it off. 

### 2. Plug a VGA monitor, keyboard and mouse in. 
There should already be a vga cable dangling from behind Skynet. 

### 3. Start Skynet with the the front power button. 
Then wait until a password prompt appears on the screen. This can take a while, may be a couple minutes. It's very slow to start up. The password is the usual lab password. 

### 4. Start the wikijs server.
For whatever reason, the wiki server does not start automatically. Long term, someone should either figure this out, or ideally migrate all the data off the existing installation and use a [docker or docker-compose](https://docs.requarks.io/install/docker) installation instead. Until that's figured out, we are stuck manually starting the wiki server. 

Still using the locally attached monitor, keyboard and mouse, log in as the wiki user using the usual password. Open a terminal and navigate to '/mnt/data/wiki/server' [^1]

[^1]: If running this command in the `/server` directory does not work, go up one directory to `/wiki` and try again. I'm writing this from memory and I can't test right now.


```shell
cd /mnt/data/wiki/server/
```
Become root with the `su` command, and enter the password. 
Then run:
```shell
npm start
```
Leave the terminal open, remove the VGA monitor, mouse and keyboard. Everything else skynet related should start automatically. 

#### Isn't that a hacky and stupid way to start the server?
Yes, I don't know a better way. You're welcome to look into a better way of doing it, or asking Alex W. 





