# Kafka-Real-Time-Stock-Market-Project
Real time stock market data piepline project


---------------------------------

Detailed Summary for [📈 Stock Market Real-Time Data Analysis Using Kafka | End-To-End Data Engineering Project]

Real-Time Stock Market Data Analysis using Kafka

 Designing a stock market data processing engine using Kafka
- Prerequisites required: laptop, internet connection, Python installed, basic understanding of Python, AWS account
- Divided into three parts: understanding prerequisites, basics of Kafka and its architecture, hands-on practice

 Kafka is a distributed event store and stream processing platform.
- Real-time streaming is important for applications like Google Maps, Uber, and Amazon.
- Real-time streaming allows for instant notifications and updates.

 Kafka is a distributed system with brokers, producers, and consumers.
- Kafka cluster consists of multiple brokers, which are like servers or nodes.
- Producers produce data, which is written to the Kafka cluster, and consumers consume the data for various activities.

 Zookeeper is the manager of the Kafka cluster, ensuring proper functioning and data integrity.
- Zookeeper manages server access control list, security, and overall cluster management.
- Zookeeper enables distributed synchronization and coordination for reliable replication of data.

 Understanding the basics of Kafka
- Data is written onto brokers in Kafka
- Topics are partitioned using log files

Understanding the architecture diagram of the project
- Simulating a real-time stock market application using a dataset
- Pushing events into Kafka broker with a producer code and consuming the data

 Connect to EC2 instance and download Apache Kafka compressed version
- Connect to EC2 instance using instance ID and command provided
- Download Apache Kafka compressed version using 'wget' command

 Install Kafka and Java on your local machine or EC2 instance
- Download and uncompress Kafka server files
- Install Java 1.8 on your EC2 instance
- Check Java version to verify installation
- Start Zookeeper and Kafka server

 Change private IP to public IP to access EC2 machine outside of the network.
- Stop both servers (Ctrl Z, Ctrl C).
- Edit 'config.properties' file and replace the private IP with the public IP of your EC2 machine (65.2.168.105). Save the file (Ctrl x, y, enter).
- Start Zookeeper server, then start the Kafka server on the public IP address.

 Setting up Zookeeper, Kafka server, and configuring inbound rules for accessing EC2 instance.
- Zookeeper and Kafka server are installed.
- Inbound rules in security groups are edited to allow access from local machine to EC2 instance.

 Real-time data from producer can be seen on the consumer side using Kafka server.
- Use EC2 instance to connect to Kafka folder and start consumer code.
- Producer sends data to Kafka server, which can be consumed and seen in real-time.

Python code will be used to push stock market data in real-time, consume it, and upload it to Amazon S3.
- Install the Kafka python package using pip install Kafka python.
- Import the required packages like pandas and the consumer module.

 Import necessary packages, create consumer and producer objects, and loop through consumer to print the consumed data.
- You can import the 'consumer' package and forget about the 'producer' package.
- You can also use the 'producer' package instead of the 'consumer' package.
- To create a consumer object, import the necessary packages, provide the topic name, and the IP address for the consumer.
- Serialize the data into JSON format, load it, and decode it into JSON format.
- Loop through the consumer object and print the value.
- You can replicate the actions done in the terminal using code.
- Instead of manually inputting data, you can load data from an API or dataset in JSON format.
- The producer will keep producing and sending data in a loop, while the consumer will receive the data and put it in a target location.

Setting up Kafka and understanding producer and consumer functionalities
- Install Kafka on EC2 machine and connect with producer and consumer in real-time
- Simulate stock market data by selecting an existing dataset and sending it to the Kafka producer

Extracting stock market data into proper JSON format using Kafka.
- Assigning proper keys and values to the data using dictionaries.
- Using a loop to continuously extract real-time data and send it to Kafka.

running a Kafka server, starting and stopping the Zookeeper and consumer, and flushing data.
-  run the code and observe the data moving from one source to another.
- If the server breaks, simply restart the Zookeeper, Kafka server, and consumer to continue.

To access AWS secret and access key, go to IAM and add a user with programmatic access.
- Go to AWS Management Console and click on IAM
- Add a new user with programmatic access and administrative access
- Download the CSV file containing the access key and secret key
- Install AWS CLI if not already installed
Setup your AWS account on your local machine
- Copy and paste your access key ID and secret key ID from your CAC file
- Specify the default region based on your location

 Build a crawler to crawl the entire schema from the S3 file and enable querying with Athena
- The crawler will map the data source to glue tables
- Run the crawler on the selected S3 bucket and enable data analysis

Setting up IAM role for accessing AWS S3 bucket
- In order to access AWS S3 and upload data, an IAM role needs to be configured on the local machine.
- IAM role provides access to AWS Glue to write and read data from S3 bucket.

 Real-time data is being sent and uploaded onto S3 bucket.
- Data is being sent from the producer at each and every second.
- Consumer is receiving the data and uploading it onto the S3 bucket in real-time.
 Real-time data analysis using Kafka and Athena
- By querying data in real-time, the count keeps increasing every second
- Scanning the entire data takes time, querying specific data is faster

