# Troubleshooting

## Issue: Access Denied
- Cause: Wrong credentials
- Fix: Use domain credentials (lab\Administrator)

## Issue: Kerberos Error
- Cause: Time mismatch
- Fix: Sync system time

## Issue: WinRM Not Working
- Fix:
Enable-PSRemoting -Force

## Issue: DNS Not Resolving
- Fix:
Set-DnsClientServerAddress -InterfaceAlias "Ethernet0" -ServerAddresses 192.168.12.10
