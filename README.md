# smart-DAO


# 🧪 Smart DAO Refactorer

**Modernize legacy SQL-based DAOs into MongoDB-ready document models — powered by GenAI.**

---

## 🧠 What It Does

Smart DAO Refactorer analyzes application-layer code to extract SQL queries, understand their intent, and suggest MongoDB document schema equivalents.

Unlike traditional schema converters, this tool takes a **developer-first approach**: it inspects how SQL is actually used in the codebase (DAOs, service methods), then uses GenAI to propose document structures tailored to real access patterns.

---

## 🔧 Who It's For

- Application developers migrating from SQL to MongoDB
- Architects planning a legacy system modernization
- SREs or platform engineers auditing data access patterns
- Forward Deployed AI engineers needing insight into real-world usage of SQL

---

## 🛠 How It Works

1. **DAO Scanner**  
   Recursively parses source code files (Java, Python, etc.) to find SQL queries embedded in DAOs or repositories.

2. **Query Normalizer**  
   Standardizes and deduplicates SQL queries to isolate unique query patterns.

3. **GenAI-Powered Analyzer**  
   For each unique query, an LLM (e.g., OpenAI) is used to:
   - Describe query intent in plain English
   - Infer data relationships (e.g., joins, 1:N, embedded vs. referenced)
   - Propose an ideal MongoDB document schema

4. **Report Generator**  
   Outputs a human-readable Markdown report summarizing:
   - Original SQL
   - Application-level intent
   - Proposed document schema
   - Suggested refactoring notes

---

## 🧪 Sample Output

```markdown
## DAO: `UserOrderDao.java`

### 🧩 SQL Query
```sql
SELECT o.id, o.amount, u.email FROM orders o JOIN users u ON o.user_id = u.id
