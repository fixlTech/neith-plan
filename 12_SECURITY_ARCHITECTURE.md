# Neith — Security Architecture

**Status:** Threat-model and control plan; compliance claims unapproved

## Trust boundaries
Browser/mobile clients are untrusted; API enforces identity, tenant scope, and action policy; workers run with least privilege; external triggers and publishing destinations are untrusted integration boundaries; uploaded media and templates may be hostile input. Cross-tenant isolation is mandatory in storage, caches, search, events, and logs.

## Required controls
MFA and session lifecycle; SSO/SCIM if enterprise scope selects them; short-lived scoped credentials; centralized authorization at every mutation; secret rotation; encrypted transport and storage; validated and scanned uploads; isolated media processing; content security policy and input/output encoding; rate limits; signed webhooks and replay protection; protected audit evidence; backups and incident response.

## High-risk scenarios
An attacker guesses another tenant's document ID; a guest retains an old URL; a malicious file exploits transcoding; an automation connector publishes to an unintended destination; a reviewer approves their own work despite policy; template variable injection exfiltrates data; admin override evades audit. For each, document assets, entry point, likelihood/impact, prevention, detection, and recovery.

## Assurance and ownership
Security lead approves threat model and policy tests. CI checks dependencies, secrets, and static analysis; API tests exercise tenant boundaries and role combinations; review third-party processors and data flow; perform penetration and recovery exercises before enterprise release. Choose applicable legal/contractual requirements based on target markets and customer commitments, not generic certification claims.
