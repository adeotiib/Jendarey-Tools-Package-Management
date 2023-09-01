# Here are the steps on how to set up a free AWS Free Tier account:

```bash
https://aws.amazon.com/
```

- Click on the Create an AWS Account button.

- Enter your name, email address, and password.

- Select your country or region.

- Read and agree to the AWS terms of service and privacy policy.

- Click on the Create Account button.

- You will receive an email with a confirmation link. Click on the link to verify your account.

- Once your account is verified, you can start using the AWS Free Tier.

# Here are some additional things to keep in mind when setting up a free AWS Free Tier account:

- You will need a credit or debit card to create an AWS account. However, you will not be charged for any usage within the Free Tier limits.

- The AWS Free Tier is available to all types of customers, including students, entrepreneurs, small businesses, and Fortune 500 companies.

- The AWS Free Tier offers a variety of services, including computing, storage, networking, databases, analytics, machine learning, and artificial intelligence.

- You can find more information about the AWS Free Tier on the AWS website: https://aws.amazon.com/free/

# Set Billing Alarm
To set up a billing alarm in AWS, you can follow these steps:

- From the user drop-down menu at the top right side of your AWS console.
- Select AWS Billing Console.
- Click Billing Preferences. Enable invoice delivery Preferences and Alert Preferences (Add your email address), and add CloudWatch Billing alerts
- Save and Click on the AWS logo on the Console.
- Search for CloudWatch from the search bar.
- Click on CloudWatch - Ensure you are in North Virgina.
- Click Alarms.
- Click on all alarms 
- Click Create alarm.
- Select Billing as the Metric type.
- Select the Metric that you want to monitor. - Select Billing, select Total Estimated Charge, select Currency USD, Select Matric, and Enter the Threshold value.
- Next, Select an SNS topic - or create an SNS topic, - topic name - ChargesMonitoringTeam.
- Add an email address and create a topic.
- Next, Name your AWSBillingAlert
- Next, click Create Alarm.
- Click Create alarm.
- Check email and confirm Subscription
- Go back to AWS and refresh your CloudWatch.
  
# Here is a more detailed explanation of each step:

- Metric type: This is the type of metric that you want to monitor. For example, you could monitor your monthly AWS costs, your daily EC2 usage, or your hourly EBS bandwidth.
- Metric: This is the specific metric that you want to monitor. For example, you could monitor the Cost metric for your AWS account, or the CPU utilization metric for your EC2 instances.
- Statistic: This is the statistical measure that you want to use to compare the metric value to the threshold. For example, you could use the Average statistic to compare the average monthly AWS costs to the threshold, or the Maximum statistic to compare the maximum daily EC2 usage to the threshold.
- Threshold: This is the value that you want to compare the metric value to. For example, you could set the threshold to $1000 to be notified when your monthly AWS costs exceed $1000.
- Comparison operator: This is the operator that you want to use to compare the metric value to the threshold. For example, you could use the greater than operator to be notified when your monthly AWS costs are greater than $1000.
- Period: This is the length of time that AWS will use to calculate the metric value. For example, you could set the period to 1 month to be notified when your monthly AWS costs exceed $1000.
- Evaluation period: This is the number of periods that AWS will use to evaluate the alarm. For example, you could set the evaluation period to 1 to be notified when your monthly AWS costs exceed $1000 in any given month.
- Alarm actions: These are the actions that AWS will take when the alarm is triggered. For example, you could send an email notification, or create a new CloudWatch event.
- Once you have created the billing alarm, AWS will start monitoring the metric value. If the metric value exceeds the threshold, AWS will trigger the alarm and take the specified actions.

# Here are some additional things to keep in mind when setting up a billing alarm:

- You can create multiple billing alarms to monitor different metrics.
- You can also create billing alarms for different accounts or regions.
- You can use billing alarms to track your AWS costs and usage and to identify potential problems.
