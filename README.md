## ADOP Instance cloudformation template
This project defines a basic aws cloudformation template configuration for adop-c instance:
* Define username and password for adop stack
* Choose what is the vpc and network
* The instance AMI is centos 7 image and by default type is t2.xlarge
* The user data script is using [adop-ansible](https://github.com/RobeDevOps/adop-ansible) to:
    1. configure docker repositories
    2. Install common components: git, lvm2, docker, docker-compose
    3. Configure docker group and user
    4. Pull the adop-docker-compose project. 
    5. See more details in adop-ansible project link.
    6. Once everything is installed, adop is started and waiting from jenkins to be ready.
## TO-DO
1. Allow more regions. ( so far it is deployed only on us-east-1 )
2. Allow to choose ec2 instances type ( so far is t2.xlarge )
3. Allow to define more storage capacity ( by default 50 gb abd gp2 type )