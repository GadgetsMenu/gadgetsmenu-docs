---
title: Data Migration (From SQLite to MySQL)
description: You can migrate SQLite local data to MySQL database without losing player's data.
group: setup
keywords: data migration, database migration, sqlite to mysql
topics:
 - data migration
 - database migration
 - sqlite to mysql
---

Migrate data from SQLite to current connected MySQL database.

## Requirements
* Plugin is connected to a MySQL database.
* Stable internet connection between MySQL database and MC server.
* Do not stop the server while the migration is running.
* Make sure you made a backup before proceed with the migration.
* A MySQL database without any GadgetsMenu data is recommended but not a must.

## Steps
1. Ensure your server is not running under high load. (No player in the server is the best)
2. Execute command `/gmenu migrate confirm` from in-game command panel or console.
3. Wait until the migration is done. (A success message will be shown)

## Sample Output Message
![Data migration](/assets/gadgetsmenu-docs/images/others/data-migration-migrate-data-from-sqlite-to-mysql.png "[Wrapper] Data migration")
