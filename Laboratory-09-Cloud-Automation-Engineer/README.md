# Laboratory 09 - Cloud Automation Engineer

## Mission Overview
I automated a nightly backup for CloudNova Technologies by writing a Bash script that compresses the `app-data` folder, making it executable with chmod, and scheduling it with cron to run every night at 2:00 AM.

## Objectives
- Understand Bash script syntax, including variables and basic commands
- Use nano to write and save scripts
- Change file permissions with chmod
- Understand crontab scheduling syntax
- Document automation in Markdown

## Commands Executed
mkdir app-data
echo “This is critical client data.” > app-data/data.txt
nano backup.sh
./backup.sh
chmod +x backup.sh
./backup.sh
ls -l backups/
crontab -l
env EDITOR=nano crontab -e

## Skills Learned
- Writing a Bash script with variables
- Setting executable permissions
- Creating compressed backups with tar
- Scheduling tasks with cron
- Documenting work in Markdown and using Git/GitHub
