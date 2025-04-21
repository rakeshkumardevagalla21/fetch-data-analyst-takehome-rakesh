
# 📊 Exercise: Part 1 – Explore the Data

## 🎯 Objective
To evaluate the quality and structure of the provided datasets (`Users`, `Transactions`, and `Products`) using Python, SQL, and visualizations. The goal is to identify any data quality issues and fields that may require clarification before proceeding with deeper analysis.

---

## 1️⃣ Are there any data quality issues present?

Yes, several data quality issues were identified:

### 🧾 Products Table
- `CATEGORY_4` is missing in over **90%** of rows.
- `MANUFACTURER` and `BRAND` are missing in approximately **27%** of records.
- `BARCODE` values have inconsistent formatting and length, which could affect joins or filtering.

### 🧾 Transactions Table
- `BARCODE` is missing in **~11.5%** of rows.
- `FINAL_SALE` and `FINAL_QUANTITY` contain invalid string values like `"zero"` or a blank space, which must be cleaned before use in numerical operations.

### 🧾 Users Table
- `LANGUAGE` is missing in **~30%** of records.
- `GENDER`, `STATE`, and `BIRTH_DATE` are missing in **4–6%** of users.

> These issues may cause join failures, inaccurate groupings, or misleading summary statistics unless resolved.

---

## 2️⃣ Are there any fields that are challenging to understand?

Yes, the following fields need clarification or transformation:

### 🔹 `FINAL_SALE` and `FINAL_QUANTITY`
- Should be numeric, but currently contain text-based entries like `'zero'` and `' '`, which require cleaning.

### 🔹 `CATEGORY_1` through `CATEGORY_4`
- Intended as a product category hierarchy, but no documentation is provided.
- Most records only use up to `CATEGORY_3`, with `CATEGORY_4` rarely populated.

### 🔹 `BARCODE`
- Used as a join key but stored as a float in some files, leading to potential precision issues.

---

