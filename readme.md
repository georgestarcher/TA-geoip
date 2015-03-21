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
2. This TA may not work well in a search head cluster. I have not tested it.
