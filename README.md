# Revere Sync API

### Public API V2
***

This describes the resources that make up the official Revere Sync V2. If you have any problems or requests please contact [Sam Robertson](mailto: srobertson@revolutionmessaging.com).

- [Current Version](#current-version)
- [Base Endpoint](#base-endpoint)
- [Endpoints](#constituents)

### Current Version

All requests must be made through the API and include the accept header to get the correct version of the API.

For version 2 of constituent API we pass a V2 in the accept header.

``` 
Accept: application/vnd.sync.v2+json
```

### Schema

All API access is over HTTPS, and accessed from the sync.revmsg.net domain. All data is sent and received as JSON unless otherwise noted. 

Routes with the `Authorization` header required authorization and an active session. Any route without the `Authorization` has open access for the public to be used.

``` 
GET / HTTP/1.1
Host: sync.revmsg.net
Connection: close
Accept: application/vnd.sync.v2+json
Content-Type: application/json
```

### Base Endpoint

**Production**

``` 
https://sync.revmsg.net
```

**Staging**

```
https://revere-sync-v2-stage.herokuapp.com
```

## Functions
Sync runs triggers based on **tags** and the **access token** which is based on a per client basis. Triggers are able to activate various actions and sync data to third-party services such as [Revere Calling](https://revolutionmessaging.com/revere/calling), [Revere Mobile](https://revolutionmessaging.com/revere/mobile), [BSD](https://www.bluestatedigital.com/) and more. Sync is the `ifttt.com` of the progressive movment. Inquire about what is possible with sync by contacting [Revolution Messaging](https://revolutionmessaging.com).

## Endpoints

#### Constituent Resources

- **[<code>POST</code>constituent/:access_token](https://github.com/revolution-messaging/revere-sync-api/blob/master/endpoints/constituents/POST_Constituent.md)**