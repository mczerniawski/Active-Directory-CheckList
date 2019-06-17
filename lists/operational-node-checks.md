# Operational node checks

### Legend
---
- DC = Domain Controller
- FSMO = Flexible Single-Master Operation
- PDC = Domain Controller with PDC Emulator FSMO role
- `{Services}` = services required by a DC to function properly - `'Active Directory Domain Services','Active Directory Web Services''DFS Replication','DNS Client', 'DNS server','Group Policy Client','Intersite Messaging','Kerberos Key Distribution Center','NetLogon','Windows Time','Workstation'`


---

These checks should be performed against EACH DC!

|Area|Test|Possible approach|Details|
|---|---|---|---|
|Connectivity|Verify `DC is [recheable]`|ICMP echo request (ping)||
|Services|Verify all `{Services} are [running]`|||
|Services|Verify all `{Services} are set to [automatic startup]`|||
|DNS resolve|Verify `DNS on DC [resolves DNS]`|Resolve current/any host name i.e. Resolve-DNSName||
|PowerShell|Verify DC `responds to PowerShell queries`|Run any Get-AD* cmdlet agains a DC||
|Replication|Verify DC `has no replication failures`|`Get-ADReplicationFailure`||
|Backup|Verify `last backup time should be [less than X days]`|
|Time|Verify `current time difference between Host and DC is [less than X minutes]`|||
|Time|Verify `PDC should [sync time to external source]`|||
|Time|Verify `Non-PDC should [sync time to PDC emulator]`|||
|Time|Verify `Virtualized DCs should [sync to hypervisor during boot time only]`|||
|Host|Verify `OS partition Free space is [at least X %]`|||
|Host|Verify `SYSVOL partition Free space is [at least X %]`|||

