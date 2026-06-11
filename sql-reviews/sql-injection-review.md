## SQL Injection Vulnerability Review

### Code Example

```sql
SELECT * FROM users
WHERE username = '" + username + "'
```

### Finding

**SQL Injection Risk**
**Severity:** Critical

User-supplied input is directly concatenated into the SQL statement. Because input is not properly separated from query logic, the application is vulnerable to injection attacks that can alter the intended behavior of the query.

This issue may allow unauthorized data access, authentication bypass, or other unintended database operations depending on how the query is used.

### Example Attack

**Input:**

```text
' OR '1'='1
```

**Resulting Query:**

```sql
SELECT * FROM users
WHERE username = '' OR '1'='1'
```

### Recommendations

* Use parameterized queries or prepared statements.
* Do not construct SQL statements using string concatenation.
* Validate input against expected formats and constraints.
* Apply least-privilege permissions to database accounts.
* Include security testing and code review in the development lifecycle.

### Review Summary

The implementation is vulnerable to SQL injection due to improper handling of user input. This issue should be addressed prior to deployment, as it poses a significant risk to the confidentiality and integrity of application data.
