# HBV-ReconOps-ADCSRecon-abb3rr3nt

Educational resource documenting Active Directory Certificate Services (AD CS) ESC9 exploitation. Demonstrates how misconfigured certificate templates with the `CT_FLAG_NO_SECURITY_EXTENSION` flag can be leveraged for privilege escalation.

## Contents

| File | Description |
|------|-------------|
| `ADCS_ESC9.md` | Step-by-step guide to create and exploit the ESC9 misconfiguration |
| `Rubeus.exe` | Compiled Kerberos interaction tool for certificate-based authentication |

## Attack Summary

ESC9 exploits certificate templates where the `msPKI-EnrollmentFlag` has `CT_FLAG_NO_SECURITY_EXTENSION` set. An attacker with write privileges over an account with enrollment rights can change the target account's UPN to impersonate a domain administrator, request a certificate, and use it for authentication.

## Dependencies

- Windows Server 2019+ with Certificate Authority role
- Certipy-AD
- Appropriate AD user relationships (see `ADCS_ESC9.md` for details)

## Disclaimer

For authorized security testing and educational purposes only. This misconfiguration guide is intended to help defenders identify and remediate AD CS vulnerabilities.


---

## HoneyBadger Vanguard

**Part of the [HoneyBadger Vanguard (HBV)](https://ihbv.io) purple team ecosystem.**

ADCS misconfiguration recon targeting ESC1/ESC8/ESC9. Pairs with ADCSKiller for automated exploitation. MITRE T1649.

```powershell
$global:Intent = 'Purple'  # Understand offense. Build better defense.
```

| | |
|---|---|
| **Org** | [MoSLoF on GitHub](https://github.com/MoSLoF) |
| **Platform** | HoneyBadger Vanguard 2.0 |
| **Demo Target** | CyberShield 2026 - Little Rock, AR |
| **License** | See LICENSE |

> The difference between a red team tool and a purple team tool is intent.
> -- $global:Intent = 'Purple'
