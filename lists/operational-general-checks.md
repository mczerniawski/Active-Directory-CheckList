# Operational general checks

### Legend
---
- DC = Domain Controller
- FSMO = Flexible Single-Master Operation
- RODC = Read Only Domain Controller

---

|Area|Test|Possible approach|Details|
|---|---|---|---|
|Connectivity|Verify each `DC in replication site can [reach other replication members]`|||
|DHCP|Verify at least `one DHCP is [authorized in domain]`|`Get-ADObject -filter "objectclass -eq 'dhcpclass' -AND Name -ne 'dhcproot'"`|If other DHCP than domain integrated is used this should be skipped|
|Sites|Verify each `site have at least [one subnet configured]`|`[System.DirectoryServices.ActiveDirectory.Forest]::GetCurrentForest()`||
|FMSO|Verify each `FSMO holder is [recheable]`|||
|RODC|Verify each `RODC is [recheable]`|||