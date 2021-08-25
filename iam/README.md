# identity and access management (iam)

----
- [authentication](#authentication)
- [authorization](#authorization)
- [oauth](#oauth)
- [open id connect](#open-id-connect)
- [resources](#resources)
----

## authentication

- allows to identify the claims of an entity 
- examples: username and password, gesture pattern on touchscreen

## authorization

- allows an entity to perform operations based on it' allowed authorisation information
- examples: admin entity to a admin portal, support entity login to care portal


## oauth

- a protocol that controls the authorization of an entity
- terms:
  - authorization server: an access token minting engine
  - resource server: a server which receives and validates the access token
  - client: an application you interact that request access token from authorization server to access resource server
  - resource owner: you
  - grant/grant type: authorization given to the client by the user. example: client credentials, implicit flow

> The usual OAuth 2.0 grant flow looks like this: ([source](https://developer.okta.com/docs/concepts/oauth-openid/#oauth-2-0))
> 1. Client requests authorization from the resource owner (usually the user).
> 2. If the user gives authorization, the client passes the authorization grant to the authorization server (in this case Okta).
> 3. If the grant is valid, the authorization server returns an access token, possibly alongside a refresh and/or ID token.
> 4. The client now uses that access token to access the resource server.

## open id connect

- a protocol that controls the authentication of an entity and is built on top of OAuth 2.0
- terms:
  - openid provider:  The authorization server that issues the ID token
  - relying party: client application 
  - end user: you
  - clain: a piece of information about the end user
  - id token: issued by openid provider and contains information about the end user in the form of claims.
  
## resources

- [identity and access management](https://en.wikipedia.org/wiki/Identity_management)
- [okta oauth 2.0](https://developer.okta.com/docs/concepts/oauth-openid/#oauth-2-0)
- [okta open id connect](https://developer.okta.com/docs/concepts/oauth-openid/#openid-connect)
