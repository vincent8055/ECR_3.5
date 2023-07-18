# ECR_3.5 Assignment submission

step-by-step how to create an image until it will be deployed to AWS ECR

## Step 1: Create a AWS ECR Private Repository


![Screenshot 2023-07-18 at 9 32 51 PM](https://github.com/vincent8055/ECR_3.5/assets/127754761/352f6d3d-6094-404e-ae48-57023139ebc7)


## Step 2 Setup AWS & Authentication/ Authorization to ECR
1. Run 'aws configure' on terminal to configure the access and secret keys with at least AmazonEC2ContainerRegistryPowerUser permissions

2. For Public Repositories, permission needed: `ecr:GetAuthorizationToken`
Command:

`aws ecr get-login-password --region ap-southeast-1 | docker login --username AWS --password-stdin <aws account number>.dkr.ecr.ap-southeast-1.amazonaws.com
IAM Policy: AmazonEC2ContainerRegistryPowerUser (AWS Managed Policy)`

## Step 3 Build and push Image to Private ECR

1. Command to build an image `docker build -t <image_name>:<image_tag>`
2. Command to tag an image `docker tag <image_name>:<image_tag> <repository_URL>:<image_tag>`
3. Command to push image `docker push <account no>.dkr.ecr.ap-southeast-1.amazonaws.com/<repository_name>:latest`

## Verify image is successfully pushed in ECR

Image is sucessfully pushed into ECR


![Screenshot 2023-07-18 at 10 17 08 PM](https://github.com/vincent8055/ECR_3.5/assets/127754761/08a01e85-fd01-4412-ac93-88b1149c3162)

 ## The end  
