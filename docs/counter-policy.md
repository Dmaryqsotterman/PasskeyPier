# Signature counter policy (sketch)

WebAuthn allows a counter to stay at zero when the authenticator does not implement it,
and a real authenticator may reset it after a factory change. The lab has to draw a line
between those cases and an actual replay.

## Open questions

- Is `0 -> 0` always acceptable, or only for authenticators that declare no counter?
- Does `5 -> 3` fail the ceremony, or warn and continue?
- Where does the rule live for a verifier that consumes our reports?
