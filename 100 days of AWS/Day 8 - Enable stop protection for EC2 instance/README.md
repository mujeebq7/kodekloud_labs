### Enable stop protection for EC2 instance

#### Description

As part of the migration, there were some components added to the AWS account. Team created one of the EC2 instances where they need to make some changes now.

There is an EC2 instance named datacenter-ec2 under us-east-1 region, enable the stop protection for this instance.



Use below given AWS Credentials: (You can run the showcreds command on aws-client host to retrieve these credentials)

Console URL : https://389585776552.signin.aws.amazon.com/console?region=us-east-1

Username : kk_labs_user_356760

Password : 5DlJImFH!9f!

Note:

Create the resources only in us-east-1 region.

----

#### Step 1: Log in to the AWS console

<img width="2120" height="1516" alt="image" src="https://github.com/user-attachments/assets/c99ff9a4-dd64-44aa-861c-9972f9a4c50f" />


#### Step 2: Go to EC2 service

Stop the running EC2 instance 

<img width="2970" height="470" alt="image" src="https://github.com/user-attachments/assets/bfcf83cf-0e20-4dde-9c99-3cf6b5732525" />


#### Step 3 : Enable stop protection for the EC2 instance

Go to Actions > Instance Settings > Change stop protection > Enable

<img width="2974" height="1650" alt="image" src="https://github.com/user-attachments/assets/e21e5fe2-3f92-47e3-b1a6-3db4dcc018bd" />

----
Task Completed
