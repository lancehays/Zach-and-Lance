**Zach Ernesti**

**My partner is Wendy Rosenquist, and her group is creating a database for a gym called Avolve Fitness. They operate like a typical gym, and as such will have questions common for that industry.**

**Questions for Avolve Fitness by Zach Ernesti:**

**1.** Q1: What is your busiest day of the week based on member sign ins?
```sql
SELECT in
FROM visits
GROUP BY COUNT (in)
```
**2.** Q2: How many personal trainers do you have per member?
```sql
SELCET employeenumber, memberid
FROM personal trainers, customers
SUM (employeenumber) / SUM (memberid)
```
**3.** Q3: How much membership revenue do you earn a month?
```sql
SELECT fees
FROM customers
SUM (fees)
WHERE last_pay_date >= 2019-08-31
