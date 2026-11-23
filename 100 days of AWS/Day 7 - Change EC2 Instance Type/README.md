### Change EC2 Instance Type

#### Description

During the migration process, the Nautilus DevOps team created several EC2 instances in different regions. They are currently in the process of identifying the correct resources and utilization and are making continuous changes to ensure optimal resource utilization. Recently, they discovered that one of the EC2 instances was underutilized, prompting them to decide to change the instance type. Please make sure the Status check is completed (if its still in Initializing state) before making any changes to the instance.

1) Change the instance type from t2.micro to t2.nano for nautilus-ec2 instance.

2) Make sure the ec2 instance nautilus-ec2 is in running state after the change.



Use below given AWS Credentials: (You can run the showcreds command on aws-client host to retrieve these credentials)

Console URL : https://415500486906.signin.aws.amazon.com/console?region=us-east-1

Username : kk_labs_user_836674

Password : ekuqh6HQk@RW

Note:

Create the resources only in us-east-1 region.

----
#### Step 1: Log in to the AWS console

<img width="2120" height="1516" alt="image" src="https://github.com/user-attachments/assets/c99ff9a4-dd64-44aa-861c-9972f9a4c50f" />


#### Step 2: Go to EC2 service

Stop the running instance > Go to Actions > Instance Setting > Under Instance Configuration > Change Instance Type

<img width="3448" height="1934" alt="image" src="https://github.com/user-attachments/assets/334223e1-b0e0-4de0-b77c-0850efb917be" />


#### Step 3: Change the Instance Type

<img width="2296" height="1798" alt="image" src="https://github.com/user-attachments/assets/9d3356a7-932c-474f-bbfe-68083db50c67" />


#### Step 4 : Start the EC2 instance

-----
Task Completed

