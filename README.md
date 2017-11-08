# Big-data-project
The objective was to build a business application by providing an API that resolves Name Node issues by effectively storing files of all sizes and ensure protection of data stored in the system. The main focus of the design is to handle various file sizes of the encrypted data, accessing patterns of the encrypted metadata and retrieving patterns of the encrypted data. It is designed using Hadoop and HBase. For comparison purposes, Hadoop Distributed File System (HDFS), which is a storage system of Hadoop, is used as a general big data framework to store the encrypted data. The evaluation parameters include the memory consumption and the retrieval time of the proposed system.

This project made use of the following:
1. Cloudera platform
2. Eclipse
3. Apache Tomcat server
4. MySQL
5. Java
6. Oracle VirtualBox to run cloudera 

The repository consists of a WAR file. 

1. Download the WAR file
2. Open Eclipse and start a new project
3. Import the WAR file
4. Setup the Tomcat server in eclipse and start the server
5. Copy the local URL generated
6. Paste in a browser of your choice
7. Setup MySQL java connector

Data Write Operation
====================
Step 1: Read username and password
Step 2: Authenticate
Step 3: If Authentication failed
		Goto Step 1
	else 
		Goto Step 4
Step 4: Read the patients personal data and health data
Step 5: Perform encryption operation on patients data using RSA Algorithm 
Step 6: Store the decryption keys in HBase
Step 7: Compute the total size of the encrypted patients data
Step 8: If the total size of encrypted patients data > Blocks size
		Goto Step 9
	else 
		Goto Step 10
Step 9: Store the encrypted patients data in HDFS
	Store the pointer in HBase
	Goto step 11
Step 10: Store the encrypted patients data in HBase
  	 Store the pointer in HBase
	 Goto step 11
Step 11: Acknowledge the user by sending an email


Data Read Operation
===================
Step 1: Read username and password
Step 2: Authenticate
Step 3: If Authentication failed
		Goto Step 1
	else 
		Goto Step 4
Step 4: Read the patients ID from the user
Step 5: Read the pointer for this patients ID from HBase
Step 6: If the pointer says HBase
		Goto Step 7
	else 
		Goto Step 8
Step 7: Read the encrypted patients data from HBase
	Goto step 9
Step 8: Read the encrypted patients data from HDFS
	Goto step 9
Step 9: Read the decryption keys from HBase
Step 10: Perform decryption operation on the patients data
Step 11: Acknowledge the user

