# mac-access-lists
# Table of Contents

- [Management](#management)
  - [Management Interfaces](#management-interfaces)
- [Authentication](#authentication)
- [Monitoring](#monitoring)
- [Internal VLAN Allocation Policy](#internal-vlan-allocation-policy)
  - [Internal VLAN Allocation Policy Summary](#internal-vlan-allocation-policy-summary)
- [Interfaces](#interfaces)
- [Routing](#routing)
  - [IP Routing](#ip-routing)
  - [IPv6 Routing](#ipv6-routing)
- [Multicast](#multicast)
- [Filters](#filters)
- [ACL](#acl)
  - [MAC Access-lists](#mac-access-lists)
- [Quality Of Service](#quality-of-service)

# Management

## Management Interfaces

### Management Interfaces Summary

#### IPv4

| Management Interface | description | Type | VRF | IP Address | Gateway |
| -------------------- | ----------- | ---- | --- | ---------- | ------- |
| Management1 | oob_management | oob | MGMT | 10.73.255.122/24 | 10.73.255.2 |

#### IPv6

| Management Interface | description | Type | VRF | IPv6 Address | IPv6 Gateway |
| -------------------- | ----------- | ---- | --- | ------------ | ------------ |
| Management1 | oob_management | oob | MGMT | -  | - |

### Management Interfaces Device Configuration

```eos
!
interface Management1
   description oob_management
   vrf MGMT
   ip address 10.73.255.122/24
```

# Authentication

# Monitoring

# Internal VLAN Allocation Policy

## Internal VLAN Allocation Policy Summary

**Default Allocation Policy**

| Policy Allocation | Range Beginning | Range Ending |
| ------------------| --------------- | ------------ |
| ascending | 1006 | 4094 |

# Interfaces

# Routing

## IP Routing

### IP Routing Summary

| VRF | Routing Enabled |
| --- | --------------- |
| default | false|
### IP Routing Device Configuration

```eos
```
## IPv6 Routing

### IPv6 Routing Summary

| VRF | Routing Enabled |
| --- | --------------- |
| default | false |

# Multicast

# Filters

# ACL

## MAC Access-lists

### MAC Access-lists Summary

#### {'name': 'TEST1', 'entries': [{'sequence': 10, 'action': 'deny any 01:80:c2:00:00:00 00:00:00:00:00:00'}, {'sequence': 5, 'action': 'permit any 01:00:0c:cc:cc:cd 00:00:00:00:00:00'}]}

| Sequence | Action |
| -------- | ------ |

#### {'name': 'TEST2', 'counters_per_entry': True, 'entries': [{'sequence': 5, 'action': 'permit any 01:00:0c:cc:cc:cd 00:00:00:00:00:00'}, {'sequence': 10, 'action': 'deny any 01:80:c2:00:00:00 00:00:00:00:00:00'}]}

| Sequence | Action |
| -------- | ------ |

#### {'name': 'TEST3', 'counters_per_entry': False, 'entries': [{'sequence': 5, 'action': 'permit any 01:00:0c:cc:cc:cd 00:00:00:00:00:00'}, {'sequence': 10, 'action': 'deny any 01:80:c2:00:00:00 00:00:00:00:00:00'}]}

| Sequence | Action |
| -------- | ------ |

#### {'name': 'TEST4', 'entries': [{'action': 'permit any 01:00:0c:cc:cc:cd 00:00:00:00:00:00'}, {'action': 'deny any 01:80:c2:00:00:00 00:00:00:00:00:00'}]}

| Sequence | Action |
| -------- | ------ |

### MAC Extended Access-lists Device Configuration

```eos
!
mac access-list TEST1
   10 deny any 01:80:c2:00:00:00 00:00:00:00:00:00
   5 permit any 01:00:0c:cc:cc:cd 00:00:00:00:00:00
!
mac access-list TEST2
   counters per-entry
   5 permit any 01:00:0c:cc:cc:cd 00:00:00:00:00:00
   10 deny any 01:80:c2:00:00:00 00:00:00:00:00:00
!
mac access-list TEST3
   5 permit any 01:00:0c:cc:cc:cd 00:00:00:00:00:00
   10 deny any 01:80:c2:00:00:00 00:00:00:00:00:00
!
mac access-list TEST4
   permit any 01:00:0c:cc:cc:cd 00:00:00:00:00:00
   deny any 01:80:c2:00:00:00 00:00:00:00:00:00
```

# Quality Of Service
