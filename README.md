# rpi-resolution_checker
A simple set of scripts/commands to ensure that the resolution is correct on a Raspberry pi.


Add the following entry to your crontab

<code>1-59/2 * * * * /usr/bin/resolution_checker >/dev/null 2>&1</code>
