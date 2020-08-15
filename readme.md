# TA-geoip : Splunk Add-on for containing an updated copy of the free Maxmind GeoIP Database

Author: George Starcher (starcher)
Email: george@georgestarcher.com

# Description:

The Splunk Add-on TA-geoip is just container TA to house a downloaded update of the database used by the iplocation command.
The configuration tells Splunk to use the file in the TA-geoip/bin location and to blacklist the mmdb file from replication to keep it out of the search bundle.

# COMMENTS:

1. Maxmind updated how they allow downloading of the free databases to require a login. You also cannot auto download without a paid license key. Regardless of how you obtain the mmdb file you need to update it on ALL search heads and indexers to ensure the iplocation has updated information as you can obtain.
2. You will need to follow their instructions for setting up an account and download it to a central location. If you mass download it from a large number of servers you could get blocked for appearing to be a DDoS against Maxmind.
3. Use your organization's configuration automation tools to distribute it to all the Search Heads and Indexers and place the file into TA-geoip/bin/GeoLite2-City.mmdb
4. If you deploy this configuration container app and do not place the mmdb in bin Splunk will simply default to the installation's default copy. This will most likey be very out of data geo information.

# Reference: 

* https://blog.maxmind.com/2019/12/18/significant-changes-to-accessing-and-using-geolite2-databases/


