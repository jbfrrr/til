# Replacing Strings

Need to update some contaminated / incorrect content that's saved on your MySQL DB?

MySQL's `REPLACE` can be of help!

General usage is `REPLACE(<haystack>, <needle>, <replacement>)`

Here's a pretty decent usage scenario. The code below fixes broken links on an article wherein some links have 'http://https//' instead of 'https://', 'http://http//', instead of 'http://' and other similar mess ups.

What's cool about this example is that `REPLACE` was repeatedly used, becoming the content of the succeeding `REPLACE` call

```sql
UPDATE articles
SET content = REPLACE(
    REPLACE(
        REPLACE(
            REPLACE(
                content,
                'http://https//',
                'https://'
            ),
            'http://http//',
            'http://'
        ),
        'http://https://',
        'https://'
    ),
    'http://http://',
    'http://'
)
WHERE id = 3054;
```

Observe that you can affect more records by adjusting the `WHERE` clause.

Also, note that things could get a bit tricky when you're trying to reduce / remove escaped characters, e.g. (`\`), from the content as you might need to do escaping itself on the `<needle>` and/or the `<replacement>` so that MySQL interprets your query properly.

**pro tip**: Before you permanently replace content via `UPDATE...REPLACE`, you can first see the effects of your `REPLACE` by doing a `SELECT`
```sql
SELECT REPLACE(haystack, needle, replacement) FROM <table> WHERE id = <id>
```
