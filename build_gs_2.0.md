To build Version 1.0 (SimpleDB) of GenomeSpace:
```
sudo su
cd /mnt/genomespace/SRC/combined
mvn clean install -PdeployLocal -Dmaven.test.skip=true -DskipTests
```

To start the server
```
cd /mnt/genomespace/DEVDEPLOY/virgo/bin
./startup.sh
```
