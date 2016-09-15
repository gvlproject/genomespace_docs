### How to update the SSL Certificate once expired

Ensure you have root access to the machine.

```
sudo su
cd /mnt/genomespace/DEVDEPLOY/virgo/config
```
Remove all old keys and cert files from the directory.

With the key and certificate in .pem format, do the following steps. You'll need to set a password, for consistency, use the one in the tomcat server.xml file under the SSL connector.
```
openssl pkcs12 -export -inkey genome-edu-au-2016.key -in genome-edu-au-2016.cer -name tomcat -out keystore.p12
keytool -importkeystore -srckeystore keystore.p12 -srcstoretype pkcs12 -destkeystore $JAVA_HOME/jre/lib/security/cacerts
```

If it errors because the certificate is already there, delete the existing one:

```
keytool -delete -alias tomcat -keystore $JAVA_HOME/jre/lib/security/cacerts
```

Finally, create the keystore file Tomcat will use
```
keytool -importkeystore -srckeystore keystore.p12 -srcstoretype pkcs12 -deststoretype jks -destkeystore keystore
```

Then, follow the instructions to [update the genomespace secret key](update_gs_key.md), and rebuild the code.
