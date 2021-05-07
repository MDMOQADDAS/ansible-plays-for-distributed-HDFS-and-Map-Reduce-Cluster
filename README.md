Create Distributed Hadoop Cluster and Map Reduce
=========

This play is very mature to create HDFS and Map Reduce Cluster and the interesting thing here is to it automatically connect with master to worker or Job Tracke to Task Tracker on the fly.

Architecture
============
Step 1 : First it lauch one instance over AWS <br/>
Step 2 : Dynamically remote login and download Hadoop and JDK rpm Package
step 3 : Create AMI Image of above instance
step 4 : Now launch cluster instances as you required but all the image lauch by own created AMI Image
step 5 : Configure one of them as a HDFS Master Node (No need to tell it automatically fetch by using tags)
step 6 : Configure some instance as as HDFS Slave Node (No need to tell it automatically fetch by using tags)
step 7 : Configure one of them as Job Tracker (No need to tell it automatically fetch by using tags)
step 8 : Configure some of them as a Task Tracker (No need to tell it automatically fetch by using tags)
step 9 : Configure one of them as a entire cluster client (No need to tell it automatically fetch by using tags)

Now your cluster ready


![architecture](https://github.com/MDMOQADDAS/Private-Images/blob/main/j.png)

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
