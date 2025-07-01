---
tags:
  - nodejs
status: 🟩
---

2025-06-17 17:47

Related topics: 

# What is SemVer?

**SemVer**, or **Semantic Versioning**, is a versioning system for software that uses the format:

```
MAJOR.MINOR.PATCH
```

For example:

```
1.4.2
```

![[semantic-versioning.png]]

Most of the packages use Semantic Versioning System or SemVer. 

> [!NOTE] Title
> Some packages like typescript, react-native don't follow it.

---

## Symbols in dependency versioning


| Symbols   | Meaning                          | Example         | Resolves To            |
| --------- | -------------------------------- | --------------- | ---------------------- |
| ^ (Caret) | Minor and patch updates allowed  | ^4.17.1         | 4.18.0 not 5.0.0       |
| ~ (Tilde) | Only patch updates allowed       | ~4.17.1         | 4.17.2 not 4.18.0      |
| Exact     | Fixed version                    | 4.17.1          | 4.17.1 only            |
| >         | Grater Version                   | >4.17.1         | 4.18.0                 |
| <         | Less than                        | <4.17.1         | 4.16.1                 |
| >=        | Grater than or equal to          | <=4.17.1        | 4.17.1                 |
| <=        | less than or equal to            | >=4.17.1        | 4.17.1                 |
| *         | Any version                      | *               |                        |
| Range     | Acceptable range                 | 4.16.0 - 4.17.1 | 4.16.5                 |
| x         | Wildcard for minor patch version | 4.x             | 4.16.1, 4.17.1, 4.16.1 |

---


## References

