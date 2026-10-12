# Mission 9 Reflection

Automation is critical when managing hundreds of cloud servers because doing the same task by hand on each one would take too long and mistakes would be easy to make. A script does the job the same way every time, and a scheduler like cron makes sure it runs even when nobody remembers. This saves time and keeps all the servers consistent.

Automation also has dangers. A script does exactly what it is told, so a destructive typo, like deleting the wrong folder, would run on 1,000 servers at once and the damage would spread very fast. To lower this risk, a script should be tested on one server first, kept in version control, and reviewed before it is scheduled everywhere.

Writing a Bash script was different from making a Docker Compose YAML file in Mission 6. In Bash I wrote the steps in order, like creating a folder and then compressing it. In YAML I described the final result I wanted, and Docker worked out how to get there. Bash felt like giving instructions, and YAML felt like making a plan.

Looking back at my repository from Laboratory 1 to Laboratory 9, my understanding of cloud computing changed a lot. At the start I thought the cloud was just storing files online. Now I know it also means building infrastructure, running containers, monitoring systems, securing servers with a firewall, and automating routine work. Each lab added a new skill on top of the last one.

The role I enjoyed the most was the Cloud Security Engineer in Laboratory 8. I liked seeing the firewall rules change what traffic could reach the server, because the result was clear and I could test it with curl. It showed me how a few simple commands can protect a real service.
