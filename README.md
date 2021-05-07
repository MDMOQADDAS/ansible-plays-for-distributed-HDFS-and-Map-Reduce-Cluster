Create Distributed Hadoop Cluster and Map Reduce
=========

This play is very mature to create HDFS and Map Reduce Cluster and the interesting thing here is to it automatically connect with master to worker or Job Tracke to Task Tracker on the fly.

Architecture
============
#### Step 1 : First it launch one instance over AWS <br/><br/>
#### Step 2 : Dynamically remote login and download Hadoop and JDK rpm Package<br/><br/>
#### step 3 : Create AMI Image of above instance<br/><br/>
#### step 4 : Now launch cluster instances as you required but all the image lauch by own created AMI Image<br/><br/>
#### step 5 : Configure one of them as a HDFS Master Node (No need to tell it automatically fetch by using tags)<br/><br/>
#### step 6 : Configure some instance as as HDFS Slave Node (No need to tell it automatically fetch by using tags)<br/><br/>
#### step 7 : Configure one of them as Job Tracker (No need to tell it automatically fetch by using tags)<br/><br/>
#### step 8 : Configure some of them as a Task Tracker (No need to tell it automatically fetch by using tags)<br/><br/>
#### step 9 : Configure one of them as a entire cluster client (No need to tell it automatically fetch by using tags)<br/><br/>

Welcome Your cluster ready!!

Requirements
------------

#### Step 1 : Install below package
1. pip3 install awscli <br/><br/>
2. pip3 install boto3 <br/><br/>
3. pip3 install boto <br/><br/>
Note -:) To download above package you must download python installer or update it.

#### Step 2 : Create an AWS IAM user and assign EC2 permission or you can assign the common "power user access", It releated to your AWS account Security so that how to manage its your choice.

#### step 3 : Now when you'll create and AWS IAM user at that time they will given ACCESS Key and Secrete Key copy them and run command

![aws configure](https://github.com/MDMOQADDAS/Private-Images/blob/main/awsconfigure.png)

#### Note-:) Select the by default region here so that all the operation will in default region.

#### step 4 : Now Just run the one commond your entire cluster ready
Command -: python3 auto.py (This commond should be run inside "hdfs-map-reduce-play" folder)

![]()
License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
