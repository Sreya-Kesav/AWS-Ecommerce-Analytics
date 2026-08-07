# ☁️ AWS Implementation Notes

This folder documents the AWS services I used while building my end-to-end cloud analytics project.

The goal was to create a serverless analytics pipeline where the raw data is stored in Amazon S3, cataloged using AWS Glue, queried with Amazon Athena, and finally connected to Power BI for reporting.

---

# 🪣 Step 1 – Amazon S3

The first step of the project was uploading the raw e-commerce dataset to Amazon S3.

Instead of storing the data locally or importing it into a database, I used S3 as the central storage layer for the entire analytics pipeline.

### What I did

- Created an S3 bucket for the project.
- Uploaded the raw CSV datasets.
- Organized the files into separate folders for better management.
- Used the bucket as the data source for AWS Glue.


### What I learned

This helped me understand that Amazon S3 acts as a cloud data lake. The data remains in one place while other AWS services such as Glue and Athena work directly on top of it.

---

# 📚 Step 2 – AWS Glue

Once the data was uploaded to S3, I used AWS Glue to make the dataset available for querying.

Instead of manually defining table schemas, I created a crawler that scanned the S3 bucket and automatically generated the metadata.

### What I did

- Created a Glue Database named **ecommerce_analytics**.
- Configured a Glue Crawler.
- Crawled the S3 bucket.
- Automatically created metadata for the uploaded CSV files.


### What I learned

AWS Glue simplifies data preparation by automatically detecting the schema and creating tables that Amazon Athena can query directly.

---

# 🔐 Step 3 – IAM

To securely connect Amazon Athena with Power BI, I created a dedicated IAM user instead of using the AWS root account.

I also configured the required permissions so Power BI could access Athena safely.

### What I did

- Created an IAM User.
- Created an IAM User Group.
- Assigned the required permissions.
- Created a Glue Service Role for the crawler.

### What I learned

This helped me understand why AWS recommends following the Principle of Least Privilege instead of using the root account for everyday tasks.

---

# 🔍 Step 4 – Amazon Athena

After the Glue Data Catalog was created, I used Amazon Athena to query the data stored in Amazon S3.

Since Athena is serverless, I didn't need to provision or manage any database servers.

### What I did

- Queried data directly from S3.
- Verified the imported tables.
- Wrote SQL queries for data exploration.
- Created a SQL View (`vw_orders_clean`) to simplify reporting in Power BI.
- 

### What I learned

Amazon Athena made it possible to query data stored in S3 using standard SQL without moving the data into a traditional database.

---

# 💡 Key Takeaways

Working on this project helped me understand how different AWS services work together in a modern cloud analytics solution.

My biggest learnings were:

- Using Amazon S3 as the storage layer.
- Automating metadata creation using AWS Glue.
- Querying cloud data using Amazon Athena.
- Configuring IAM users and permissions securely.
- Connecting AWS services with Power BI for business reporting.

This project gave me practical experience in building a simple serverless analytics pipeline using AWS.
