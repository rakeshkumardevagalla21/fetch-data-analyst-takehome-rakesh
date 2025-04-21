
## 📩 Communication with Stakeholders

Hi Recruitment Team,

I’ve completed a first pass at reviewing the transaction, product, and user data. Here’s a quick summary of what stood out:

### 🛠️ Data Quality Concerns:
- A significant number of records in the `FINAL_SALE` and `FINAL_QUANTITY` fields contain the string “zero” or just a space instead of actual numeric values. This impacts about 25% of the data and needs clarification before we can trust any sales-related metrics.
- The product categorization fields are inconsistent. Most products are missing values in `CATEGORY_3` and `CATEGORY_4`, making it unclear how complete or reliable the hierarchy is.
- There are also gaps in user profile data — around 30% of users have missing language information, and several records lack birthdate or gender details.

### 📈 Interesting Early Trend:
Among users who have been with us for more than six months, the top-selling brands tend to cluster around household and wellness categories. This could indicate stronger brand engagement in those areas among longer-term users.

### ❓ Open Questions / Request:
- Should we interpret “zero” and blank values in sales and quantity as actual zeros, or are they placeholders for missing or unverified data?
- Is there any documentation or guidance on how the product category hierarchy is structured and intended to be used?

Happy to dig further once we align on these. Let me know if there’s someone I should connect with for more context.

Best,  
**Rakesh Devagalla**
