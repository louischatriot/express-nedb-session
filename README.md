express-nedb-session
====================

**IMPORTANT: this library is not maintained anymore, please don't submit anymore pull requests except for bugfixes**

NeDB-backed session store for the Express 4 session middleware.

## Install and test
```javascript
npm install connect-nedb-session
npm test
```

## How to use
```javascript
var express = require('express')
  , session = require('express-session')
  , NedbStore = require('connect-nedb-session')(session);

// Use with the session middleware (replace express with connect if you use Connect)
server.use(session({ secret: 'yoursecret'
                   , resave: false
                   , saveUninitialized: false
                   , cookie: { path: '/'
                             , httpOnly: true
                             , maxAge: 365 * 24 * 3600 * 1000   // One year for example
                             }
                   , store: new NedbStore({ filename: 'path_to_nedb_persistence_file' })
                   }));
```

## License
MIT
