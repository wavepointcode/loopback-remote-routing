# loopback-remote-routing

Easily disable remote methods.

##Installation

```bash
npm install loopback-remote-routing --save
```

##How to use

```js

// common/models/color.js
var RemoteRouting = require('loopback-remote-routing');

module.exports = function(Color) {
  // use only to expose specified remote methods
  RemoteRouting(Color, {only: [
    '@find',
    '@findById',
    'updateAttributes'
  ]})
  
  //use except to expose all remote methods except specified ones
  RemoteRouting(Color, {except: [
    '@create',
    '@find'
  ]}
  
  //disable all remote methods omitting options
  
  RemoteRouting(Color)
}
```
you can only use options.only or options.except, do not mix using them.
