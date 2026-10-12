# Security Audit Report

## The Principle of Least Privilege (PoLP)
PoLP means a user or service gets only the minimum permissions needed to do its job, and nothing more. In cloud accounts this matters because if an account is stolen or misused, the damage is limited to what that account was allowed to do.

## Attack Surface
The attack surface of a virtual machine is the total number of points where an attacker could try to get in. These include open ports, running services, user accounts, and installed software. The fewer of these exposed, the fewer chances an attacker has.

## Default Deny Policy
Default Deny blocks all incoming traffic unless it is explicitly allowed. It is safer than blocking hackers one by one because attackers constantly change IP addresses and methods, so a blocklist is always incomplete, while an allowlist only lets in what is known and needed.
