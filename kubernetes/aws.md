**IAM USER**

Once Account is setup go to Security And Identity  -> Identity And Access Management (IAM)

Create user with a programmatic key admin rights(Create a group and give admin rights)

Key generated will be something like this

Access ID - AKIAJTRHH3PBQILEXL7Q

Access Key - HV3YPSuPqVfy0s0YddLkEZE6RON2E1p4PAxzoAy1

In command line type 

aws configure (Enter ID and key)

ls -ahl ~/.aws/ (To see credentials files and where passwords are setup)

**GET LOGIN FOR AWS REPOSITORY**

aws ecr get-login --no-include-email --region eu-west-1 (This will give you the command for the docker login)


**S3 BUCKET (Can create using aws command line tool)**

Create Bucket

 aws s3api create-bucket --bucket gfox-test-automation --region eu-west-1 --create-bucket-configuration Loc ationConstraint=eu-west-1
 
Delete Bucket
 
api delete-bucket --bucket gfox-test-automation --region eu-west-1 

Similar to Google Drive

Create new bucket e.g kops-state-1985 (End with unique characters so it is unique fo the region)

http://www.cloudping.info/ (See what the closest AWS region is to you)

**DNS (Can create using aws command line tool)**

If you are using Kops 1.6.2 or later, then DNS configuration is optional. Instead, a gossip-based cluster can be easily created. The only requirement to trigger this is to have the cluster name end with .k8s.local. 

**SSH Key**

Create ssh key for accessing your cluster






