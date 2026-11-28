### Enable Termination Protection for EC2 Instance

#### Description

As part of the migration, there were some components created under the AWS account. The Nautilus DevOps team created one EC2 instance where they forgot to enable the termination protection which is needed for this instance.

An instance named datacenter-ec2 already exists in us-east-1 region. Enable termination protection for the same.



Use below given AWS Credentials: (You can run the showcreds command on aws-client host to retrieve these credentials)

Console URL	: https://906292119996.signin.aws.amazon.com/console?region=us-east-1

Username : kk_labs_user_898751

Password : S@@s!@b0cML!

----

#### Step 1: Log in to the AWS console

<img width="2120" height="1516" alt="image" src="https://github.com/user-attachments/assets/c99ff9a4-dd64-44aa-861c-9972f9a4c50f" />


#### Step 2: Go to EC2 service

Stop the running EC2 instance 

<img width="2970" height="470" alt="image" src="https://github.com/user-attachments/assets/bfcf83cf-0e20-4dde-9c99-3cf6b5732525" />


#### Step 3 : Enable stop protection for the EC2 instance

Go to Actions > Instance Settings > Change termination protection > Enable

<img width="2974" height="1670" alt="image" src="https://github.com/user-attachments/assets/a2e87fec-e7dd-41e4-a15b-fedd934204b1" />

----
Task Completed
