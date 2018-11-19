# serverless-database-to-datalake-ETL-with-AWS-Glue

AWS Glue is a fully managed extract, transform, and load (ETL) service that makes it easy for customers to prepare and load their data for analytics.

In this tutorial, you will learn how to use [AWS Glue](https://aws.amazon.com/glue/),to connect to and extract data from a relational database, we will be using  [Amazon RDS MySql](https://aws.amazon.com/rds/); into an S3 Data Lake then transform the data into Parquet format to increase analytics performance then perform server-less queries on the data using [Amazon Athena](https://aws.amazon.com/athena/).


Please see below for the solution architecture


<img src="99_resources/architecture_diagram.png" width="100%">

## Prerequisites

### AWS Account

In order to complete this workshop you'll need an AWS Account with sufficient permission to create AWS IAM, Amazon RDS, AWS Glue and Amazon Athena. The code and instructions in this workshop assume only one student is using a given AWS account at a time. If you try sharing an account with another student, you'll run into naming conflicts for certain resources. You can work around these by appending a unique suffix to the resources that fail to create due to conflicts, but the instructions do not provide details on the changes required to make this work.

## Modules

This workshop is broken up into multiple modules. You must complete the modules in sequence starting from the first module before proceeding to the next:

1. [Create a RDS MySql Database and load sample data](blob/master/1_CreateMySqlDBloadData/README.md)
2. [Connect, discover and extract data from your MySql database using AWS Glue](02_ExtractDataWithGlue)

Once you have successfully extracted the data from your MySql database into your Data Lake, you can choose to complete one or more of the following modules:

* [Perform server-less perform transformation on your data with AWS Glue(Coming Soon)](03_AmazonConnectIntegration)
* [Serverlessly query your data using Amazon Athena(Coming Soon) ](04_TwilioSMSIntegration)

Extra credit ideas:

* [Extra credit](10_ExtraCredit)

Resource cleanup:

* [Resource clean-up](11_Cleanup)
