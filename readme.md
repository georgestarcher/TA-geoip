# TA-geoip : Splunk Add-on for Auto Updating the free Maxmind GeoIP Database

Author: George Starcher (starcher)
Email: george@georgestarcher.com

#Description:

The Splunk Add-on TA-geoip is just a rough TA to make a Splunk server monthly download the database used by the iplocation command.
It currently is coded for just a linux server. It could use a good bit of polish but it is usable.


#SETUP:

1. Edit the bin/update.sh script and leave either the wget or curl lines commented out. Leave the command your system supports active.


#COMMENTS:

1. The scheduled search is scheduled for the 10th of each month.  Change the schedule as desired.
2. This TA does NOT work well in a large Splunk environments. If you have the TA download the same database from Maxmind in same time frame via an externally NAT'd IP will resemble a DOS to them and you could be blocked from downloading. Consider not using this TA as is, download the DB centrally and use something like rsync etc to distribute it across your Splunk systems.
