# TA-geoip : Splunk Add-on for containing the free Maxmind GeoIP Database

Author: George Starcher (starcher)
Email: george@georgestarcher.com

# Description:

The Splunk Add-on TA-geoip is container app for the database used by the iplocation command.


# COMMENTS:

1. In 2019 Maxmind changed their free databases to require a login. Also you can only automate the download if you obtain a paid license key. 
2. To properly update the database in Splunk you can use this TA as a container application of the configuration. You must distribute it to all search heads and related indexers.
3. You should download GeoLite2-City.mmdb centrally then use your organization's system automation tool of choice to copy the updated file to TA-geoip/bin/GeoLite2-City.mmdb on EACH search head and indexer directly.
4. Trying to download the file from each server in your environment can get your organization blacklisted due to large number of scheduled downloads directly from Maxmind.
5. Note this TA blacklists the mmdb file from bundle replication in distsearch.conf to help reduce bundle size. You should be updating it via an organizationally selected method from #3 above.
6. If you fail to land the file Splunk will just log an error that it cannot find the database and default to the copy included in your Splunk install which will likely be very outdated. But it will keep the iplocation command working.

# References:

* https://blog.maxmind.com/2019/12/18/significant-changes-to-accessing-and-using-geolite2-databases/

