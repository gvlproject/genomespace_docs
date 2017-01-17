# GenomeSpace Australia Custom Components

Things that were developed at VLSCI:

- All of the OpenStack Swift functionality. I.e. the ability to connect a swift container, upload to it, download from it, get public URL's, and all other file operations. Note that there is no sharing with Swift due to OpenStack's design.
- The 'import from URL' functionality.

Things that differ between Broad's GS and GS AU:

- We no longer support Dropbox & Google Drive. This is because uploads to these storage types actually go via the genomespace s3 bucket and users are not informed of this.
- A lot of the Broad's external resources e.g. recipes, their user groups, etc are not linked under the 'help' section.
- There's an extra step in setting up a private s3 bucket - adding the CORS config.
- Users don't have a 'home' folder, i.e., no default storage.
- The ability to upload custom tool icons is turned off due to lack of home folder.
