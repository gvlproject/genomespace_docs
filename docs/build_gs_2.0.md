# Building v2.0 of GenomeSpace

To build Version 2.0 (MongoDB/Tomcat7) of GenomeSpace:
```
sudo su
cd /home/ubuntu/genomespace/SRC/combined
mvn -X clean install  -am -DskipTests -Denv-properties-file=/home/ubuntu/genomespace/env-dev.properties -P deployToLocalTomcat -Dmaven.test.skip=true
```
Ensure you have a env-dev.properties file in the home directory, which contains the URL's and credentials required for GenomeSpace. See [this example](https://github.com/gvlproject/gvl.ansible.genomespace/blob/new_genomespace/templates/env-dev.properties.j2)

To start the server
```
sudo service tomcat7 restart
```

## Caching issues

If you experience tomcat/maven caching issues (i.e. your changes aren't being reflected after a build/restart):
```
rm -r /var/lib/tomcat7/webapps/datamanager*
rm -r /var/lib/tomcat7/webapps/atm*
rm -r /var/lib/tomcat7/webapps/identityServer*
rm -r /var/lib/tomcat7/webapps/jsui*
```
Then re-build the code and restart the server.
