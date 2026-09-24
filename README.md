# 🛒 Supermarket Analytics Dashboard | Power BI

## 📌 Project Overview

This project presents an interactive **Supermarket Analytics Dashboard** developed in Microsoft Power BI to analyze sales performance, profitability, customer behavior, product performance, and operational activity.

The dashboard transforms 1,000 supermarket transactions into an interactive business intelligence solution that allows users to explore performance across different branches, product categories, customer segments, payment methods, time periods, and order statuses.

The project was designed as a portfolio project to demonstrate practical skills in **data preparation, data modeling, DAX, business analysis, and Power BI visualization**.

---

## 🎯 Business Problem

A supermarket generates large volumes of transaction data, but raw transaction records alone do not provide an immediate understanding of business performance.

This project addresses questions such as:

* How much revenue is being generated?
* Which branches generate the most sales and profit?
* Which product categories perform best?
* Which products contribute the most to sales?
* How effective are discounts?
* What percentage of orders are returned or cancelled?
* Which customer groups contribute most to sales?
* Which payment methods are most commonly used?
* During which periods of the day are sales highest?
* Which categories provide stronger profit margins?

The dashboard brings these questions together in a single interactive reporting environment.

---

## 📊 Dataset

The dataset contains **1,000 simulated supermarket transactions** covering the year **2025**.

### Main Data Fields

| Area                | Fields                             |
| ------------------- | ---------------------------------- |
| Transaction         | Invoice ID, Order Date, Order Time |
| Location            | Branch, City                       |
| Customer            | Customer Type, Gender              |
| Product             | Product Category, Product          |
| Sales               | Quantity, Unit Price, Gross Sales  |
| Discount            | Discount %, Discount Amount        |
| Financials          | Net Sales, COGS, Gross Profit      |
| Operations          | Payment Method, Order Status       |
| Customer Experience | Customer Rating                    |

Additional analytical fields were created during data preparation:

* Order Hour
* Time Period
* Discount Band

---

## 🔄 Data Preparation

The raw dataset was imported into **Power Query** for transformation and validation.

The preparation process included:

1. Verifying column names and data structure.
2. Assigning appropriate data types.
3. Checking the dataset for errors and missing values.
4. Extracting the hour from the order time.
5. Creating time-of-day categories.
6. Grouping discount percentages into meaningful bands.
7. Preparing the dataset for DAX calculations and visualization.

### Time Period Classification

| Order Hour | Time Period |
| ---------- | ----------- |
| Up to 11   | Morning     |
| 12–16      | Afternoon   |
| 17–20      | Evening     |
| 21–22      | Night       |

### Discount Classification

| Discount  | Discount Band |
| --------- | ------------- |
| 0%        | No Discount   |
| Up to 5%  | Low           |
| Up to 10% | Medium        |
| Up to 15% | High          |
| Above 15% | Very High     |

---

## 🧮 Key DAX Measures

Several DAX measures were created to support the dashboard.

### Total Sales

```DAX
Total Sales =
CALCULATE(
    SUM(Supermarket_Data[Net_Sales]),
    Supermarket_Data[Order_Status] = "Completed"
)
```

### Total Profit

```DAX
Total Profit =
CALCULATE(
    SUM(Supermarket_Data[Gross_Profit]),
    Supermarket_Data[Order_Status] = "Completed"
)
```

### Total Orders

```DAX
Total Orders =
CALCULATE(
    DISTINCTCOUNT(Supermarket_Data[Invoice_ID]),
    Supermarket_Data[Order_Status] = "Completed"
)
```

### Average Order Value

```DAX
Average Order Value =
DIVIDE(
    [Total Sales],
    [Total Orders],
    0
)
```

### Profit Margin

```DAX
Profit Margin % =
DIVIDE(
    [Total Profit],
    [Total Sales],
    0
)
```

Additional measures were created for:

* Total Items Sold
* Average Customer Rating
* Total Discount
* Returned Orders
* Cancelled Orders
* Return Rate
* Cancelled Rate

---

# 📈 Analytical Areas

Instead of simply displaying transaction totals, the dashboard was designed around several analytical perspectives.

## 1. Sales Performance

The dashboard evaluates overall sales through:

* Total sales
* Monthly sales movement
* Category-level sales
* Branch-level sales
* Payment-method contribution

This provides a high-level view of the supermarket's sales activity.

---

## 2. Product Performance

Product-level analysis helps identify:

* Highest-selling products
* Product category performance
* Quantity sold
* Category-level revenue
* Category-level profitability

