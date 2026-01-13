# KQL Security Cheatsheet
**Author:** Mike Berggren (@edgevolt)  
---

## KQL Foundations
The basics of filtering and data manipulation in Log Analytics.

| Operator | Description | Example |
| :--- | :--- | :--- |
| `where` | Filters based on specific criteria | `where Severity == "High"` |
| `project` | Selects only the columns you want to see | `project TimeGenerated, Computer, Account` |
| `extend` | Creates a new column based on logic | `extend UserDomain = tostring(split(User, "@")[1])` |
| `summarize` | Aggregates data (count, avg, max) | `summarize count() by OperationName` |
| `take` / `limit` | Returns a sample of X rows | `take 10` |
| `order by` | Sorts results (default is `desc`) | `order by TimeGenerated desc` |

### Key Functions
* `ago(24h)` / `ago(7d)`: Relative time windows.
* `contains`: Substring search (not case-sensitive).
* `has`: Full-word search (faster than contains).

---

## Advanced Security Logic
Used for building custom Analytics Rules and Workbooks.

### Advanced Operators
| Operator | Description |
| :--- | :--- |
| `join` | Merges two tables into one based on a shared column (e.g., UserID). |
| `union` | Combines rows from multiple tables into one single view. |
| `let` | Defines a variable or a sub-query for cleaner code. |
| `mv-expand` | Expands a multi-value array (JSON) into individual rows. |
| `parse` | Extracts data from a raw string into new columns. |


