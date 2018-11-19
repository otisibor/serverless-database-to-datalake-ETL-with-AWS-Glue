# Module 2: Connect, discover and extract data from your MySql database using AWS Glue

In this module you will connect to your RDS MySql Database, discover and extract data into your Data Lake on S3 using AWS Glue.



### Create AWS Glue Crawler 

In this step, we will use a CloudFormation template to provision the RDS MySql database which we will need in later steps of the workshop.



<details>
<summary><strong>AWS Glue Crawler creation Instructions (expand for details)</strong></summary><p>

1. Go to [AWS Glue](https://console.aws.amazon.com/glue/home?region=us-east-1) on the console.

1. On the left pane, select **Crawlers** then Click **Add Crawler** .

1. Enter a ```DB-to-DL``` as **Crawler name** and click **Next** .

1. On the Add a data store page, click on the dropdown and select **JDBC** on the **Choose a data store** option and click **Add connection**.

1. On the Add connection page, enter ```RDSMySql``` as **Name** and **JDBC** as **Connection type** .
	For the JDBC URL, enter ```jdbc:mysql://endpoint:3306/mydatabase``` and replace endpoint with your database endpoint.

1. Enter the database username and password. 

1. From the dropdown menu, select the VPC where your RDS instance is.

1. From the drop down menu, select the one of the subnet your RDS instance uses. (Check the **details** section of the RDS instance page on the AWS Console for this information).

1. For security group, select one or more the Security groups that allows access to the data store in your VPC. Ensure the security group defined to allow **Security Group - Inbound** to your RDS instance is selected. This security group can be found on the **details** section of the RDS instance page on the AWS Console.Then click **Add**

1. This takes you back to the Add Crawler wizard. On the Add a data store page, enter ```mydatabase``` in the include path field then click **Next**

1. Select **NO** on the Add another data store page the click **Next**

1.



</p></details>


### 1A: Connect to the RDS MySql Database

Connect to the newly created RDS MySQL Database. 

<details>
<summary><strong>Step-by-step instructions (expand for details)</strong></summary><p>

1. Go to RDS instances on AWS [Console](https://console.aws.amazon.com/rds/home?region=us-east-1#dbinstances:). 

1. Click on the newly create instance and scroll down to the **Connect** . 

1. Ensure that the **Publicly accessible** is set to **Yes** and the database security group allows connection from your IP.
	
	See [here](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Overview.RDSSecurityGroups.html) for how to configure Security Groups

1. Using a SQL client of your choice, connect to the database using the endpoint, port, database name, database user and database password (that you defined when creating the database with CloudFormation)
	
	[Tableplus](https://tableplus.io/) and [SQL WorkBench/J](https://www.sql-workbench.eu/downloads.html) are both SQL clients that you can use for this tutorial.  
	
1. Download,open and run the [SampleData](https://s3-ap-southeast-1.amazonaws.com/sapuzzle.com/serverless-database-to-datalake-ETL-with-AWS-Glue/sampleData.sql) query on your SQL Client to create a table and load it with data.   

</details>


### 1B: Load sample data

Create a new table `customers` in your database and load sample data.

<details>
<summary><strong>Step-by-step instructions (expand for details)</strong></summary><p>

1. Download and open the [SampleData](https://s3-ap-southeast-1.amazonaws.com/sapuzzle.com/serverless-database-to-datalake-ETL-with-AWS-Glue/sampleData.sql) file.

1. Copy, paste and run the query on your SQL Client to create a table and load it with data.   

</details>



### 1C: Verify data is in database

Run the following command on your SQL client to query the data in your database
```SELECT * FROM CUSTOMERS;```
 

### Next module


After you have verified your database contains data, move onto the next module: [Connect, discover and extract data from your MySql database using AWS Glue](2_ExtractDataWithGlue)

