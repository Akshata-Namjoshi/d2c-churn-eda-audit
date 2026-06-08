# Data Quality Audit Report

## 1. Executive Summary
We scanned the customer dataset (2,400 records) to check if it was ready for AI modeling. Overall, the data is clean (no duplicates), but we found specific missing information that we need to fix before building our predictions.

## 2. Missing Values Found
| Column Name | Missing Rows | Impact | Solution |
| :--- | :--- | :--- | :--- |
| Loyalty Tier | 1,386 rows | High | These are likely new customers who haven't earned a tier yet. We labeled them as "Missing_Tier". |
| Skin Type | 401 rows | Medium | Some users skipped the profile quiz. We labeled them as "Unknown". |
| Product Rating | 80 rows | Low | Some users didn't leave a review. We will fill this with the average rating. |

## 3. Consistency Check
- Duplicates: We checked for duplicate Customer IDs and found 0. The data is unique and safe to use.
- Outliers: We noticed some customers with very high spending or age. We will cap these values in Part 2 so they don't confuse the model.

## 4. Conclusion
The data is good enough to proceed to Part 2 (Segmentation), provided we handle the "Missing Loyalty Tier" group carefully, as they make up more than 50% of our database.