A **Top 10 Products by Sales** analysis was included to make product performance easier to interpret.

---

## 3. Customer Analysis

Customer-related analysis includes:

* Member vs Normal customers
* Male vs Female customer sales
* Average customer rating
* Customer purchasing patterns
* Payment preferences

These views help connect sales performance with customer characteristics.

---

## 4. Profitability Analysis

Revenue alone does not provide a complete picture of business performance.

The dashboard therefore analyzes:

* Total profit
* Profit margin
* Profit by branch
* Profit by category
* Sales vs profit
* Discount amounts

This allows sales and profitability to be examined together.

---

## 5. Operational Analysis

Operational performance is analyzed through:

* Completed orders
* Returned orders
* Cancelled orders
* Return rate
* Cancellation rate
* Sales by hour
* Sales by time period

This adds an operational perspective beyond traditional sales reporting.

---

# 📑 Dashboard Structure

The Power BI report contains three analytical sections.

### Sales Overview

Focuses on overall sales performance, including:

* Sales
* Profit
* Orders
* Average Order Value
* Monthly trends
* Category performance
* Branch performance
* Payment methods

### Product & Customer Analysis

Focuses on:

* Top-selling products
* Product categories
* Customer types
* Gender
* Payment methods
* Quantity sold
* Customer ratings

### Profitability & Operations

Focuses on:

* Branch profitability
* Profit margins
* Discounts
* Order statuses
* Returns
* Cancellations
* Time-of-day sales
* Sales vs profit

---

# 🛠️ Tools & Technologies

* **Microsoft Power BI**
* **Power Query**
* **DAX**
* **Microsoft Excel**
* **Data Visualization**
* **Business Intelligence**

---

# 💡 Skills Demonstrated

This project demonstrates practical experience in:

* Data cleaning
* Data transformation
* Power Query
* DAX calculations
* KPI development
* Interactive dashboard design
* Business performance analysis
* Sales analysis
* Profitability analysis
* Customer segmentation
* Operational analysis
* Data visualization
* Slicer and filter implementation
* Top-N analysis

---

# 🔍 Key Analytical Approach

A major focus of this project was separating **completed transactions** from operational exceptions.

For example, sales and profit KPIs are calculated using completed orders, while returned and cancelled transactions are analyzed separately.

This prevents returned or cancelled transactions from being treated the same way as successfully completed sales.

---

# ⚠️ Dataset & Assumptions

This project uses a **synthetically generated dataset created for portfolio and learning purposes**.

The transaction records do not represent an actual supermarket or real customers.

Financial fields such as COGS and Gross Profit are based on simulated assumptions rather than real company financial records.

Therefore, the dashboard demonstrates the **analytical process and Power BI implementation**, rather than reporting actual business performance.

---

# 🚀 Project Outcome

The final dashboard converts raw supermarket transaction data into an interactive analytical report covering **sales, products, customers, profitability, and operations**.

The project demonstrates how Power BI can be used to move from raw transactional data to meaningful business insights through **Power Query transformations, DAX measures, interactive visualizations, and structured dashboard design**.

---

## 👩‍💻 Author

**Ankita Sharma**

Aspiring Data Analyst | Power BI | Excel | SQL | Data Analytics

---

## 📌 Project Type

**Data Analytics / Business Intelligence Portfolio Project**

**Dataset:** Synthetic
**Records:** 1,000 transactions
**Year:** 2025
**Tool:** Microsoft Power BI

## Dataset Used
- <a href="https://github.com/anki1908/Supermarket-analytics-pbi-dashboard/blob/main/Supermarket%20Analytics%20Dashboard.pbix"> Dataset view </a>

## Dashboard layout
- <a href="https://github.com/anki1908/Supermarket-analytics-pbi-dashboard/blob/main/a1.png"> Dataset view </a>
- <a href="https://github.com/anki1908/Supermarket-analytics-pbi-dashboard/blob/main/a2.png"> Dataset view </a>
- <a href="https://github.com/anki1908/Supermarket-analytics-pbi-dashboard/blob/main/a3.png"> Dataset view </a>

<img width="1436" height="806" alt="a1" src="https://github.com/user-attachments/assets/9d79f01d-d458-43ef-ae4c-3c3456554482" />
<img width="1437" height="803" alt="a2" src="https://github.com/user-attachments/assets/494b3897-a905-4d1b-bfc3-e7f1709d449f" />
<img width="1436" height="802" alt="a3" src="https://github.com/user-attachments/assets/86b8ee21-ec67-4ba7-b701-21811eef0524" />
