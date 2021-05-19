## How-To

1. Run `sqlfluff lint .` in the top-level directory of this project
2. Notice that there is an error message for `test_model_broken.sql` which calls `week_start_date()` via another macro  but not when `week_start_date()` is called directly in `test_model_working.sql`

```sql
(base) michael@Michaels-Macbook-Air sqlfluff_nested_macro_example % sqlfluff lint .
== [test_model_broken.sql] FAIL
L:   0 | P:   0 |  TMP | Unrecoverable failure in Jinja templating:
                       | 'week_start_date' is undefined. Have you configured your
                       | variables?
                       | https://docs.sqlfluff.com/en/latest/configuration.html
```
