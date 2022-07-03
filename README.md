# Springboot JAR Application as Service
Make a jar application as service at linux

* `sudo nano /usr/lib/systemd/system/name.service` <name>  is service name.
*  Write following code into file name.service

```
# Name Service
[Unit]
Description=Manage Java service
Documentation=https://serviceURL.io/

[Service]
WorkingDirectory=/path/to/jarfiledirectory
ExecStart=/bin/java -Xms128m -Xmx256m -jar jarfile.jar
User=ubuntu
Group=ubuntu
Type=simple
Restart=on-failure
RestartSec=10

[Install]
WantedBy=multi-user.target
```

* `sudo systemctl enable name.service`
* `sudo systemctl start name.service`
* `sudo systemctl restart name.service`
* `sudo systemctl stop name.service`
