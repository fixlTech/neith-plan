# Security architecture

Status: Threat-model outline

## Controls to specify
Identity, MFA/SSO, session lifecycle, scoped authorization, tenant isolation, secure uploads, malware and content validation, encrypted transport/storage, secrets handling, rate limits, webhook verification, service identities, and audit integrity.

## Sensitive flows
External sharing; third-party delivery; template variables; automation credentials; approval overrides; admin impersonation; asset deletion; export of restricted media.

## Assurance work
Threat model per workflow; abuse cases; permission tests; dependency and secret scanning; incident response; retention/deletion review; penetration test before enterprise launch. Map contractual or regulatory commitments only once target markets and customer requirements are known.
