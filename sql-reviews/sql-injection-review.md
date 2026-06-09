# SQL Injection Vulnerability Review

## Code Example

```sql
SELECT * FROM users
WHERE username = '" + username + "'
```

## Findings

### SQL Injection Risk

Severity: Critical

The query directly incorporates user input into the SQL statement.

An attacker could manipulate the input and execute unauthorized database commands.

## Example Attack

Input:

```text
' OR '1'='1
```

This could alter query behavior and potentially expose sensitive data.

## Recommendations

- Use parameterized queries
- Validate and sanitize input
- Apply least-privilege database permissions
- Perform regular security testing
