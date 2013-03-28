plaid-node
==============

<!--[![Build Status](https://travis-ci.org/plaid/plaid-node.png)](https://travis-ci.org/plaid/plaid-node) -->


plaid-node is a node.js client for [Plaid.io](https://plaid.io)

## Documentation

Documentation is available at [https://plaid.io/docs](https://plaid.io/docs).

## Install
    npm install plaid

## Examples
```javascript
var plaid = require('plaid')({client_id: '123456', secret: '7891011'});

plaid.connect({username: 'demo', password: 'test'}, 'amex', 'w@plaid.io', function(error, response, mfa){
	
	//Non MFA
	console.log(response)

	//MFA
	if(mfa){
		response.step({token: '1234'}, function(err, response){
			//response is accounts and transactions object
		})
	}
});
```

## License

```
WWWWWW||WWWWWW
 W W W||W W W
      ||
    ( OO )__________
     /  |           \
    /o o|    MIT     \
    \___/||_||__||_|| *
         || ||  || ||
        _||_|| _||_||
       (__|__|(__|__|
```

(The MIT License)

Copyright (c) 2013 Plaid Technologies <william@plaid.io>

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the 'Software'), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED 'AS IS', WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.