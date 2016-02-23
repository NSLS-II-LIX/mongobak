# MonGoBak


Simple Backup Script for MongoDB

### Setup

Change the variables in the mongo_backup file according to your installation.

 - MONGO_HOST="127.0.0.1"
 - MONGO_PORT="27017"
 - MONGODUMP_PATH="/usr/bin/mongodump"
 - DUMP_PATH="/GPFS/xf16id/mongodump"

### Installation
 - Add execution permission to the `mongo_backup` script
```sh
chmod +x mongo_backup
```

 - Optional: Add the `mongo_backup` script to your path.
 - Optional: Set up a cron job to run `mongo_backup` automatically.

### Todo List
 - [ ]  Test against large database
 - [ ]  Change the comparisson between backups. Maybe md5, sha1 or other.
 - [ ]  Error Handling
    - [ ] Check if the host is reachable
    - [ ] Check if mongodump exists
    - [ ] Check if user running the script has write permission to the DUMP_PATH
    - [ ] Handle execution errors
 - [ ] Log

