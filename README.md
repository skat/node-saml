Create SAML assertions.

NOTE: currently supports SAML 1.1 tokens

[![Build Status](https://travis-ci.org/auth0/node-saml.png)](https://travis-ci.org/auth0/node-saml)

### Usage
For SKAT SAML 1.1 configuration

```js
var saml11 = require('saml').Saml11;

var options = {
  cert: fs.readFileSync(__dirname + '/test-auth0.pem'),
  key: fs.readFileSync(__dirname + '/test-auth0.key'),
  issuer: 'urn:issuer',
  nameQualifier: 'skat',
  lifetimeInSeconds: 600,
  offset: 60,
  audiences: 'urn:myapp',
  subjectConfirmationMethod: 'holder-of-key',
  attributes: {
    'urn:bea:security:saml:groups': 'AUTH_LEVEL_7'
  },
  nameIdentifier: 'skatGuid=DemoSystemUser,ou=skatSystem,ou=internal,ou=entities,dc=skat,dc=dk',
  sessionIndex: '_faed468a-15a0-4668-aed6-3d9c478cc8fa'
};

var signedAssertion = saml11.create(options);
```

Everything except the cert and key is optional.

## Issue Reporting

If you have found a bug or if you have a feature request, please report them at this repository issues section. Please do not report security vulnerabilities on the public GitHub issue tracker. The [Responsible Disclosure Program](https://auth0.com/whitehat) details the procedure for disclosing security issues.

## Author

[Auth0](auth0.com)

## License

This project is licensed under the MIT license. See the [LICENSE](LICENSE) file for more info.
