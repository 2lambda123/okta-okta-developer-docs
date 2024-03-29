Using the [NJWT library](https://github.com/jwtk/njwt):

```javascript
const njwt = require('njwt');

const clientSecret = "${clientSecret}"; // Or load from configuration
const clientId = "${clientId}"; // Or load from configuration
const now = Math.floor( new Date().getTime() / 1000 ); // seconds since epoch
const plus5Minutes = new Date( ( now + (5*60) ) * 1000); // Date object

const claims = {
  aud: "https://${yourOktaDomain}/oauth2/default/v1/token", // audience
};

const jwt = njwt.create(claims, clientSecret)
  .setIssuedAt(now)
  .setExpiration(plus5Minutes)
  .setIssuer(clientId)
  .setSubject(clientId)
  .compact();
```
