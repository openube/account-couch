# Account Couch
Implement the account interface using a couchdb backend with the couch-profile module

# Installation

```bash
npm install -S account-couch
```

# Usage
The account couch module exports `register` and `login` functions

To register a new account, pass an `email`, `password` and a cradle `db` connection
```javascript
var accountCouch = require('account-couch')
var config = require('nconf').defaults({
  couch: {
    host: 'localhost',
    port: 5984,
    database: 'account_couch_test'
  }    
})
var db = require('cradle-nconf')(config)
var data = {
  email: 'foo@example.com',
  password: 'barPassword',
  db: db
}
accountCouch.register(data, function (err, reply) {
  if (err) {
    inspect(err, 'error registering user account')
    return
  }
  inspect(reply, 'account created correctly'
})
```

# Test
To run the test suite execute

```bash
# install development deps
npm install
# run tests
npm test
```

