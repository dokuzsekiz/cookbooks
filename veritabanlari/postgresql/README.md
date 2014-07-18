# Postgresql
## Installation

### With Brew on Mac

```bash
$ brew update
$ brew doctor
$ brew install postgresql
$ initdb /usr/local/var/postgres -E utf8
$ gem install lunchy
$ mkdir -p ~/Library/LaunchAgents $ cp /usr/local/Cellar/postgresql/9.X.X/homebrew.mxcl.postgresql.plist ~/Library/LaunchAgents/
$ lunchy start postgres
$ lunchy stop postgres
```

### Run with lunchy gem on Mac

```bash
gem install lunchy
lunchy start postgres
lunchy stop postgres
```

## User Roles

### Super and Nosuperuser

```sql
ALTER USER myuser WITH SUPERUSER;
ALTER USER myuser WITH NOSUPERUSER;
```

## Backup Restore

### Dump remote database to local machine

You can use `pg_dump` command to dump remote database.

```bash
$ pg_dump -h xxx.xxx.xxx.xxx -U postgresql_username -p xxxx databasename > localfile.sql
```

You can restore the dump with this command.

```bash
$ psql -U postgresql_username -d databasename -f localfile.sql
```

## Extensions

### HStore

Enable HStore

```bash
sudo apt-get install postgresql-contrib
```

```sql
psql -d yourproject_production -U yourdbuser -W
CREATE EXTENSION hstore;
```

## PSQL

* `$ psql` - enter
* `psql=> \q` - quit
* `psql=> \h` - help
* `psql=> SELECT version();` - show version
* `psql -U username -d myDataBase -a -f myInsertFile` - run sql file
* `list` - list all databases in cluster
* `\d <table_name>` - list all columns for a specified table

## Log

* http://www.postgresql.org/docs/9.1/static/runtime-config-logging.html

`log_min_messages=debug5`

## Diagnostic Commands

* Runtime queries

```sql
select datname,usename,application_name,client_addr,state,query from pg_stat_activity where state <> 'idle';
```

* Slowest queries

```sql
SELECT query, calls, total_time, rows, 100.0 * shared_blks_hit /
               nullif(shared_blks_hit + shared_blks_read, 0) AS hit_percent
          FROM pg_stat_statements ORDER BY total_time DESC LIMIT 5;
```

* Most runned queries

```sql
SELECT query, calls, total_time, rows, 100.0 * shared_blks_hit nullif(shared_blks_hit + shared_blks_read, 0) AS hit_percent FROM pg_stat_statements ORDER BY calls DESC LIMIT 5;
```
