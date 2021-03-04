## Preparing the AWS services

1- create an IAM user `lambdas-upload` with `programmatic access` and AdministratorAcess 

<img width="905" alt="Screen Shot 2021-03-04 at 10 19 07 AM" src="https://user-images.githubusercontent.com/1462878/110007171-a734cb80-7cd7-11eb-80c6-911b223c6545.png">

2- create a bucket in us-east-1 with name `serverless-video-upload`

<img width="1068" alt="Screen Shot 2021-03-04 at 10 24 01 AM" src="https://user-images.githubusercontent.com/1462878/110007215-b156ca00-7cd7-11eb-9dca-6c3805f2daa4.png">

3- create an IAM role `transcode-video` for interacting with AWS `ElementalsMediaConvert` and `S3` with 2 policies:
  - `AWSLambdaExecute`
  - `AWSElementalsMediaConvertFullAccess`

<img width="1084" alt="Screen Shot 2021-03-04 at 10 26 35 AM" src="https://user-images.githubusercontent.com/1462878/110007324-c6335d80-7cd7-11eb-9191-5df271b81471.png">

4- create a `MediaConvert` endpoint. It'll be used using `AWSElementalsMediaConvert` to convert uploaded video files stored in a s3 bucket from 1 format to another and save them in another s3. 

<img width="676" alt="Screen Shot 2021-03-04 at 10 29 58 AM" src="https://user-images.githubusercontent.com/1462878/110007346-cc293e80-7cd7-11eb-88c4-b3db8b9a85f1.png">


5- create an IAM role for the `MediaConvert` service which automatically adds 2 policies `S3 Full Access` and `API Gateway Full Invoke`

<img width="1042" alt="Screen Shot 2021-03-04 at 10 38 48 AM" src="https://user-images.githubusercontent.com/1462878/110007369-d1868900-7cd7-11eb-843e-d1e811293306.png">
