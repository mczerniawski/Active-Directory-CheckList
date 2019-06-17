# Configuration general checks

### Legend
---
- DC = Domain Controller
- PrivAccounts = Privileged Accounts [Docs.Microsoft.com](https://docs.microsoft.com/en-us/windows-server/identity/ad-ds/plan/security-best-practices/appendix-b--privileged-accounts-and-groups-in-active-directory)
- PrivGroups = Privileged Groups [Docs.Microsoft.com](https://docs.microsoft.com/en-us/windows-server/identity/ad-ds/plan/security-best-practices/appendix-b--privileged-accounts-and-groups-in-active-directory)


---



|Area|Test|Possible approach|Details|
|---|---|---|---|
|Password|Verify Password `Complexity Policy should be [Enabled]`|||
|Password|Verify Password `Length should be [greater than X]`|||
|Password|Verify Password `Treshold should be [greater than X]`|||
|Password|Verify Password `Lockout Duration should be [greater than X minutes]`|||
|Password|Verify Password `Lockout Observation Window should be [greater than X minutes]`|||
|Password|Verify Password `Minimum Age should be [greater than X]`|||
|Password|Verify Password `History Count should be [greater than X]`|||
|Password|Verify Password `Reversible Encryption should be [Disabled]`|||
|Features|Verify Optional Feature `Recycle Bin should be [Enabled]`||If domain 2008 R2|
|Features|Verify Optional Feature `Privileged Access Management Feature should be [Enabled]`||If domain 2016|
|Features|Verify Optional Feature `Bitlocker allows storing recovery key in AD should be [Configured]`|||
|Features|Verify Optional Feature `Bitlocker allows storing recovery key in AD should be [Configured]`|||
|PrivAccounts|Verify Privileged Groups `contains only desired members`|||
|PrivAccounts|Verify Privileged Users permissions `are set to defaults`||[Docs.Microsoft.com](https://docs.microsoft.com/en-us/windows-server/identity/ad-ds/plan/security-best-practices/appendix-b--privileged-accounts-and-groups-in-active-directory)|
