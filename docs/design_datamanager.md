# Data Manager

### dm-core
Dm-core is one of the biggest GS modules... it's messy!

- Most (but unfortunately not all...) of the storage specific stuff is under 'storage', and then the respective folder for the storage type you're dealing with.
- The rest of the main stuff lives in 'core'
- The storage stuff is relatively abstracted out with Interfaces etc, majority of which live in 'core', and any implementation will generally have 'Impl' at the end of the name.
- Debugging issues with storage: apart from the stack trace, any other issues can generally be solved by starting inside 'resource', finding the corresponding URL segment, and following through the code.
- Logging can be easily done using the 'swiftlogger' class (can't remember it's exact location... easily searchable though).

### dm-messages

Contains a whole bunch of stuff mosyly used by other modules and the CDK.

### dm-security

Contains stuff to do with ACL's (access control).
