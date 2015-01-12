---
layout: post
title:  "Useful code snippets"
date:   2015-01-11 13:26:20
tags: ["bash", "daily"]
---

## MYSQL

### Backup

{% highlight bash %}
$ mysqldump --opt -u [uname] -p[pass] [dbname] > [backupfile.sql]
{% endhighlight %}

If you want to back up all the databases in the server at one time you should use the --all-databases option. It tells MySQL to dump all the databases it has in storage.

{% highlight bash %}
$ mysqldump -u root -p --all-databases > alldb_backup.sql
{% endhighlight %}

The mysqldump command has also some other useful options:

{% highlight bash %}
--add-drop-table: Tells MySQL to add a DROP TABLE statement before each CREATE TABLE in the dump.

--no-data: Dumps only the database structure, not the contents.

--add-locks: Adds the LOCK TABLES and UNLOCK TABLES statements you can see in the dump file.
{% endhighlight %}

If your mysql database is very big, you might want to compress the output of mysqldump. Just use the mysql backup command below and pipe the output to gzip, then you will get the output as gzip file.

{% highlight bash %}
$ mysqldump -u [uname] -p[pass] [dbname] | gzip -9 > [backupfile.sql.gz]
{% endhighlight %}

If you want to extract the .gz file, use the command below:

{% highlight bash %}
$ gunzip [backupfile.sql.gz]
{% endhighlight %}

### Restore

Create an appropriately named database on the target machine

Load the file using the mysql command:
{% highlight bash %}
$ mysql -u [uname] -p[pass] [db_to_restore] < [backupfile.sql]
{% endhighlight %}

To restore compressed backup files you can do the following:

{% highlight bash %}
$ gunzip < [backupfile.sql.gz] | mysql -u [uname] -p[pass] [dbname]
{% endhighlight %}

If you need to restore a database that already exists, you'll need to use mysqlimport command. The syntax for mysqlimport is as follows:

{% highlight bash %}
$ mysqlimport -u [uname] -p[pass] [dbname] [backupfile.sql]
{% endhighlight %}

From [webcheatsheet.com](http://webcheatsheet.com/sql/mysql_backup_restore.php)