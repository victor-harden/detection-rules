# SSH Brute Force Detection (Basic)

## Indicator

Multiple failed authentication attempts from the same source in a short time window.

## Example Log Pattern

```
Failed password for .* from <IP>
```

## Simple detection idea

- Count failed attempts per source IP in 5 minutes
- Threshold: > 10 failures
- Action: alert + optional Fail2Ban

## Notes

This is intentionally simple. Production rules should include allowlists, geolocation context and correlation with successful logins.
