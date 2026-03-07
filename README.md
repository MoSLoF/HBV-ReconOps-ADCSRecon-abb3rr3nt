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
