# Identity Server and Manager

- This deals with all things user-related.

### IdentityManager
- This module contains the 'managers' for 3 main things:
    - Users - username, password, etc.
    - UserProfile - this includes things like what tools a user has on their custom toolbars, any other custom settings.
    - Groups - being able to share things with a group of other users. What groups a user manages, what groups they're a member of, etc.

### IdentityServer
- Under 'auth', you'll find 2 folders:
    - 'basic' - this is basic authentication for genomespace- send username, password, it'll give you an auth token.
    - 'openid' - this is OpenID based auth. Often tools (e.g. Galaxy) will use this type of auth to avoid users entering passwords all the time.

- Under 'identity' you'll find some stuff for group management and user management.

### identityserver-messages
- Inside the 'identityserver-messages' module, you'll find the model for the user related things e.g. User, Groups, etc. This module is a dependency of lots of things, e.g. CDK.

### identityserver-common
- Inside the 'identityserver-common' module you'll find some user constants.
