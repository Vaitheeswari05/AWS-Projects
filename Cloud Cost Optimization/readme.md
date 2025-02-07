<h1>Automated AWS Cost Optimization: Detecting and Deleting stale resources Snapshots</h1>
<h2>This project aims to optimize AWS cloud costs by automating the detection and removal of stale EBS snapshots. 
  
Motto of the Project:
AWS resources, particularly snapshots, can accumulate over time and incur unnecessary costs if not actively managed. By implementing automated scripts and monitoring tools, this project identifies such stale resources, flags them, and safely deletes unnecessary snapshots, effectively reducing overall cloud expenses.</h2>

<h1>Key Features</h1>

<h2>Automated Snapshot Identification: Detects unused or outdated snapshots across your AWS environment.
Cost Savings: Helps reduce AWS storage costs by cleaning up unneeded snapshots.

Scheduling & Alerts: Allows scheduled cleanup and notifications for resource management.

Scalable & Flexible: Designed to work across different AWS services and can be customized to specific use cases.</h2>

<h1>The list of services used in this project</h1>
<h2>EC2, EBS, Lambda, Cloud Watch, EventBridge Management, IAM </h2> 

<h1>The End to End steps</h1>
<h2>1. Create an EC2 Instance and Take a Snapshot of its EBS Volume</h2>
        <h3>Launch an EC2 instance and attach an EBS volume to it.</h3>
        <h3>Create snapshots of the EBS volumes attached to the EC2 instance to backup data.</h3>

<h2>2. Create a Lambda Function and Add the Python Code</h2>
        <h3>Create an AWS Lambda function within the Lambda console.</h3>
        <h3>Write or paste the Python code in the function’s inline editor to handle the detection and deletion of stale snapshots.</h3>
        ![Lambda_function](https://github.com/Vaitheeswari05/AWS-Projects/blob/master/Cloud%20Cost%20Optimization/Lambda%20function.jpg)

<h2>3. Deploy the Lambda Function and Attach Necessary Policies to the IAM Role</h2>
        <h3>After pasting the Python code into the Lambda function, deploy the code.</h3>
        <h3>Attach an IAM policy to the Lambda's execution role that allows it to list EC2 instances, EBS volumes, and snapshots.</h3>
        ![IAM_role_for_lambda](https://github.com/Vaitheeswari05/AWS-Projects/blob/master/Cloud%20Cost%20Optimization/create%20policy%20for%20that%20role.jpg)

<h2>4. Test the Lambda Function for Output
        <h3>Once the policy is attached, manually test the Lambda function in the AWS Lambda console to ensure it is executing correctly and returning the expected output.</h3>
</h2>
<h2>5. Create a CloudWatch Rule to Invoke Lambda on a Schedule</h2>
        <h3>Create a CloudWatch Event Rule that triggers the Lambda function. Set the cron expression to invoke the function every Monday at 12:00 AM.</h3>
        <h3>Attach the IAM role that has the necessary permissions to invoke the Lambda function in the EventBridge Rule.</h3>
![cloudwatch_Eventbridge](https://github.com/Vaitheeswari05/AWS-Projects/blob/8561ff05c2dd8575116e42a72a036f7610c52d06/Cloud%20Cost%20Optimization/schedule%20the%20job%20using%20cloud%20watch_1.jpg)
