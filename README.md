# FreeIPA IAM Lab

A simulated enterprise identity environment built on FreeIPA, running on Proxmox in my home lab. The goal was to practice the core of Linux-side IAM: centralized identities, group-based access, password policy, and controlling who can log in to which machines.

## What's in it

| Phase | What I built |
|---|---|
| [Phase 1](phase-1/) | FreeIPA server, department groups (Dev, HR, Finance, IT), users assigned by department, a domain password policy, and an HBAC rule limiting SSH to Dev and IT |
| [Phase 2](phase-2/) | An Ubuntu client VM joined to the `mdp.local` domain, login verified with a domain account, and HBAC enforced so only IT and Dev can sign in to it |

## Concepts covered

- **Centralized identity:** one directory for users and groups instead of local accounts on every server
- **Role-based access by group:** access is granted to departments, not individuals
- **Host-Based Access Control (HBAC):** rules that decide which groups can log in to which hosts
- **Password policy:** 12+ characters, 3 character classes, 90-day max age, 5-password history
- **Domain join:** enrolling a Linux client with `ipa-client-install` so it trusts the IPA server for authentication

## Environment

- Proxmox VE host
- FreeIPA server (`ipa.mdp.local`)
- Ubuntu client (`ubuntu-vm.mdp.local`)

Each phase folder has the commands I ran and screenshots of the result.

## Related

[jml-cli](https://github.com/oscar2246/jml-cli): the same lifecycle ideas on the Windows side, provisioning real Active Directory accounts over LDAPS.
