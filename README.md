# Elevate-Labs-DAY-6
📘 Task 6 – Sales Trend Analysis Using Aggregations 

🧠 Objective :

    Analyze monthly revenue and order volume from the online_sales dataset to uncover time-based trends in customer behavior and sales performance.

🛠️ Tools :

    Compatible with: PostgreSQL, MySQL, or SQLite
  
    SQL dialect-specific adjustments noted where applicable

📂 Dataset :

      Table: orders Columns:

      order_id (unique identifier)
    
      order_date (date of transaction)

      amount (total revenue per order)

      product_id (product reference)

📄 Deliverables :
  ✅ SQL script for trend analysis

  ✅ Results table showing monthly revenue and order volume

🧭 Guide & Hints :
          Step	Description :
          
        a.	Use EXTRACT(MONTH FROM order_date) or STRFTIME('%m', order_date) (SQLite) to extract month
        
        b.	Group by EXTRACT(YEAR FROM order_date), EXTRACT(MONTH FROM order_date) or STRFTIME('%Y-%m', order_date)
            
        c.	Use SUM(amount) to calculate total revenue
    
        d.	Use COUNT(DISTINCT order_id) to calculate order volume

        e.	Use ORDER BY year, month to sort chronologically
        
        f.	Use WHERE clause to filter specific time periods (e.g., '2023-01')
    
🧪 Sample SQL (SQLite Version) :

        sql
        
        SELECT
        
        STRFTIME('%Y', order_date) AS year,
        
        STRFTIME('%m', order_date) AS month,
        
        COUNT(DISTINCT order_id) AS order_volume,
        
        SUM(amount) AS total_revenue
        
        FROM orders
        
        GROUP BY year, month
        
        ORDER BY year, month;
     
📊 Sample Output :

    Year	Month	Order Total Revenue
    2023	01	   120	₹98,500.00
    2023	02	    95	₹76,200.00
    ... 	...	  ...	 ...
    
🎯 Outcome :

    Learn to group and aggregate data by time dimensions

    Identify seasonal trends, peak months, and sales fluctuations

    Build foundational skills for time-series analysis and dashboarding
