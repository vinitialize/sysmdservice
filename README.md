**Dummy Systemd Service**
==========================

**Overview**
------------

This is a simple systemd service project that demonstrates how to create and manage a long-running service on Linux systems. The service writes log messages to a file every 10 seconds.

**Usage**
---------

To get started, clone this repository and follow the instructions below:

1. **Create a service file**: Create a new directory called `services` in your project root and add the `dummy.service` file inside.
2. **Edit the service file**: Edit the `dummy.service` file to customize its behavior (e.g., change the log file location or script execution).
3. **Run the service**: Run `systemctl enable dummy` to enable the service, followed by `systemctl start dummy` to start it.

**Service File Structure**
-------------------------

The following is an example of what the `dummy.service` file should contain:
```bash
[Unit]
Description=Dummy Application Service
After=network.target

[Service]
User=<your-username> `example: root`
ExecStart=/usr/bin/bash /path/to/dummy.sh
Restart=always

[Install]
WantedBy=multi-user.target
```
**Scripts**
---------
```bash
#!/bin/bash

while true; do
  # Log a message to the log file every 10 seconds
  echo "$(date) - DUMMY APPLICATION IS RUNNING" >> /var/log/dummy.service.log
  sleep 10
done

```

* `dummy.sh`: This script writes log messages to the log file every 10 seconds. You can customize this script to suit your needs.

**Example Use Case**
-------------------

To use this project, simply clone it and run `systemctl enable dummy` followed by `systemctl start dummy`. The service will write log messages to a file called `dummy.log` in the same directory as the service file.

**Troubleshooting**
------------------

* If you encounter errors when running the service, check the systemd logs for more information.
* You can also use the `journalctl` command to view the service's logs and diagnostics.


**License**
---------

This project is licensed under the MIT License. See the [LICENSE file](LICENSE) for more information.

**Reference**
-----------
[Roadmap.sh](https://roadmap.sh/projects/dummy-systemd-service)
