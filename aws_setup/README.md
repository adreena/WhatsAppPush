## Preparing the AWS services

1- create an IAM user `lambdas-upload` with `programmatic access` and AdministratorAcess 


2- create a bucket in us-east-1 with name `serverless-video-upload`

3- create an IAM role ``transcode-video` for interacting with AWS `ElementalsMediaConvert` and `S3` with 2 policies:
  - `AWSLambdaExecute`
  - `AWSElementalsMediaConvertFullAccess`

4- create a `MediaConvert` endpoint. It'll be used using `AWSElementalsMediaConvert` to convert uploaded video files stored in a s3 bucket from 1 format to another and save them in another s3. 

5- create an IAM role for the `MediaConvert` service which automatically adds 2 policies `S3 Full Access` and `API Gateway Full Invoke`
