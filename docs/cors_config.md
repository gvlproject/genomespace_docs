# AWS CORS Configuration

See below for the CORS config to add to the default AWS S3 bucket attached to GenomeSpace.

```
<CORSConfiguration>
    <CORSRule>
        <AllowedOrigin>PUT GENOMESPACE URL HERE</AllowedOrigin>
        <AllowedMethod>GET</AllowedMethod>
        <AllowedMethod>PUT</AllowedMethod>
        <AllowedMethod>POST</AllowedMethod>
        <AllowedMethod>DELETE</AllowedMethod>
        <MaxAgeSeconds>3000</MaxAgeSeconds>
        <AllowedHeader>*</AllowedHeader>
    </CORSRule>
</CORSConfiguration>
```
