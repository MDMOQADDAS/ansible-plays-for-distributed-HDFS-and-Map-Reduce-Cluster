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
============ 

Step 1 : Install below packages
------------------------------- 
1. pip3 install awscli <br/><br/>
2. pip3 install boto3 <br/><br/>
3. pip3 install boto <br/><br/>
Note -:) To download above package you must download python installer or update it.

Step 2 : Create an AWS IAM user and assign EC2 permission or you can assign the common "power user access", It releated to your AWS account Security so that how to manage its your choice.
-------------------------------

Step 3 : Now when you'll create and AWS IAM user at that time they will given ACCESS Key and Secrete Key copy them and run command
-------------------------------

![aws configure](https://github.com/MDMOQADDAS/Private-Images/blob/main/awsconfigure.png)

#### Note-:) Select the by default region here so that all the operation will in default region.

Step 4 : Create a AWS EC2 private key and put in same folder where all the files contents.
-------------------------------

Note -:) After copy the key in Linux ren below command to permit the key.
### Command-: chmod +400 key_name.pem
Step 5 : Create a security group in which allow
-------------------------------
1. All Trafic SSH<br/>
2. All Trafic Same Security Group id

![securitygrouppng](https://github.com/MDMOQADDAS/Private-Images/blob/main/securitygroup.png)

Step 6 : Go Inside folder "maininstance/vars/" and open "main.yml" file
-------------------------------

![maininstancevars](https://github.com/MDMOQADDAS/Private-Images/blob/main/maininstancevar.png)

key_name: hmrkeyap<br/>
security_group: sg_for_hmr_clusture<br/>
instance_type: t2.micro<br/>
image_id: ami-0bcf5425cdc1d8a85<br/>
instance_count: 1<br/>
region: ap-south-1<br/>
vpc_subnet_id: subnet-5847a533<br/>

### Note -:) Replace all the variable value, If you want to change tag then you have to change in other roles also.[Recommended not change tag name]

Step 7 : Go inside the folder "instances/vars" and open "main.yml"
-------------------------------

![instancespng](https://github.com/MDMOQADDAS/Private-Images/blob/main/instancepng.png)

Note -:) Here you can change  <br/>
key_name: hmrkeyap<br/>
security_group: sg_for_hmr_clusture<br/>
instance_type: t2.micro<br/>
hdfs_instance_count: 2 -: It means how many HDFS cluster Workder Node You want<br/>
mr_instance_count: 2 -: It means how many Map-Reduce Job Tracker you want<br/>
region: ap-south-1 <br/>
mr_client: 1  -: It means how many client instances you want to create<br/> 


Step 8 : Go inside the folder "hdfsmaster/vars/main.yml" 
-------------------------------

![hdfsmaster](https://github.com/MDMOQADDAS/Private-Images/blob/main/hdfsmaster.png)

Note -:) Here You can specify NameNode folder

Step 9 : Go inside the folder "hdfsslave/vars/main.yml"
-------------------------------

![hdfsslave](https://user-images.githubusercontent.com/69861558/117541882-a0a63580-b033-11eb-8f56-2e9c9f0303d7.png)

Note -:) Here you can specify DataNode folder


Step10  : Now Just run the one commond your entire cluster ready
-------------------------------

Command -: python3 auto.py (This commond should be run inside "hdfs-map-reduce-play" folder)


License
-------

BSD

Author Information
------------------

LinkedIn -: https://www.linkedin.com/in/mdmoqaddas
Email -: mdmoqaddas@gmail.com
