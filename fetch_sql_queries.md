## 📌 Closed-Ended Question 1: Top 5 Brands by Receipts Scanned (21+ Users)

### 🔍 SQL Query

```sql
SELECT \
    p.brand,\
    COUNT(DISTINCT t.receipt_id) AS receipt_count\
FROM Transactions t\
JOIN Users u ON t.user_id = u.id\
JOIN Products p ON t.barcode = p.barcode\
WHERE \
    u.birth_date IS NOT NULL AND\
    DATE('now') >= DATE(u.birth_date, '+21 years')\
GROUP BY p.brand\
ORDER BY receipt_count DESC\
LIMIT 5;\
\
```

### 📊 Result

```
Result:\
7200
226 3 4 000
00 3              BRAND  receipt_count\
0      NERDS CANDY              3\
1             DOVE              3\
2             None              3\
3          TRIDENT              2\
4  SOUR PATCH KIDS              2\
720144021602880360043205040576064807200792086400
024 0 1 100 00 \
\
```

## 📌 Closed-Ended Question 2: Top 5 Brands by Sales (Accounts ≥ 6 Months)

### 🔍 SQL Query

```sql
SELECT \
    p.brand,\
    SUM(t.FINAL_SALE) AS total_sales\
FROM Transactions t\
JOIN Users u ON t.user_id = u.id\
JOIN Products p ON t.barcode = p.barcode\
WHERE \
    u.created_date <= DATE('now', '-6 months') AND\
    t.FINAL_SALE IS NOT NULL\
GROUP BY p.brand\
ORDER BY total_sales DESC\
LIMIT 5;\
\
```

### 📊 Result

```
Result:\
7200
226 3 4 3          BRAND  total_sales\
0          CVS        72.00\
1      TRIDENT        46.72\
2         DOVE        42.88\
3  COORS LIGHT        34.96\
4         None        16.65\
720144021602880360043205040576064807200792086400
128 0 1 2 \
\
Open Ended Qs1: Who are Fetch\'92s power users?\
\
SELECT \
    u.id AS user_id,\
    COUNT(DISTINCT t.receipt_id) AS receipts_scanned,\
    SUM(t.FINAL_SALE) AS total_spent\
FROM Transactions t\
JOIN Users u ON t.user_id = u.id\
WHERE t.FINAL_SALE IS NOT NULL\
GROUP BY u.id\
ORDER BY receipts_scanned DESC, total_spent DESC\
LIMIT 10;\
\
Result:\
7200
226 3 4 3                     user_id  receipts_scanned  total_spent\
0  62ffec490d9dbaff18c0a999                 3        52.28\
1  62c09104baa38d1a1f6c260e                 3        20.28\
2  61a58ac49c135b462ccddd1c                 3        19.92\
3  610a8541ca1fab5b417b5d33                 3        17.65\
4  5c366bf06d9819129dfa1118                 3        17.42\
5  6528a0a388a3a884364d94dc                 3        12.50\
6  643059f0838dd2651fb27f50                 2        75.99\
7  6351760a3a4a3534d9393ecd                 2        27.74\
8  64dd9170516348066e7c4006                 2        26.52\
9  5b441360be53340f289b0795                 2        18.32
128 0 1 2 \
```