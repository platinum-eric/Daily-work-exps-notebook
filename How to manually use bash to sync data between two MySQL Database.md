# How to manually use bash to sync data between two MySQL Database

## Step 1. Export data from one of databases

#### use mysqldump command to export database
- Command Usage: mysqldump [OPTIONS] [DATABASE] [TABLES]
- Export a Database: mysqldump -u [username] - p [schema] > [file name].sql
- Export a Table: mysqldump -u [username] - p [schema] [table]> [file name].sql
- Reference online page: https://segmentfault.com/a/1190000011147118

## Step 2. Sync the export file to another server

#### use rsync command to sync data to another server
- Usage (Push to):    rsync -avP [user]@[host]:[file or folder path] [target path]
- Usage (Pull from):  rsync -avP [target path] [user]@[host]:[file or folder path] 
- Reference online page for no use password method sync: https://blog.csdn.net/fuguoq1984/article/details/32331941

## Step 3. Import to target database
- Enter into MySQL:  >mysql -u root -p
- If target database is not existed, create one:  >create database [schema name]
- Change to use target schema: >use [schema]
- Import data by target file: >source [target file path]


----
### In usually, it’s going to be successful and you could to view the data now
