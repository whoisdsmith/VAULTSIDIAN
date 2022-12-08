---
tags:: logs
---
[12-Jul-2022 18:42:35 America/Boise] PHP Fatal error:  Uncaught Doctrine\DBAL\Exception: Failed to connect to the database: An exception occurred in the driver: SQLSTATE[HY000] [1040] Too many connections in /home2/elnulqmy/public_html/cloud9-ctrlaltback-space/lib/private/DB/Connection.php:139
Stack trace:
#0 /home2/elnulqmy/public_html/cloud9-ctrlaltback-space/3rdparty/doctrine/dbal/src/Connection.php(1519): OC\DB\Connection->connect()
#1 /home2/elnulqmy/public_html/cloud9-ctrlaltback-space/3rdparty/doctrine/dbal/src/Connection.php(1041): Doctrine\DBAL\Connection->getWrappedConnection()
#2 /home2/elnulqmy/public_html/cloud9-ctrlaltback-space/lib/private/DB/Connection.php(261): Doctrine\DBAL\Connection->executeQuery('SELECT * FROM `...', Array, Array, NULL)
#3 /home2/elnulqmy/public_html/cloud9-ctrlaltback-space/3rdparty/doctrine/dbal/src/Query/QueryBuilder.php(345): OC\DB\Connection->executeQuery('SELECT * FROM `...', Array, Array)
#4 /home2/elnulqmy/public_html/cloud9-ctrlaltback-space/lib/private/DB/QueryBuilder/QueryBuilder.php(281): Doctrine\DBAL\Query\Query in /home2/elnulqmy/public_html/cloud9-ctrlaltback-space/lib/private/DB/Connection.php on line 139