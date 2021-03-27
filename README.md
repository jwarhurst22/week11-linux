# week11-linux - Joshua Warhurst A01238312 - Friday March 26th, 2021

## weather-report (script)
1. Before you begin writing your script, in the directory your writing your script. You first want to `export PATH=$PATH:/place/with/the/file`command so you can call your        script in any directory.
2. When you `cd` into your directory that you want to write the script, do the command `vim [script-name]` to begin writing your script.
3. Begin your script by using adding `#!/bin/bash` at the top of the vim editor (so bash can properly buffer your script)
4. Now add the ```curl [link] > weather.txt``` command so the output of the `curl` command with the link that you want to capture is written into a file called 'weather.txt.'

## service file
1. You can begin writing your service file in the same directory with your other files & script by doing the command ```sudo vim your-servicename.service```
2. In your VIM editor, make sure your service file is in the following format:
```
[Unit]
Description=description of your service file
Wants=your-timername.timer

[Service]
Type=oneshot
ExecStart=path/to/your/script
WorkingDirectory=/home/vagrant/path/to/dir

[Install]
WantedBy=multi-user.target
```

## timer file
1. You can begin writing your service file in the same directory with your other files & script by doing the command ```sudo vim your-timername.timer```
2. In your VIM editor, make sure your service file is in the following format:
```
[Unit]
Description=description of your timer file
Requires=your-servicename.service

[Timer]
Unit=your-servicename.service
OnCalender=*-*-* *:*:00

[Install]
WantedBy=timers.target
```



