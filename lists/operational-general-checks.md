# Operational general checks

### Legend
---
- DC = Domain Controller
- FSMO = Flexible Single-Master Operation
- RODC = Read Only Domain Controller
- `{DNS entries}` = 
    - _ldap in `{SiteName}._sites.dc._msdcs.contoso.com`
    - _kerberos `{SiteName}._sites.dc._msdcs.contoso.com`
    - _ldap in `_tcp.dc._msdcs.contoso.com`
    - _kerberos in `_tcp.dc._msdcs.contoso.com`
    - _ldap in `{domain-guid].domains._msdcs.contoso.com`
    - record type A in `gc._msdcs.contoso.com`
    - _ldap in `_tcp.{SiteName}._sites.gc._msdcs.contoso.com`
    - _ldap in `_tcp.gc._msdcs.contoso.com`
    - _ldap for PDC in `_tcp.pdc._msdcs.contoso.com`

---

|Area|Test|Possible approach|Details|
|---|---|---|---|
|Connectivity|Verify each `DC in replication site can [reach other replication members]`|||
|DNS|Verify `{DNS entries} in _msdcs zone [point to all DCs]`|||
|DNS|Verify `DNS Reverse Lookup zones are [configured for all site subnets]`|||
|DNS|Verify `DNS Scavenging is set to [X days]`|||
|DHCP|Verify at least `one DHCP is [authorized in domain]`||If other DHCP than domain integrated is used this should be skipped|
|Sites|Verify each `site has at least [one subnet configured]`|||
|FMSO|Verify each `FSMO holder is [reachable]`|||
|RODC|Verify each `RODC is [reachable]`||If applicable|
