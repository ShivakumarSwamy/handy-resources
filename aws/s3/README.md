# simple storage service (s3)

----
- [recursively copy from s3 bucket to local path](#recursively-copy-from-s3-bucket-to-local-path)
- [recursively copy from s3 bucket folder to local path](#recursively-copy-from-s3-bucket-folder-to-local-path)
- [recursively copy from local path to s3 bucket folder](#recursively-copy-from-local-path-to-s3-bucket-folder)
- [recursively remove a folder in s3 bucket](#recursively-remove-a-folder-in-s3-bucket)
----

## recursively copy from s3 bucket to local path
```shell
# example YOUR_S3_BUCKET_URI value s3://bucket_name
aws s3 sync <YOUR_S3_BUCKET_URI> <YOUR_COMPUTER_LOCAL_PATH>

# dry run only
aws s3 sync <YOUR_S3_BUCKET_URI> <YOUR_COMPUTER_LOCAL_PATH> --dryrun

# with region
aws s3 sync <YOUR_S3_BUCKET_URI> <YOUR_COMPUTER_LOCAL_PATH> --dryrun --region us-east-1
```

## recursively copy from s3 bucket folder to local path
```shell
# example YOUR_S3_BUCKET_URI/FOLDER_IN_BUCKET value s3://bucket_name/folder_name
aws s3 sync <YOUR_S3_BUCKET_URI>/<FOLDER_IN_BUCKET> <YOUR_COMPUTER_LOCAL_PATH>
```

## recursively copy from local path to s3 bucket folder
```shell
aws s3 sync <YOUR_COMPUTER_LOCAL_PATH> <YOUR_S3_BUCKET_URI>/<FOLDER_IN_BUCKET> 
```

## recursively remove a folder in s3 bucket
```shell
# example YOUR_S3_BUCKET_URI/FOLDER_IN_BUCKET value s3://bucket_name/folder_name
aws s3 rm <YOUR_S3_BUCKET_URI>/<FOLDER_IN_BUCKET> --recursive

# dry run only
aws s3 rm <YOUR_S3_BUCKET_URI>/<FOLDER_IN_BUCKET> --recursive --dryrun
```
