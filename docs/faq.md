# Frequently Asked Questions

## Updating the URL - a checklist
    1. Find & replace all URL's in the source code (by using find/replace in eclipse)
    2. Open the GenomeSpace env-dev.properties file, and change all the URL's.
    3. Build (using build script in SRC/combined).
    4. Update the config.war file through the Tomcat Manager application.

## Things that commonly go wrong
    1. Tomcat7 needs restarting. This will solve 99% of GS problems.
    2. The ActiveMQ cache hasn't been started.
    3. The config.war file hasn't been updated.
    4. Something in the GenomeSpace properties file is wrong (e.g. a URL, Database IP)
