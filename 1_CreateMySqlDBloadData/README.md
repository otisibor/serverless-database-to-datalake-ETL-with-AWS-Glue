# Module 1: Create an RDS MySql Database and Load Sample data into it

In this module you will create an RDS MySql Database and load sample data into it.


## Implementation Instructions

Each of the following sections provide an implementation overview and detailed, step-by-step instructions. The overview should provide enough context for you to complete the implementation if you're already familiar with the AWS Management Console or you want to explore the services yourself without following a walkthrough.

### Prepare resources 

In this step, we will use a CloudFormation template to provision the RDS MySql database which we will need in later steps of the workshop.

Region| Region Code | Launch
------|------|-------
US East (N. Virginia) |   <span style="font-family:'Courier';">us-east-1</span> | [![Launch Module 1 in us-east-1](http://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/images/cloudformation-launch-stack-button.png)](https://console.aws.amazon.com/cloudformation/home?region=us-east-1#/stacks/new?stackName=DB-to-DL&templateURL=https://sapuzzle.com.s3.amazonaws.com/serverless-database-to-datalake-ETL-with-AWS-Glue/setup.yaml)


<details>
<summary><strong>CloudFormation Launch Instructions (expand for details)</strong></summary><p>

1. Click the **Launch Stack** link above.

1. Click **Next** on the Select Template page.

1. On the Specify Details page, enter values for Database Name, DBPassword and DBUser, leave the rest default values and click **Next** .

1. On the Options page, leave all the defaults and click **Next**.

1. Click **Create Stack**.


1. Wait for the CloudFormation to finish launching resources before proceeding to the next step. 



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

