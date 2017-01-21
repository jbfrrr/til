# `pager`

If you use the mysql command-line client, then `pager` is a must know! 

Quoting [Baron Schwartz](https://www.percona.com/blog/2008/06/23/neat-tricks-for-the-mysql-command-line-pager/), "`pager` tells mysql to pipe the output of your commands through a specific program before displaying it to you."

The most common use case for this is to tell mysql to show you output you can scroll through (hence 'pager'). This is especially useful for big result sets.

```sql
mysql> pager less
mysql> SELECT u.id, u.username, u.display_name, u.email FROM users u;
```

**additional info**: Because `pager` pipes mysql's output through a program / set of commands, you can use it alongside other things besides less! (e.g. grep, tail, ...). For more examples, check the quote link above.