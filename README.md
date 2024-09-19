Project

Descriptive Analysis 

Project Title:
Comparing the phone inquiries received by the City of Vancouver’s department in 2023 and 2024
 
Project Description:
This project focuses on conducting a descriptive analysis of phone inquiries made to various Vancouver City departments across multiple communication channels between 2023 and 2024. The goal is to summarize and compare inquiry volumes year-over-year to provide actionable insights that will aid in improving the efficiency of the phone inquiry system.
 
Objective:
To analyse and compare phone inquiry data across Vancouver’s departments from 2023 to 2024, focusing on identifying trends and providing recommendations to enhance operational efficiency and customer service in handling phone inquiries.
 
Dataset:
The dataset includes inquiry records from various departments through different channels, with key attributes:

•	Department: The city department receiving the inquiry.

•	Type: The type or category of the inquiry.

•	Year Month: The timestamp of when the inquiry was made.

•	Channel: Communication medium used (e.g., phone, email).

•	Number of Records: Total inquiry volume through each channel.

•	BI_ID: Unique identifier assigned to each inquiry for traceability.
 
Methodology:


<img width="482" alt="image" src="https://github.com/user-attachments/assets/dc7f7798-2d4f-49be-a1f0-cd80b1ecadf3">


1. Data Collection and Preparation:

•	Data Import: Loaded the dataset into Excel for initial data exploration and analysis.

•	Data Cleaning: Addressed missing values, standardized data types, and removed duplicate entries.

•	Date Formatting: Reformatted the date field to the format (YYYY-MM-DD) for consistency.

•	Data Validation: Ensured consistency across departments and channels by eliminating outliers.

3. Data Processing:

•	AWS Glue ETL Pipeline: Designed and implemented an ETL pipeline on AWS Glue to automate data transformation.


<img width="475" alt="image" src="https://github.com/user-attachments/assets/1acce267-6950-435f-932a-e456cf2ab073">


•	Key Filtering: Applied a filter transformation to isolate records where the channel was "Phone."

•	Data Aggregation: Grouped by department, channel, and year, and aggregated the total phone inquiries using the COUNT function.

4. Descriptive Statistics:
   
•	Focused on the FSC-Property Tax department, performing year-over-year analysis for phone inquiries in 2023 and 2024.

•	Extracted and aggregated data to enable comparison between the two years.

6. Data Visualization:
   

<img width="482" alt="image" src="https://github.com/user-attachments/assets/9eaf3aa8-1f91-4850-83c1-78decb6def61">


•	Exported aggregated data as CSV and used Excel to visualize trends.

•	Generated bar charts to visually compare phone inquiries to the FSC-Property Tax department in 2023 vs. 2024.

7. Data Publishing:

•	EC2 Setup: Deployed a general EC2 instance without HTTP access to restrict internal use.

•	IIS Configuration: Configured IIS on the EC2 instance to host and publish the data publicly, with secure internal access for authorized personnel.

8. Data Protection:

•	Encryption: Enabled Server-Side Encryption (SSE) with AWS KMS for securing the dataset.

•	S3 Versioning: Activated versioning for auditability and recovery of historical data.

•	Cross-Region Replication (CRR): Configured CRR to ensure geographical redundancy and disaster recovery.

•	Combined KMS, Versioning, and Replication for robust security and disaster resilience.

10. Data Governance:
    

<img width="468" alt="image" src="https://github.com/user-attachments/assets/fd16a151-2228-4614-b0a2-49284c7c96a7">


•	Utilized AWS Glue for sensitive data detection and data quality assessment.

•	Trusted S3 Bucket: All critical files were stored in a trusted, controlled-access S3 bucket with automated workflows for replication and monitoring.

11. Data Monitoring:
    

<img width="488" alt="image" src="https://github.com/user-attachments/assets/4d5c77f2-9624-4642-a674-3e4c87853074">


•	CloudWatch Dashboards: Set up monitoring for key S3 operations.

•	CloudTrail: Configured CloudTrail to log activity, stored securely in an S3 bucket with its own encryption key for additional security.
 
Insights and Findings:

•	Phone inquiries to the FSC-Property Tax department saw an increase in 2024 compared to 2023, signalling potential inefficiencies in the current system.

•	The security framework effectively safeguarded data from unauthorized access, ensuring Confidentiality, Integrity, and Availability (CIA).

•	Cross-region data replication provides geographical redundancy, ensuring disaster recovery readiness.

•	Monitoring and error handling processes resulted in high-quality data throughout the pipeline.
 
Recommendations:

•	Operational Optimization: Introduce automation to reduce phone call volume, potentially through an IVR system or online self-service portals.

•	Scaling Considerations: Continuously monitor inquiry trends and adjust system capacity, accordingly, using AWS Auto Scaling.

•	Cost Efficiency: Optimize by moving to smaller EC2 instances, reducing unnecessary S3 monitoring, and implementing AWS cost-saving measures such as S3 Intelligent-Tiering.

•	Sustainability Practices: Align the platform with AWS sustainability initiatives to lower carbon footprint while maintaining cost-efficiency.
