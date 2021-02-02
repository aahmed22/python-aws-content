# Python Ops for Amazon Web Services using Boto3
This repo contains python scripts for executing operations on AWS

## S3 Operations 
```python
# Objective: Print out all of the S3 bucket names from your AWS account. 
import boto3

session = boto3.Session(profile_name='Development')
s3 = session.client('s3')

def viewListBuckets():
    response = s3.list_buckets()['Buckets']
    for bucket in response:
        print(bucket['Name'])
    
    
print('Please provide a print out of all buckets in our AWS account..\n')
viewListBuckets()
```

```python
import boto3

session = boto3.Session(profile_name='Development')

s3 = session.client('s3')

def bucketCreation(b_name):
    response = s3.create_bucket(
        Bucket = b_name
    )

my_new_bucket = input("Please enter a bucket name for creation: ")
bucketCreation(my_new_bucket)
```

```python
import boto3

session = boto3.Session(profile_name='Development')

s3 = session.client('s3')

def bucketDeletion(b_name):
    response = s3.delete_bucket( Bucket = b_name )
    print()
    print(response)

my_bucket = input("Please enter a bucket name for creation: ")
bucketDeletion(my_bucket)
print()
```
