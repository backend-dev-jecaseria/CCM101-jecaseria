# Final Reflection: From Mission 1 to Mission 10

**Course:** CCM101 Cloud Computing
**Name:** Jehiel Caseria
**Project:** Laboratory 10, Enterprise Cloud Architect (CloudNova Ghost Stack)

## My Journey

In Mission 1, I started as a Junior Trainee learning basic Linux commands and what "the cloud" really means. [Add one thing you remember from Lab 1.]

In Missions 2 and 3, I built cloud infrastructure and explored more than one cloud platform. This taught me that the ideas (compute, storage, networking) stay the same even when the provider changes.

In Missions 4 and 5, I worked with cloud-native tools and cloud data. This is where I first used containers and learned that data has to live somewhere safe. [Add your own detail.]

In Missions 6 and 7, I moved to deployment and operations. I learned to deploy an app, watch it, and fix it when it breaks.

In Mission 8, I learned security: closing ports, using a firewall, and limiting who can reach what.

In Mission 9, I automated tasks with Bash scripts and scheduled them. This was the first time the server did work without me.

In Mission 10, I put everything together with no step-by-step guide.

## What I Built

I built a private Ghost website with a MySQL 8.0 database. Both run in Docker containers on Ubuntu Server inside VirtualBox. The pieces map to the earlier missions:

- **Infrastructure (Missions 1 to 3):** VirtualBox VM, Ubuntu Server, NAT with port forwarding (8080 to 80, 2222 to 22).
- **Deployment (Missions 4 to 7):** `docker-compose.yml` with two linked containers, a healthcheck, and persistent volumes (`db_data`, `ghost_content`).
- **Security (Mission 8):** UFW with default deny, only ports 22 and 80 open, MySQL not published, and a `.env` file with mode 600.
- **Automation (Mission 9):** `automation-script.sh` backs up the database every day at 2:00 AM with cron and removes backups older than 7 days.

## Problems I Solved

- The VM had no IPv4 address at first. I fixed it by using NAT and setting `dhcp4: true` in netplan.
- The VM froze with `soft lockup` messages when it had too little RAM. I changed it to 4096 MB RAM and 2 CPUs.
- [Add any other problem you faced, such as a UFW or SSH issue.]

## What I Learned

1. **Backups must be tested.** During the restore test, a backup made after a post was deleted does not bring that post back. A backup that is empty is useless. I learned to check the file size and run a restore test.
2. **Security comes in layers.** The firewall, the private Docker network, and the protected `.env` file all work together.
3. **Infrastructure as Code is repeatable.** One compose file can rebuild the whole stack.
4. **Docs are part of the system.** The operational manual lets another person run what I built.

## What I Would Improve

- Copy backups off the VM to another machine or cloud storage.
- Back up the `ghost_content` volume too.
- Add HTTPS with a reverse proxy.
- Add monitoring and alerts.
- Use SSH keys and turn off password login.

## Closing

I started this course typing my first Linux commands. I finished by designing, securing, automating, and defending a full stack on my own. The biggest change for me is that I no longer follow steps blindly. I now understand why each step is there. [Add one personal sentence.]

*AI disclosure: I used an AI assistant to help organize this reflection. The experiences and lessons are from my own lab work.*
