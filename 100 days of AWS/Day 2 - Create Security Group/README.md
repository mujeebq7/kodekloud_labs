## Create Security Group in AWS

### Description

The Nautilus DevOps team is strategizing the migration of a portion of their infrastructure to the AWS cloud. Recognizing the scale of this undertaking, they have opted to approach the migration in incremental steps rather than as a single massive transition. To achieve this, they have segmented large tasks into smaller, more manageable units. This granular approach enables the team to execute the migration in gradual phases, ensuring smoother implementation and minimizing disruption to ongoing operations. By breaking down the migration into smaller tasks, the Nautilus DevOps team can systematically progress through each stage, allowing for better control, risk mitigation, and optimization of resources throughout the migration process.

For this task, create a security group under default VPC with the following requirements:

Name of the security group is nautilus-sg.

The description must be Security group for Nautilus App Servers

Add the inbound rule of type HTTP, with port range of 80. Enter the source CIDR range of 0.0.0.0/0.

Add another inbound rule of type SSH, with port range of 22. Enter the source CIDR range of 0.0.0.0/0.



Use below given AWS Credentials: (You can run the showcreds command on aws-client host to retrieve these credentials)


Console URL - https://538701479232.signin.aws.amazon.com/console?region=us-east-1

Username - kk_labs_user_285609

Password - Bm6dzaLRi0mb


Note:
Create the resources only in us-east-1 region.

----

#### Step 1: Log into AWS console with the given credentials

<img width="1091" height="742" alt="image" src="https://github.com/user-attachments/assets/739429dc-8ddd-4958-81fc-1431775d7c1c" />

-----
#### Step 2: Create Security Group

Go to EC2 service and under that to security group and create one

<img width="3450" height="1726" alt="image" src="https://github.com/user-attachments/assets/96c56d11-7b44-4776-8fdb-82777f1a9069" />

Add the name of the security group, description and inbound rules as required in the task

----
Task Completed





