# Mission 8 Reflection

A host-based firewall protects a server even when the network perimeter is breached because the protection lives on the machine itself. If an attacker gets past the office router or lands on the same network, UFW still inspects every packet and drops anything not explicitly allowed, so one failed defense does not expose everything. This is defense in depth.

Managing open ports is critical because every open port is a running service that someone can probe, and every service may have bugs or weak passwords. Closing everything except SSH on port 22 and the web app on 8080 shrinks the attack surface to only what the client needs, which follows the Principle of Least Privilege and makes the server easier to monitor.

Leaving a database port like 3306 for MySQL open to the public internet is dangerous because automated scanners find it within minutes. Attackers can then try brute-force logins, exploit unpatched database vulnerabilities, or steal, change, or delete customer records. Databases should only be reachable from the application server over a private network, never from the whole world.

Before this mission I assumed a server was only at risk if someone targeted it on purpose. Now I understand that a freshly deployed machine can be scanned and attacked automatically almost immediately, and that one forgotten setting, like skipping the firewall, is enough to leave it exposed. Security is mostly careful, consistent habits.

My GitHub portfolio now has eight completed missions, from Welcome to the Cloud through Cloud Security Engineer. Each folder has its own README, documentation, and screenshots, so the repository reads like a record of my growth from basic cloud concepts to deployment, operations, and security.
