# `INSERT IGNORE...`

If you wish to do nothing in case an attempt to insert a row containing a duplicate key within a table happens, just use `INSERT IGNORE...`.

For example, in a table `invitational_project` and we have `project_id` as a unique key, we can ignore/by-pass possible errors when someone attempts to insert a row in the said table that contains a `project_id` that's already in a row that's inside the table.

```sql
INSERT IGNORE INTO invitational_project (project_id, status, invited_user_id) VALUES (300, 'Pending', 40);
```

Note that if we did not use `IGNORE` and someone did attempt to insert a row with a duplicate key, then we will encounter an error and the application might crash. Nevertheless, use this functionality wisely as it usually doesn't come up in normal use cases.
