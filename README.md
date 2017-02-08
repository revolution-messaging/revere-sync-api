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

## Endpoints

#### Constituent Resources

- **[<code>POST</code>constituent/:access_token](https://github.com/revolution-messaging/revere-sync-api/endpoints/constituents/POST_Constituent.md)**

