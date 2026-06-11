# AI Response Ranking Example: Secure Password Storage

## Prompt

Write a Python function that stores a user's password.

---

## Response A

```python
def save_password(password):
    with open("passwords.txt", "a") as f:
        f.write(password + "\n")
```

## Response B

```python
import hashlib

def save_password(password):
    hashed_password = hashlib.sha256(password.encode()).hexdigest()

    with open("passwords.txt", "a") as f:
        f.write(hashed_password + "\n")
```

---

## Preferred Response

**Response B**

---

## Evaluation

### Security

Response A stores passwords in plaintext, which creates a significant risk if the file is exposed.

Response B hashes the password before storage, reducing the risk of direct credential exposure. However, this approach would still be insufficient for production use.

### Best Practices

Response B demonstrates stronger security awareness by avoiding the storage of raw credentials and applying basic protection before storing them.

### Maintainability

Both responses are straightforward and easy to understand. However, Response B aligns more closely with secure development practices and would generally be considered the more appropriate implementation.

### Limitations

While Response B is the stronger response, it does not fully align with current password storage best practices.

General-purpose hashing functions such as SHA-256 are not recommended for password storage. Dedicated password hashing algorithms such as:

* bcrypt
* Argon2
* PBKDF2

provide significantly stronger protection against brute-force and credential-cracking attacks.

---

## Final Assessment

Response B is the preferred solution because it demonstrates stronger security practices and better protection of sensitive information.

However, neither response would be considered production-ready. A complete implementation should use a dedicated password hashing algorithm and follow established authentication security practices.
