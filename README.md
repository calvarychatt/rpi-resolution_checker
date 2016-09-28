# rpi-resolution_checker
A simple set of scripts/commands to ensure that the resolution is correct on a Raspberry pi.

Change /etc/hosts to match the following:

127.0.0.1	localhost
127.0.0.1
127.0.0.1 localhost calvarykids.pi raspberrypi
::1		localhost ip6-localhost ip6-loopback
ff02::1		ip6-allnodes
ff02::2		ip6-allrouters

127.0.1.1	raspberrypi

Then run:

<code>sudo apt-get update</code>
<code>sudo apt-get install sendmail</code>
<code>sudo sendmailconfig</code>

Follow the prompts to set the default settings.  Test Sendmail using this command:

<code>echo "Calvary Kids Pi is down" | sendmail -v youremail@gmail.com</code>

substitute youremail@gmail.com with the email address you wish to send to.  The email will show up in your spam folder as we have not set up any sort of authentication for the server.  This is fine in the case that we are just using this to alert ourselves of an issue.  You can set up filters in Gmail to send these emails straight to the inbox instead of the spam folder.
