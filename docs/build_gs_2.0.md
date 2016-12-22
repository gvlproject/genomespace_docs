# Building v2.0 of GenomeSpace



## Building for the first time?

Ensure you have started the cache:
```
cd ~/genomespace/activeMQ/apache-activemq-5.9.0/bin/
nohup ./activemq console &
```

For the database machine- Ensure you have edited `/etc/mongod.conf` file to add the IP of the DB machine:
```
comma bind_ip = 127.0.0.1,<GENOMESPACE_DB_MACHINE_IP>
```

Add the DB machine IP into the genomespace env-dev.properties file. More info on this file is below.

## Building GS
**NOTE: There is a script called 'build' inside SRC/combined that automates this process.**

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
**NOTE: There is a script called 'build' inside SRC/combined that automates this process.**

If you experience tomcat/maven caching issues (i.e. your changes aren't being reflected after a build/restart):
```
rm -r /var/lib/tomcat7/webapps/datamanager*
rm -r /var/lib/tomcat7/webapps/atm*
rm -r /var/lib/tomcat7/webapps/identityServer*
rm -r /var/lib/tomcat7/webapps/jsui*
```
Then re-build the code and restart the server.
