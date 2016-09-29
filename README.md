# rpi-resolution_checker
A simple set of scripts/commands to ensure that the resolution is correct on a Raspberry pi.  I wanted a dead simple way to be able to monitor a raspberry pi and have it send me an email alert if something was wrong.  In this case we are checking to make sure that it is set to the correct resolution.  The purpose for this is because we have had issues with one Pi in particular changing to a non standard resolution that is not accepted by the tv.  It is not yet known why this is occurring.  At this time I have tried swapping the SD card and no change.  I have now swapped out the pi to see if that resolves the issue.

The purpose of this project is to set up a simple alert system so that I know exactly when the problem starts and can reimage the SD card and correct the problem asap.  I originally was using sendmail for this but then discovered that it can be done through a simple curl command.  I have put the curl command into a bash script named sendmail just to make it easier to call from my resolution_checker script. 

You will need to fill in the appropriate information in the sendmail script such as the username:password used to authenticate with Gmail, as well as the to and from email address.  Everything else should be good to go.  Just clone the repo, make sure to add execute permissions to sendmail and resolution_checker and then run:

<code>git clone https://github.com/calvarychatt/rpi-resolution_checker.git</code>


<code>rpi-resolution_checker/resolution_checker & disown</code>

This will run our resolution_checker in the background and detach it from our session ensuring that it stays running when we close out the session, however as long as the session is active, we will receive output from the script in our current session

This should run our check every 30 seconds in an infinite loop.  If when it goes through the loop it detects something other than 1920x1080, we should receive an email.
