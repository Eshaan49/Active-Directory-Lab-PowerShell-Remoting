# Troubleshooting Notes

## DNS Misconfiguration

Client was unable to resolve domain due to incorrect DNS settings.

## Multiple IP Conflict

Domain Controller had two IP addresses:

* 192.168.12.x (correct)
* 192.168.137.x (incorrect)

Fix:
Removed incorrect IP using PowerShell.

## Authentication Failure

PowerShell Remoting failed due to lack of domain trust and DNS issues.

Resolved after fixing DNS and joining domain.
