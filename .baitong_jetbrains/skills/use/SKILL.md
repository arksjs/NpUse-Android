---
name: use
description: "Skill for the Use area of NpUse-Android. 10 symbols across 2 files."
---

# Use

10 symbols | 2 files | Cohesion: 100%

## When to Use

- Working with code in `app/`
- Understanding how GreeNpRule, GreeNpTest, data work
- Modifying use-related functionality

## Key Files

| File | Symbols |
|------|---------|
| `app/src/test/java/com/lyentech/use/GreeNpTest.java` | data, getNpArg, setNpBody, isValidStr, encodeURI (+2) |
| `app/src/test/java/com/lyentech/use/GreeNpRule.java` | doGet, parseIsToString, GreeNpRule |

## Entry Points

Start here when exploring this area:

- **`GreeNpRule`** (Class) — `app/src/test/java/com/lyentech/use/GreeNpRule.java:16`
- **`GreeNpTest`** (Class) — `app/src/test/java/com/lyentech/use/GreeNpTest.java:16`
- **`data`** (Method) — `app/src/test/java/com/lyentech/use/GreeNpTest.java:32`
- **`getNpArg`** (Method) — `app/src/test/java/com/lyentech/use/GreeNpTest.java:54`
- **`setNpBody`** (Method) — `app/src/test/java/com/lyentech/use/GreeNpTest.java:74`

## Key Symbols

| Symbol | Type | File | Line |
|--------|------|------|------|
| `GreeNpRule` | Class | `app/src/test/java/com/lyentech/use/GreeNpRule.java` | 16 |
| `GreeNpTest` | Class | `app/src/test/java/com/lyentech/use/GreeNpTest.java` | 16 |
| `data` | Method | `app/src/test/java/com/lyentech/use/GreeNpTest.java` | 32 |
| `getNpArg` | Method | `app/src/test/java/com/lyentech/use/GreeNpTest.java` | 54 |
| `setNpBody` | Method | `app/src/test/java/com/lyentech/use/GreeNpTest.java` | 74 |
| `isValidStr` | Method | `app/src/test/java/com/lyentech/use/GreeNpTest.java` | 99 |
| `encodeURI` | Method | `app/src/test/java/com/lyentech/use/GreeNpTest.java` | 123 |
| `doGet` | Method | `app/src/test/java/com/lyentech/use/GreeNpRule.java` | 35 |
| `parseIsToString` | Method | `app/src/test/java/com/lyentech/use/GreeNpRule.java` | 53 |
| `testGetUrls` | Method | `app/src/test/java/com/lyentech/use/GreeNpTest.java` | 47 |

## How to Explore

1. `context({name: "GreeNpRule"})` — see callers and callees
2. `query({search_query: "use"})` — find related execution flows
3. Read key files listed above for implementation details
4. `explain({target: "<file or symbol>"})` — persisted taint findings (source→sink data flows), when indexed with `--pdg`
