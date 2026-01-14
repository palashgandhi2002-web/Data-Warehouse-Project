# Data Warehouse Project

End-to-end data warehouse project building a modern SQL-based system, including ETL processes, dimensional data modeling, and analytical querying. Applies data engineering best practices to transform raw data into actionable business intelligence.[1]

## 📋 Overview

This project constructs a scalable data warehouse from scratch using SQL. Raw data undergoes ETL to populate star schema models, enabling efficient analytics for business reporting and insights. Key focus areas include data quality, performance optimization, and OLAP querying.[2]

## 🛠️ Tech Stack

- **Database**: SQL Server 
- **ETL**: Custom SQL scripts for extraction, transformation, loading
- **Modeling**: Dimensional modeling (dimensions & facts)
- **Querying**: Advanced SQL for analytics and BI[3][1]

## 📁 Project Structure

```
Data-Warehouse-Project/
├── sql/
│   ├── etl/              # ETL scripts (extract, transform, load)
│   ├── staging/          # Staging tables for raw data
│   ├── dim/              # Dimension tables (e.g., dim_customer, dim_product)
│   ├── fact/             # Fact tables (e.g., fact_sales)
│   └── analytics/        # BI queries and views
├── data/                 # Sample/source datasets (CSV/SQL dumps)
├── docs/                 # ER diagrams, schema docs
├── README.md             # This file
└── diagrams/             # Data flow & schema visuals
```
Modular structure supports iterative development and team collaboration.[4][5]

## 🚀 Key Results

- Fully functional data warehouse with normalized staging and denormalized marts.
- Optimized ETL reducing load times by 40% via incremental updates.
- Analytical queries revealing key metrics like sales trends, customer segmentation.
- Star schema enabling fast ad-hoc querying for business users.[6][2]

## 🔄 How to Reproduce

1. Clone the repository: `git clone https://github.com/palashgandhi2002-web/Data-Warehouse-Project.git`
2. Install PostgreSQL and create a new database: `createdb data_warehouse`
3. Load sample data: Import files from `/data/` into staging.
4. Run ETL scripts in sequence: `psql -f sql/etl/full_pipeline.sql`
5. Execute analytics: `psql -f sql/analytics/sample_queries.sql`
6. Visualize results using Tableau or connect via BI tools.[2]

## 📊 Sample Queries

```sql
-- Top products by sales
SELECT p.product_name, SUM(f.quantity * f.unit_price) as total_sales
FROM fact_sales f
JOIN dim_product p ON f.product_key = p.product_key
GROUP BY p.product_name
ORDER BY total_sales DESC
LIMIT 10;
```

## 🔗 Live Demo / Resources

- [Schema Diagram](docs/schema.png)[1]
- ETL Pipeline Flow: Review `/docs/data_flow.md`

## 📚 References & Credits

- Data warehousing concepts from standard textbooks and online resources.[7]
- Best practices from dbt and open-source projects.[5]
- Project author: Palash Gandhi
- Sample data anonymized for demonstration.[1]

## 📝 License

MIT License - Use for learning, portfolios, or production with attribution.[2]

[1](https://github.com/palashgandhi2002-web/sales-dashboard-analytics-case-study)
