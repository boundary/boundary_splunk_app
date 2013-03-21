Boundary + Splunk App
===================

The Boundary Splunk app provides app topology integration and time-series app conversation data from Boundary to Splunk.

Boundary enables customers to monitor and improve application performance. If you have business-critical services deployed in cloud or hybrid IT infrastructures, Boundary can help you ensure these services deliver optimal performance and uptime.

The Boundary app for Splunk feeds information about app topology, latency, and app-to-app conversation information into your Splunk environment.

---

### Getting Started

Configuring the Boundary Splunk app takes just a couple steps.

##### Adding Your Credentials

First, open up the "boundary.conf" file in a text editor such as vim or nano. This file is located in `$SPLUNK_HOME/etc/apps/boundary/local/boundary.conf`. Then, add your Boundary "organization ID" and API key where directed at the top of the configuration file. You can find your organization ID and API key by logging in at [http://app.boundary.com](http://app.boundary.com) and clicking "Organization » Org Settings" at the top right. A completed file will look like:

    [boundary]
    org_id=xxxxxxxxxxxxxxxxxxxxxxxxxxxx
    api_key=xxxxxxxxxxxxxxxxxxxxxxxxxxx
    api_base=https://api.boundary.com
    meter_info_output=$SPLUNK_HOME/etc/apps/boundary/lookups/meter_info.csv
    discovery_output=$SPLUNK_HOME/etc/apps/boundary/lookups/discovery.csv
    app_map_output=$SPLUNK_HOME/etc/apps/boundary/lookups/app_map.csv
    app_to_app_output=$SPLUNK_HOME/etc/apps/boundary/lookups/app_to_app.csv
 
##### Applying the Configuration

There's just one last step: we need to apply this configuration. To do this, cd to `$SPLUNK_HOME/etc/apps/boundary/bin` and run the following command:

        ./configure

Finally, restart Splunk to reload the app with your configuration applied.

And you're done! With your configuration set, applied, and Splunk restarted, you're good to go!

---

For support, please contact support@boundary.com.