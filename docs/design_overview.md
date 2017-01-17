# GenomeSpace Design Overview

GenomeSpace is made up of the following main components:

- Analysis and Tool Manager (ATM) - Handles everything tool related.
- Data Manager - Handles everything data related.
- Identity Server & Manager - Handles everything user related.
- JSUI - The user interface. Mostly the standard vanilla javascript, html, css, but with a bit of AngularJS.
- The database - Stores all info re: tools, connected data sources, public data, user info, etc.
- Client Development Kit - a way for developers to interact with GS without the UI. It's a jar file.
