# Security

## Reporting a vulnerability

Please report security issues privately through GitHub's
[security advisory](https://github.com/Dmaryqsotterman/PasskeyPier/security/advisories/new)
form rather than in a public issue.

Include the scenario you ran, the inputs, and what you
expected the ceremony to do. You should get an answer within a few days.

## Scope

PasskeyPier runs virtual WebAuthn ceremonies over untrusted inputs. Anything that
turns a malformed credential, challenge or origin into a wrong verdict, a crash
or an out-of-memory is in scope.
