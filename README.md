# testRepoForGit
Learning git

The IRDB project leverages Databricks as its core platform for reporting and advanced analytics. Source data is received in the form of Parquet files, which are stored in AWS S3. Databricks AutoLoader is used to efficiently ingest this data from S3 into Databricks, supporting schema inference and incremental loading for continuous data processing. The architecture follows a structured Medallion approach, with clearly defined schemas for each layer—Bronze, Silver, and Gold.

In the Bronze layer, raw, unprocessed data is ingested and stored for archival and traceability purposes. The data then moves to the Silver layer, where it undergoes cleansing, validation, and enrichment processes to ensure data quality. During this stage, additional derived fields and business logic are applied to enhance data usability. The Gold layer further refines the data into curated datasets, supporting specific analytical use cases and business reporting needs.

Downstream applications and data consumers, such as BI tools and dashboards, primarily consume data from the Silver and Gold layers depending on their use case requirements. Additionally, Silver layer data can be copied back to AWS S3 for broader access and integration with external systems or applications. This robust architecture ensures reliable, scalable, and high-quality data delivery, empowering IRDB’s analytics and reporting ecosystem.
