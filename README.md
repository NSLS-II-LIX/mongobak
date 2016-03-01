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
 - [X]  Test against large database
   - HXN Backup (~40G) takes around 12-15 minutes being 11 minutes for the mongodump 
 - [X] Change the comparisson between backups. Maybe md5, sha1 or other.
   - The diff command was taking 1:39 minutes for a ~40G backup.
   - Changed to compare file by file with cmp command and stop on the first difference.
   - New strategy with cmp is faster when files are different but will take ~2 minutes two compare to similar ~40G backups.
 - [ ]  Error Handling
    - [ ] Check if the host is reachable
    - [ ] Check if mongodump exists
    - [ ] Check if user running the script has write permission to the DUMP_PATH
    - [ ] Handle execution errors
 - [ ] Log

