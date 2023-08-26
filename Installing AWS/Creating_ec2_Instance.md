# Here are the steps on how to create a free tier EC2 instance on an AWS free account:

- Go to the AWS Management Console and sign in to your account.

   * In the Services menu, select Compute, then EC2.

- In the Launch Instance wizard, select Free Tier only in the Filter by section.

- Choose an AMI (Amazon Machine Image) that is free tier eligible. For example, you can choose the Amazon Linux 2 AMI.

- Select the instance type. For a free tier instance, you can choose the t2.micro instance type.

- Configure the instance details. For example, you can specify the number of instances to launch and the VPC and subnet to launch the instances in.

- Add storage. For a free tier instance, you can add a 1 GB EBS volume.

- Add tags. Tags are used to identify and organize your resources. You can add tags to your instance here.

- Review the instance details and click Launch.

- In the Configure Instance Details dialog, select the Key Pair that you want to use to connect to your instance. If you don't have a key pair, you can create one.

   * Click Launch Instances.

- Your EC2 instance will be launched and will be ready to use in a few minutes. You can find the public IP address of your instance in the Instances page. You can use this IP address to connect to your instance using SSH.

# Here are some additional things to keep in mind:

- The free tier limits for EC2 instances are 750 hours per month for t2.micro instances.

- You can create a maximum of 2 EC2 instances per month under the free tier.

- You can create EC2 instances in any region that is available in the AWS Free Tier.




