# OpenStack Swift

The VLSCI-developed swift functionality is done very similarly to s3.

File upload: SwiftMultipartUploadInfoManager.java
Small objects OK in one piece, bigger files are split and done using a multipart upload.
JSUI will decide if its a multipart upload or not.
There'll be a signed URL for the upload to swift.

Large objects are stored as Dynamic Large Objects: Basically a whole bunch of file chunks in a folder, with a manifest describing where the chunks are. When you 'download' the tile, swift will sort the chunks by their name and concatenate them to make 1 file.

Connecting a swift container: You need username + password + tenancy + container name. The username+pwd+tenancy combo is stored in RAM, so it's lost when the server is restarted and the password will need to be re-entered. Then all containers in a single tenancy will be re-attached. If you have multiple containers over multiple tenancies, you'll need to re-enter the password multiple times.
