**E-Commerce Cohort Retention Analysis**

I wanted to actually understand cohort analysis instead of just reading about it, so I built this in Power BI using a simulated e-commerce dataset — 3,000 customers and their orders over about two and a half years. The question I was trying to answer: once someone buys from you, how long do they actually keep coming back, and does that depend on what kind of customer they are?

**The data**
3,000 customers, ~12,100 orders, Jan 2024 – Jun 2026
Each order has a customer ID, signup month (their cohort), order date, revenue, and a segment tag (Discount Shopper, Loyal Regular, One-Time Buyer, Subscriber-like)
Built in Power Query + DAX, matrix visuals

**How the cohort logic works**
The core idea: tag every customer with their signup month (that's their "cohort"), then for every order they place afterward, figure out how many months it's been since they first bought something.

**DAX:**
Cohort Index = 
DATEDIFF(
    Orders[First Purchase Date],
    Orders[order_date],
    MONTH
)

**Retention is just**: of everyone in a cohort, what % are still buying N months later?


Mainly built this to get comfortable with cohort logic in DAX and time-based filtering — happy to walk through any of the measures if useful.
