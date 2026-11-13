### Enable versioning for S3 bucket

#### Description

Data protection and recovery are fundamental aspects of data management. It's essential to have systems in place to ensure that data can be recovered in case of accidental deletion or corruption. The DevOps team has received a requirement for implementing such measures for one of the S3 buckets they are managing.

The s3 bucket name is nautilus-s3-289694350, enable versioning for this bucket.



Use below given AWS Credentials: (You can run the showcreds command on aws-client host to retrieve these credentials)

Console URL	https://644346842496.signin.aws.amazon.com/console?region=us-east-1

Username	kk_labs_user_907701

Password	i^bVaJpVg3%x

-----

#### Step 1 : Log into the AWS console

<img width="3426" height="1944" alt="image" src="https://github.com/user-attachments/assets/89fbac02-2a58-484c-9220-b0617fd09498" />


#### Step 2: Go to S3 service

<img width="1940" height="704" alt="image" src="https://github.com/user-attachments/assets/2be32303-c94e-42b7-869b-87a7d071de9e" />

#### Step 3: Enable Bucket Versioning

Inside the bucket, go to properties option and enable bucket versioning

<img width="2884" height="798" alt="image" src="https://github.com/user-attachments/assets/6c5b9a06-0ed0-4a02-924b-f8acd093eb71" />


#### Step 4 : Verify if the bucket version is enabled

<img width="2868" height="1356" alt="image" src="https://github.com/user-attachments/assets/628d999b-c1a1-41e1-8162-6609dd532192" />


----
Task Completed

