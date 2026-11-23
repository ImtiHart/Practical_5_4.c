# Password Strength Validator (C)

A C program that checks whether a user-entered password meets three criteria:
**minimum 8 characters**, **at least one uppercase letter**, and **at least one number**.
Each character class is verified with `strstr()` inside a loop, as specified.

## 🎯 What It Demonstrates

- **`strstr()` as a membership test** — for each candidate character (`A`–`Z`, `0`–`9`)
  a one-character needle is searched for in the password; a non-`NULL` result means
  the class is present.
- **Early-exit loops** — once a match is found, `break` stops scanning, so the check
  is cheap on average.
- **Bounded input** — `scanf("%49s")` prevents buffer overflow on long passwords.
- **Actionable feedback** — the program reports *which* rule failed, not just "invalid".

## 📋 Validation Rules

| Rule        | Requirement                    |
|-------------|--------------------------------|
| Length      | ≥ 8 characters                 |
| Uppercase   | ≥ 1 letter in `A`–`Z`          |
| Digit       | ≥ 1 character in `0`–`9`       |

## 🚀 How to Run

```bash
gcc main.c -o password_check
./password_check
