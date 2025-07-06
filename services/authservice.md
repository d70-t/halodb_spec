(auth-service)=
# Auth Service

The Auth Service authenticates users (people & services) for other services.

* identifies users
* attaches rights & roles
* is available to other services to check if requests are valid
* provides decryption keys for encrypted IPLD-blocks (if needed)
* integrates with common authentication providers

## WPs

* specify how other services can use the auth service
* implement the auth service
* run & operate the auth service
