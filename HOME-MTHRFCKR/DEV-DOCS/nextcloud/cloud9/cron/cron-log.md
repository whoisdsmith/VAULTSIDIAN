---
tags:: cron
---
Next Exception: Failed to construct console command 'OCA\PermissionsOverwrite\Command\SetCommand': Could not resolve storagesService! Class "storagesService" does not exist in /home2/elnulqmy/public_html/cloud9-ctrlaltback-space/lib/private/Console/Application.php:223
Stack trace:
#0 /home2/elnulqmy/public_html/cloud9-ctrlaltback-space/lib/private/Console/Application.php(128): OC\Console\Application->loadCommandsFromInfoXml(Array)
#1 /home2/elnulqmy/public_html/cloud9-ctrlaltback-space/console.php(98): OC\Console\Application->loadCommands(Object(Symfony\Component\Console\Input\ArgvInput), Object(Symfony\Component\Console\Output\ConsoleOutput))
#2 /home2/elnulqmy/public_html/cloud9-ctrlaltback-space/occ(11): require_once('/home2/elnulqmy...')