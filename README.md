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

* sudo systemctl enable service.name
* sudo systemctl start service.name
* sudo systemctl restart service.name
* sudo systemctl stop service.name
