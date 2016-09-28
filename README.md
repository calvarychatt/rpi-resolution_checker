# rpi-resolution_checker
A simple set of scripts/commands to ensure that the resolution is correct on a Raspberry pi.

<code>sudo apt-get update</code>

<code>sudo apt-get install sendmail</code>

<code>sudo sendmailconfig</code>

Edit /etc/hosts to match the following:

127.0.0.1	localhost
127.0.0.1
127.0.0.1 localhost calvarykids.pi raspberrypi
::1		localhost ip6-localhost ip6-loopback
ff02::1		ip6-allnodes
ff02::2		ip6-allrouters

127.0.1.1	raspberrypi



Answer yes to all the defaults.  This should set up Sendmail with the basics we need.

We can test sendmail using the following:

echo "Calvary Kids Pi is down" | sendmail -v yourname@gmail.com

replace yourname@gmail.com with the address you would like the email sent to.  It will show up in the spam folder because it is coming from an unverified address since we are not using any sort of relay.  This is fine for sending ourselves alerts.  You can set up filters in Gmail to send these emails directly to the inbox and bypass the spam folder.  

To get it going we can just run:

<code>nohup ./resolution_checker</code>
