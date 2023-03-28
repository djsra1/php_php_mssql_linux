## Запуск:
-  docker-compose up -d

## Стек:
-  PHP Version 8.1.0
-  NGINX Version 1.21.4
-  MSSQL Version 2019

## add to yml for sqlserver error fixing  https://github.com/microsoft/mssql-docker/issues/542
   user=root 

## database restore only in sqlmode, not in GUI
RESTORE DATABASE [stego_as] FROM  DISK = N'/var/opt/mssql/data/stego_as.bak' WITH  FILE = 1,  MOVE N'stego_as' TO N'/var/opt/mssql/data/stego_as.mdf',  MOVE N'stego_as_log' TO N'/var/opt/mssql/data/stego_as_0.ldf',  NOUNLOAD,  REPLACE,  STATS = 5

## it migth /db/stego_as.mdf and /db/stego_as_log.ldf must be created manually 
