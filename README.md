# EdTech Business Analysis

SQL analysis of a real-world masked EdTech dataset covering revenue trends, course performance, teacher metrics, and lead-to-enrollment conversion funnel.

---

## Dataset

A masked dataset from an EdTech organization operating in the JEE/NEET segment. Data spans February 2025 to June 2026.

| Table | Rows | Description |
|---|---|---|
| students | 995 | Student profiles |
| teachers | 15 | Teacher profiles |
| courses | 80 | Course catalog with category and plan type |
| enrollments | 414 | Student-course enrollments (paid and free trial) |
| payments | 355 | Payment transactions |
| leads | 4,519 | Marketing leads after data cleanup |
| campaigns | 30 | Marketing campaign metadata |

---

## Business Questions Answered

**Section 1 — Revenue Analysis**
- What is the overall revenue and enrollment summary?
- Which course category generates the most revenue?
- Which plan type (monthly, quarterly, etc.) drives the most revenue?
- Which payment mode is most used?
- How has monthly revenue trended over time?

**Section 2 — Course and Teacher Performance**
- Which courses have the highest enrollment?
- Which courses generate the most revenue?
- Which teachers have the most student enrollments?
- Which teachers generate the most revenue?

**Section 3 — Lead Funnel and Campaign Analysis**
- What is the overall lead-to-enrollment conversion rate?
- Which campaign source converts best?
- Which individual campaigns drove the most conversions?
- How many days does it take on average to convert a lead?

**Section 4 — Window Functions**
- Rank teachers by revenue using RANK()
- Calculate running total of monthly revenue using SUM() OVER
- Compare month-over-month revenue using LAG()

---

## Key Findings

- Total revenue of ₹710,465 generated from 355 paid enrollments across 414 total enrollments
- JEE Advanced is the highest revenue category at ₹286,956, closely followed by JEE Main and NEET
- Monthly plans dominate enrollments but yearly and half-yearly plans generate more revenue per student
- UPI is the dominant payment mode at ₹388,866 (55% of total revenue)
- Teacher_3 alone accounts for 36% of total revenue (₹259,824) despite being one of 13 active teachers
- Overall lead conversion rate is 12% (530 converted out of 4,519 leads)
- Friend Referral has the highest conversion rate at 17% despite low lead volume
- Average days from lead to enrollment is 81 days

---

## Data Limitations

- 337 lead records were deleted during cleanup where lead_date was after enrollment_date
- campaign_id and student_id columns were found swapped in the leads table and corrected before analysis
- Q10 includes two versions (with and without DISTINCT) to demonstrate duplicate lead detection
- June 2026 revenue is partial and will appear lower than preceding months
- Dataset is masked — organization name and individual identifiers have been removed

---

## Tools Used

- MySQL 8.0
- MySQL Workbench

---

## Author

**Nipun Arya**
[LinkedIn](https://linkedin.com/in/nipun-arya-pm) | [GitHub](https://github.com/Nipunarya250)
