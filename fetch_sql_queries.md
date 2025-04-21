
## 📌 Closed-Ended Question 1: Top 5 Brands by Receipts Scanned (21+ Users)

### 🔍 SQL Query
```sql
SELECT 
    p.brand,
    COUNT(DISTINCT t.receipt_id) AS receipt_count
FROM Transactions t
JOIN Users u ON t.user_id = u.id
JOIN Products p ON t.barcode = p.barcode
WHERE 
    u.birth_date IS NOT NULL AND
    DATE('now') >= DATE(u.birth_date, '+21 years')
GROUP BY p.brand
ORDER BY receipt_count DESC
LIMIT 5;
```

### 📊 Result
```
    BRAND             receipt_count
    NERDS CANDY       3
    DOVE              3
    None              3
    TRIDENT           2
    SOUR PATCH KIDS   2
```

---

## 📌 Closed-Ended Question 2: Top 5 Brands by Sales (Accounts ≥ 6 Months)

### 🔍 SQL Query
```sql
SELECT 
    p.brand,
    SUM(t.FINAL_SALE) AS total_sales
FROM Transactions t
JOIN Users u ON t.user_id = u.id
JOIN Products p ON t.barcode = p.barcode
WHERE 
    u.created_date <= DATE('now', '-6 months') AND
    t.FINAL_SALE IS NOT NULL
GROUP BY p.brand
ORDER BY total_sales DESC
LIMIT 5;
```

### 📊 Result
```
    BRAND         total_sales
    CVS           72.00
    TRIDENT       46.72
    DOVE          42.88
    COORS LIGHT   34.96
    None          16.65
```

---

## 📌 Open-Ended Question: Who Are Fetch’s Power Users?

### 🔍 SQL Query
```sql
SELECT 
    u.id AS user_id,
    COUNT(DISTINCT t.receipt_id) AS receipts_scanned,
    SUM(t.FINAL_SALE) AS total_spent
FROM Transactions t
JOIN Users u ON t.user_id = u.id
WHERE t.FINAL_SALE IS NOT NULL
GROUP BY u.id
ORDER BY receipts_scanned DESC, total_spent DESC
LIMIT 10;
```

### 📊 Result
```
    user_id                        receipts_scanned    total_spent
    62ffec490d9dbaff18c0a999       3                   52.28
    62c09104baa38d1a1f6c260e       3                   20.28
    61a58ac49c135b462ccddd1c       3                   19.92
    610a8541ca1fab5b417b5d33       3                   17.65
    5c366bf06d9819129dfa1118       3                   17.42
    6528a0a388a3a884364d94dc       3                   12.50
    643059f0838dd2651fb27f50       2                   75.99
    6351760a3a4a3534d9393ecd       2                   27.74
    64dd9170516348066e7c4006       2                   26.52
    5b441360be53340f289b0795       2                   18.32
```
