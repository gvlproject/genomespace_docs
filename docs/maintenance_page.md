# Maintenance Page

The maintenance page lives at https://github.com/madiflannery/genomespace_maintenance

It is already inside $TOMCAT_HOME/webapps/maintenance

To put into maintenance mode, make the maintenance page the default webapp:
```
cd $TOMCAT_HOME/webapps
mv ROOT ROOT_TMP
mv maintenance ROOT
```
Make sure you also update the GVL Status page, and pause the UptimeRobot monitor.

You can still access GenomeSpace by adding the /jsui to the URL, so you can test before you launch again.

To take out of maintenance mode:
```
cd $TOMCAT_HOME/webapps
mv ROOT maintenance
mv ROOT_TMP ROOT
```
