<h1>Amazon DynamoDB Streams to trigger Amazon SNS messaging</h1>

Additional Information

- Language: English
- Runtime: AWS
- Level: 200
- Framework: Cloudformation
- Type: Workshop
- Author: [Khush Patel](https://www.linkedin.com/in/khushpatel11/)

<br>

**NOTE** - Edit the CloudFormation template and replace **Endpoint: abcd@gmail.com**, with your own personal email.

This blog/repository will teach you how to create a trigger for Amazon SNS messaging every time an item is created in an Amazon DynamoDB table via DynamoDB streams.

<br>

**The Services that are being used are:**

- [AWS Cloudformation](https://aws.amazon.com/cloudformation/) - lets you model, provision, and manage AWS and third-party resources by treating infrastructure as code.

- [Amazon DynamoDB](https://aws.amazon.com/dynamodb/) - fully managed, serverless, key-value NoSQL database designed to run high-performance applications at any scale

- [AWS Lambda](https://aws.amazon.com/lambda/) - serverless, event-driven compute service that lets you run code for virtually any type of application or backend service without provisioning or managing servers

- [Amazon SNS](https://aws.amazon.com/sns/) - is a web service that coordinates and manages the delivery or sending of messages to subscribing endpoints or clients.

<br>

In 30 minutes, you will deploy the Cloudformation template which will create the following resources:

1. Amazon DynamoDB table (Name: MyTable) - Will have a hash and sort key
2. AWS Lambda Function (Name: MyLambda) - includes the DynamoDB streams trigger + Invoke the SNS Publish API
3. Amazon SNS Topic Created with Email (Name: - User will need to subscribe)

<br>

Steps:

1. Download the repository and make sure you have access to the **DynamoDB-to-SNS.yaml** file.

2. Open the file up in a code editor, (Visual Studio Code Preferred) and then locate the **.yaml file**.

3. In the .yaml file, scroll down and find **abcd@gmail.com.** Replace that email with your own personal email.

4. Save the file and know where it is located.

5. Please access the **AWS Console** via your own personal account.

6. In the search bar at the top, please search Cloudformation and click on **"Cloudformation"**.

7. Locate "Stacks" on the left side and click on it.

8. Click the **"create stack"** dropdown and click **"with new resources"**.

9. Click **"upload a template file"** and then **"choose a file"**.

10. Locate the **DynamoDB-to-SNS.yaml** file that you just updated with your own personal email.

11. Once that is done, select it, and click Next and Enter a **stack name** (DynamoDB-to-SNS) and click Next one more time.

12. Scroll down, **acknowledge** and checkbox and then click **"Submit"**.

13. Once you submit, wait a few minutes and reload your page and you should see a **"CREATE_COMPLETE"** message with the stack you submitted (DynamoDB-to-SNS).

14. Once that is done, you will then go to your personal email that you inputted and **verify** your Amazon SNS email (check spam if you cannot find it in your inbox).

15. Then, navigate to Amazon SNS, click **"Topics"** on the left hand side and copy the Amazon ARN (Ex. arn:sns:us-east-1:xxxxxxxxxxx:MySNS)

16. Once copied, navigate to **AWS Lambda**, click **"Functions"** and click on the **"MyLambda"** function

17. Scroll down to the code section and select the index.py file on the left hand side. Then replace SNS arn with the ARN you just copy and pasted.

18. Click **"Deploy"** and wait for the successful deployment.

19. Once that is done, we will be testing the solution. Navigate to the service **"Amazon DynamoDB"** via the AWS Console search bar.

20. Then click **"Tables"** on the left side and click on MyTable (a resource created via Cloudformation).

21. Click the **"Actions"** dropdown and click **"Create Item"**.

22. Create a random item and click **"Create Item"**. An email will be sent to your email notifying an item creation in your Amazon DynamoDB (MyTable) table.

<br>

**In order to delete your deployed resources:**

1. Navigate to **"Cloudformation"**.

2. Select the **"DynamoDB-to-SNS"** Stack and click **"Delete"**.

3. Click **"Delete"** once again.

<br>

**This marks the conclusion of the blog/repository.**

