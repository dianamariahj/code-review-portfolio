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

---

## Response B

```python
import hashlib

def save_password(password):
    hashed_password = hashlib.sha256(password.encode()).hexdigest()

    with open("passwords.txt", "a") as f:
        f.write(hashed_password + "\n")
```

---

## Ranking

Winner: Response B

## Evaluation

### Security

Response A stores passwords in plaintext, creating a significant security risk if the file is exposed.

Response B hashes the password before storage, reducing the risk of credential exposure.

### Best Practices

Response B demonstrates a better understanding of secure credential handling and security-conscious development.

### Maintainability

Both responses are readable, but Response B provides a more professional and security-focused implementation.

### Limitations

While Response B is superior, modern applications should use dedicated password hashing algorithms such as bcrypt, Argon2, or PBKDF2 rather than general-purpose hashing functions.

## Final Assessment

Response B is the preferred solution because it demonstrates stronger security practices, better protection of sensitive information, and greater alignment with real-world software development standards.
