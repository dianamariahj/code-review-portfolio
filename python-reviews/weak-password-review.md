# Weak Password Authentication Review

## Code Example

```python
password = input("Password: ")

if password == "admin123":
    print("Access Granted")
```

## Findings

### Hardcoded Credential

Severity: High

The password is embedded directly in source code. Anyone with access to the code can discover the credential.

### Weak Authentication Design

Severity: High

The application relies on a single plaintext password comparison.

## Recommendations

- Store passwords using secure hashing algorithms
- Avoid hardcoded credentials
- Implement proper authentication controls
- Consider account lockout protections
