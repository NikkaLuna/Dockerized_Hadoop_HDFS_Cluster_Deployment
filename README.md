# Dockerized Hadoop HDFS Cluster Deployment

**Overview**

This project showcases the deployment of a fully functional Hadoop cluster using Docker, with a focus on the Hadoop Distributed File System (HDFS). The cluster encompasses key components like the Namenode, Datanode, Node Manager, Resource Manager, and Hadoop History Server. By employing Docker, this setup provides a simplified and scalable environment for big data processing tasks.

**Key Features**

* **Dockerized Deployment:** Leverages Docker containers for streamlined setup and management of the Hadoop cluster.
* **HDFS Focus:**  Emphasis on the Hadoop Distributed File System, enabling efficient storage and management of large datasets.
* **Essential Components:** Includes core Hadoop components: 
    * Namenode 
    * Datanode
    * Node Manager
    * Resource Manager
    * Hadoop History Server

* **Scalability:** The use of Docker facilitates scaling the cluster by adding or removing nodes as needed.

* **Big Data Processing:** Provides a suitable environment for various big data processing tasks.

**Getting Started**

## Prerequisites

Ensure you have the following installed on your machine:

- **Docker**
- **Docker Compose**
- **Git**
- **Hadoop 3.3.6**: Download the Hadoop 3.3.6 binary from the [official Apache Hadoop website](https://hadoop.apache.org/releases.html).
  - After downloading, extract the archive using the following command:

    ```bash
    tar -xzf hadoop-3.3.6.tar.gz
    ```


- Ensure that the extracted files are placed in the appropriate directory as per the instructions.

* **Setup and Deployment**

Follow these steps to set up and deploy the Hadoop cluster:

## Clone the Repository

```bash 
git clone https://github.com/ibm-developer-skills-network/ooxwv-docker_hadoop.git
```

Navigate to the Project Directory
```

```bash 
cd ooxwv-docker_hadoop
```

Build and Start the Docker Containers

```bash 
docker-compose up -d
```
This command uses Docker Compose to build and start all the services defined in the configuration file. You will see that all five containers are created and started.

## Access the Namenode

```bash 
docker exec -it namenode /bin/bash
```

This command mounts the Namenode as a drive on Bash, allowing you to interact with HDFS.

* **Creating and Managing Files in HDFS**

## Create a Directory in HDFS

```bash 
hdfs dfs -mkdir -p /user/root/input
```

Copy Configuration Files into HDFS

```bash 
hdfs dfs -put $HADOOP_HOME/etc/hadoop/*.xml /user/root/input
```

Download and Copy a Sample Data File

```bash 
curl https://raw.githubusercontent.com/ibm-developer-skills-network/ooxwv-docker_hadoop/master/SampleMapReduce.txt --output data.txt
hdfs dfs -put data.txt /user/root/
```

## Verify the File in HDFS

```bash 
hdfs dfs -cat /user/root/data.txt
```

* **Viewing the HDFS GUI**

1. Launch the HDFS Web Interface

2. Access the GUI by Entering the Port Number 9870 in Your Browser

Open your web browser.

If you're running the cluster locally, type the following URL into the address bar:

```bash
http://localhost:9870
```

If you're running the cluster on a remote server, replace localhost with the IP address of your server:

```bash
http://<your-server-ip>:9870

```
Press Enter. You should see the Hadoop NameNode UI, which provides an overview of the HDFS and its status.

3. Browse the File System

- Once you’re on the NameNode UI, look for the "Utilities" section in the left-hand menu or the top navigation bar.
- Click on Utilities -> Browse the file system.
- This will allow you to navigate through the directories and files that you’ve created in HDFS.

4. Inspect File Details

- Navigate through the directories (e.g., /user/root/) to find the files you’ve uploaded to HDFS.
- Click on a file to view detailed information such as its size, block ID, and replication factor.

5. Download or View File Contents

- To view the content of a file, you can use the "View" option available in the UI.
- You can also download the file to your local system if needed.

* **Project Summary**

This project involves the successfuly deployment of a Hadoop cluster using Docker, created and managed data in HDFS, and the HDFS was then accessed through a GUI. This project serves as a foundational step in understanding big data technologies and containerized deployments. 