# Jusibe Node.js Client
> JavaScript client for Jusibe.com SMS API service

[![npm package](https://nodei.co/npm/jusibe.png?downloads=true&downloadRank=true&stars=true)](https://nodei.co/npm/jusibe/)

[![Build Status](https://travis-ci.org/azemoh/jusibe.svg?branch=master)](https://travis-ci.org/azemoh/jusibe)

## Installation

```bash
npm install jusibe
```

## Usage

```javascript
var Jusibe = require('jusibe');

var publicKey = process.env.JUSIBE_PUBLIC_KEY;
var accessToken = process.env.JUSIBE_ACCESS_TOKEN;

var jusibe = new Jusibe(publicKey, accessToken);
```

### Check SMS Credits
```javascript
jusibe.getCredits(function (err, res) {
  if (res.statusCode === 200)
    console.log(res.body);
  else
    console.log(err);
});
```

### Send SMS
```javascript
var payload = {
  to: '080XXXXXXXX',
  from: 'Jusibe Joe',
  message: 'Hello From the other side 😎\nI must have called a thousand times.'
};

jusibe.sendSMS(payload, function (err, res) {
  if (res.statusCode === 200)
    console.log(res.body);
  else
    console.log(err);
});

```

### Check SMS status
```javascript
jusibe.deliveryStatus('eq16v6vd26', function (err, res) {
  if (res.statusCode === 200)
    console.log(res.body);
  else
    console.log(err);
});
```

## License

Available as open source under the terms of the [MIT License](http://opensource.org/licenses/MIT).
