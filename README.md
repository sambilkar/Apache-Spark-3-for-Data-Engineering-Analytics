# Apache-Spark-3-for-Data-Engineering-Analytics
HOW TO INSTALL PYSPARK ON UBUNTU
Introduction to Spark:
1.	PySpark is a library that can be used to run python application using Apache Spark Capability in other words PySpark is Python API for Spark.
2.	Spark is not programming language.
a.	write spark applications using Java, Scala, R and Python
b.	PySpark allows you to write python based data processing applications that execute on a distributed cluster in parallel

Apache Spark is an analytical processing engine for large scale powerful distributed data processing and also machine learning applications.

Basic set- up for PySpark on Ubuntu for distributed Machine Learning.
Prerequisites:
1.	An Ubuntu System 
2.	Access to a terminal on command line
3.	A user with sudo or root permission
Required Packages: 
Step1: Start

Step 2: check the python and python3 correct version installed or not on your local machine. Before installation of python you need to check the pip3 installed or not on your local machine to check run following command
pip3 install python
The program ‘pip3’ is currently not installed. You can installed it by typing:
sudo apt install python3-pip
After the successfully installation of pip now you need to installed Jupyter-notebook. So using below command you can installed Jupyter notebook on your local machine
pip3 install Jupyter
Once done if make it warning about pip3 is using older version don’t worry about that, if you want to install latest version of pip or upgrade use below command
You are using pip version 8.1.1, however version 9.0.1 is available
You should consider upgrading via the ‘pip install –upgrade pip’ command
To check Jupyter notebook is correctly working or not just type on terminal,
Jupyter-notebook, and hit enter
It’s navigate to the browser and open Jupyter-notebook. If by default it is not navigate to Browser just copy the address and paste it on browser and hit enter
http://localhost:8888/?token=6dc947d5c5a911fa30e72af7a73bc92837b89b01f4926c5f

Step 3: Make sure that you have correct version of java installed on your local machine
If you don’t have java on you local machine, run the following command on your terminal
	sudo apt-get update
sudo apt-get install openjdk-8-jdk 	or 	
sudo apt-get install default-jre
After installation, if you type java-version in the terminal you will get.
openjdk version "1.8.0_212"
OpenJDK Runtime Environment (build 1.8.0_212-8u212-b03-0ubuntu1.18.04.1-b03)
OpenJDK 64-Bit Server VM (build 25.212-b03, mixed mode)

Step 4: Installing Scala
Go to the directory where spark zip file was downloaded and run the command to install it.
sudo apt-get install scala
After installation, if you type Scala-version in the terminal you will get version,
scala –version
Step 5: now need to install library called py4j for that just type on terminal,
	pip3 install py4j

Step 6: Download Spark from https://spark.apache.org/downloads.html 
or download directly using the below link 
https://downloads.apache.org/spark/spark-3.1.2/spark-3.1.2-bin-hadoop3.2.tgz
Remember the directory name where you download Apache Spark. Be default it will store in download folder of system.

Step 7: Now extract the tar file using following command before extract navigate you terminal to download folder where you have download Apache Spark Versions.
cd ~/Downloads
Check downloaded spark version are available or not in downloads directory, use for that 
ls –al
tar zxvf spark-3.1.1-bin-hadoop2.7.tgz 
and check again using ls –al and exit from downloads directory.
Now move directory spark-3.1.1-bin-hadoop2.7 from download to home directory. 
Note: If your spark file is different version correct the name accordingly.

Step 8: configure environment variables for spark 
Before starting the master server, you need to configure environment variable. There are some spark home path need to add to the user profile.
Use echo command to add these lines

export SPARK_HOME=’home/ubuntu/spark-3.1.1-bin-hadoop2.7’
export PATH=$SPARK_HOME:$PATH
export PYTHONPATH=$SPARK_HOME/python:$PYTHONPATH
export PYSPARK_DRIVER_PYTHON=”jupyter”
export PYSPARK_DRIVER_PYTHON_OPTS=”notebook”
export PYSPARK_PYTHON=python3

Step 9: Set Permission to avoid errors
1. In order to fix any possible permission error you may get using the Jupyter notebook under the spark folder, set permission using following commands
sudo chmod 777 spark-3.1.1-bin-hadoop2.7
Now change directory from,
cd spark-3.1.1-bin-hadoop2.7/
cd python/
Now just type python3, now check python3 working correctly or not just hit following command 
import pyspark
quit()


2. Now change directory 
ubutu@ubuntu:~$ cd spark-3.1.1-bin-hadoop2.7/
ubutu@ubuntu:~/spark-3.1.1-bin-hadoop2.7$ sudo chmod 777 python 

3. Now navigate to directory from cd spark-3.1.1-bin-hadoop2.7/ to  
ubutu@ubuntu:~/spark-3.1.1-bin-hadoop2.7$ cd python/
ubutu@ubuntu:~/spark-3.1.1-bin-hadoop2.7$ sudo chmod 777 pyspark
ubutu@ubuntu:~/spark-3.1.1-bin-hadoop2.7$ Jupyter-notebook

Conclusion:
I hope the article will help you in installing PySpark. In Today’s world’s, Spark has very important tool for performing distributed machine learning. Setting up Spark might be first thing to do followed by learning spark data frames and then using it in any project.
