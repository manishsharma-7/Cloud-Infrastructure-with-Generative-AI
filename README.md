# Cloud-Infrastructure-with-Generative-AI

Speed up and automate the deployment and management of cloud infrastructure by using the AWS Cloud Development Kit (AWS CDK) and Amazon Q.

In this practice lab, you will:

- Create various AWS resources by using the AWS CDK and Amazon Q.
- Deploy an application by using the AWS CDK and Amazon Q.
- Test the application by using an Application Load Balancer.

<img width="965" height="526" alt="Screenshot 2025-09-26 at 2 54 28 pm" src="https://github.com/user-attachments/assets/9e42b7ae-56b6-4475-aa20-a1e187812055" />

## Introduction

- This solution uses the AWS Cloud Development Kit (AWS CDK) and Amazon Q to speed up the adoption of Infrastructure as Code (laC) to deploy applications and infrastructure in a repeatable manner.
- With the help of Amazon Q auto-suggestions, the infrastructure can be defined by using AWS CDK code constructs on integrated development environments (IDEs) such as Code Editor in Amazon SageMaker Studio, Visual Studio Code, PyCharm, and IntelliJ.
- AWS Toolkit and AWS Identity and Access Management (IAM) credentials enable the AWS CDK and Amazon Q on IDEs.
- As the CDK code is written, Amazon Q provides suggestions based on comments and the context of the existing code.
- When the code is completed and tested, it is synthesized into an AWS CloudFormation template, which deploys the resources and applications that were defined in the CDK code.
- After all the AWS resources have been deployed and the application comes online, end users can begin accessing the application through the Application Load Balancer.
- The infrastructure can be modified with minimal impact by using the CDK to add or remove resources from the deployed CloudFormation templates.


### Step 1

1. In the top navigation bar search box, type:  
   `sagemaker ai`
2. In the search results, under Services, click **Amazon SageMaker AI**.
   
   <img width="712" height="604" alt="Screenshot 2025-09-26 at 3 42 10 pm" src="https://github.com/user-attachments/assets/0d1fda5f-1ed5-4251-a139-bb36b955d67b" />


### Step 2

1. In the left navigation pane, under **Applications and IDEs**, click **Studio**.
2. On the Amazon SageMaker Studio home page, click **Open Studio**.  
   - SageMaker Studio opens in a new browser tab (or window). Keep the current browser tab open. You return to the AWS Management Console in a later step.

<img width="704" height="476" alt="Screenshot 2025-09-26 at 3 43 16 pm" src="https://github.com/user-attachments/assets/af45da90-6c4b-48cd-a9a7-68190e25b63b" />


### Step 3

1. If the Welcome pop-up box appears, click **Skip Tour** for now.  
   - You are welcome to take the tour, but it is not covered in this practice lab.

<img width="717" height="523" alt="Screenshot 2025-09-26 at 3 43 41 pm" src="https://github.com/user-attachments/assets/8b45174c-a2aa-4dce-b1c2-3fb3ef21f18f" />


### Step 4

1. In the Applications pane, click **Code Editor**.
2. On the Code Editor page, for the Code Editor application, under Action, click **Run**.  
   - The Code Editor application takes a few minutes to start.
3. Go to the next step.

<img width="952" height="651" alt="Screenshot 2025-09-26 at 3 44 19 pm" src="https://github.com/user-attachments/assets/3990f9f1-fd79-4d94-a93e-bf007b5c44ad" />

### Step 5

1. Under Action, click **Open**.  
   - The Code Editor application opens in a new browser tab (or window).
2. Go to the next step.

<img width="929" height="657" alt="Screenshot 2025-09-26 at 3 44 53 pm" src="https://github.com/user-attachments/assets/c00aba0b-996d-48ac-982b-d0f36383b5b4" />



### Step 6

- On the new Welcome tab, you have an option to choose a theme, which defines your overall IDE colors (not shown). You are welcome to choose a theme.

1. To close the Chat tab, click the **X**.
2. On the Welcome tab, review the content, and then click the **X** to close the tab.
3. Go to the next step.

<img width="883" height="465" alt="Screenshot 2025-09-26 at 3 45 39 pm" src="https://github.com/user-attachments/assets/f2201ff3-1feb-485a-9979-797bc69236e0" />


### Step 7

1. To view the Explorer window, in the left sidebar, click the **Exploration (two folders) icon**.
2. In the Explorer window, click **Open Folder**.
3. In the Open Folder search box, choose `/home/sagemaker-user/`.
4. Click **OK**.
5. Go to the next step.

<img width="815" height="331" alt="Screenshot 2025-09-26 at 3 46 17 pm" src="https://github.com/user-attachments/assets/8814b31e-1383-4de4-8686-eb20f590d7c3" />

### Step 8

1. In the pop-up box, choose the check box to select **Trust the authors of all files ...**.
2. Click **Yes, I trust the authors**.  
   - If the Welcome tab reappears, click the **X** to close the tab.
3. Go to the next step.

<img width="728" height="493" alt="Screenshot 2025-09-26 at 3 47 49 pm" src="https://github.com/user-attachments/assets/61fd126b-446b-4733-9311-49e7927cbf66" />


### Step 9

1. In the left sidebar, click the **menu icon (three lines)** to expand the menu.
2. Choose **Terminal**.
3. Choose **New Terminal**.  
   - A command shell is launched.
4. Go to the next step.

<img width="665" height="534" alt="Screenshot 2025-09-26 at 3 48 16 pm" src="https://github.com/user-attachments/assets/92fe1533-7dd0-404a-a796-bef340148f17" />


### Step 10

1. In the bottom bash terminal window, at the command prompt, run:  

   ```bash
   mkdir cdkapp
   ```

   - You can also copy-paste this text. If you receive an undefined value when you paste this, try again. The code should look similar to what is displayed in the screenshot example.

2. In the left Explorer window, review to see that the `cdkapp` directory was created.
3. To change the directory to `cdkapp`, run:  

   ```bash
   cd cdkapp
   ```

4. To initialize the cdk process, run:  

   ```bash
   cdk init -a app -l=python
   ```

   - The "cdk init" command uses the name of the project folder to name various elements of the project, including classes, subfolders, and files. 
   - Using the "-a" option, you can specify an app name.
   - Using the "-l" option, you can specify the programming language.

5. Go to the next step.

<img width="832" height="572" alt="Screenshot 2025-09-26 at 3 48 55 pm" src="https://github.com/user-attachments/assets/12bf0073-abc3-4513-9d8a-460dc0b8445e" />


### Step 11:
1. Review the cdk initialize process log and the virtual environment creation details.

- A virtual environment contains a specific Python interpreter, software libraries, and binaries that are needed to support a project (library or application). 

2. Go to the next step.

<img width="915" height="619" alt="Screenshot 2025-09-26 at 3 51 46 pm" src="https://github.com/user-attachments/assets/81dd673f-1935-43d7-a65a-d5c062a3db65" />


### Step 12:
1. In the left Explorer window, click to expand the cdkapp directory.
2. Open (double-click) the requirements.txt file.
3. In the top requirements.txt window, review the file contents.

- This file contains the version of the aws-cdk library, and the constructs version, to be downloaded.

4. To activate the virtual environment, run:

source .venv/bin/activate

5. Go to the next step.

<img width="897" height="484" alt="Screenshot 2025-09-26 at 3 52 13 pm" src="https://github.com/user-attachments/assets/20e0ece0-10a7-4291-bfa0-e2aace9c0d16" />


### Step 13:
1. In the AWS Management Console browser tab, navigate to the Amazon S3 console.

- Remember, on the top navigation bar, you can use the Services search box (or click Services) to navigate to a different service console.

2. On the General purpose buckets tab, Create a new bucket with name "lab-bucket-XXXXX"
3. Upload Files from the resource folder to the bucket.
4. Go to the next step.

<img width="945" height="572" alt="Screenshot 2025-09-26 at 3 57 19 pm" src="https://github.com/user-attachments/assets/b6c3e9a7-5a92-43c3-a830-1cffc20519da" />

<img width="459" height="331" alt="Screenshot 2025-09-26 at 4 02 48 pm" src="https://github.com/user-attachments/assets/eb3b228d-9e2c-4311-a65c-69e930e4b893" />


### Step 14:
1. On the Objects tab, review the files that were created as part of the previous step.

- The ci_genai_stack.py contains the resources that you build in the next steps. You can use this file as a reference to check that all the resources are configured in your stack.
- The vpcapp.zip file contains the data and the files for a census application.
- The userdata.sh file includes the commands to install the dependencies and the commands for the application. It also loads data into Amazon Relational Database Service (Amazon RDS).

2. Choose the check box to select the userdata.sh file.
3. Click Copy S3 URI.

- You use this URI to download the userdata.sh file to the Code Editor IDE for deployment purposes.

4. Go to the next step.

<img width="792" height="580" alt="Screenshot 2025-09-26 at 4 03 35 pm" src="https://github.com/user-attachments/assets/e3d2c007-0e28-45a2-a55b-67d43fd633cd" />


### Step 15:
1. Return to the Code Editor IDE browser tab.
2. To change to the cdkapp subdirectory that was created by the cdk init process, in the bottom terminal window, run:

            cd cdkapp

- Note that a cdkapp subfolder exists within the cdkapp directory.

3. To download the userdata.sh file, replacing <userdata-uri> with the S3 URI that you just copied, run:

            aws s3 cp <userdata-uri> .

- Make sure to include the space and period (.) at the end of the command.

4. In the left Explorer window, click to expand the cdkapp directory.
5. Click to expand the cdkapp subfolder.
6. Open (double-click) the userdata.sh file.
7. Go to the next step.

<img width="907" height="468" alt="Screenshot 2025-09-26 at 4 05 49 pm" src="https://github.com/user-attachments/assets/e5988b3b-0432-45d4-85b3-053097ca18b3" />


### Step 16:
1. In the top userdata.sh window, review the file contents.

- This file contains the libraries to be downloaded for the census application to run on an EC2 instance.
- The vpcapp is the census application that displays the population values from different years and countries.
- The database_populate function connects to the Amazon RDS database (DB) cluster and creates a population table with the data.
- The application function starts the application.

2. Go to the next step.

<img width="956" height="605" alt="Screenshot 2025-09-26 at 4 07 28 pm" src="https://github.com/user-attachments/assets/bd8b23c9-b2e3-4a1a-a2ea-5399b5975ffa" />



### Step 17:
1. In the left Explorer window, open (double-click) the cdk.json file.
2. In the top cdk.json window, scroll down to the line that reads: 

            "@aws-cdk/aws-ec2:restrictDefaultSecurityGroup": true,

3. Change the "true" value to "false".

- The line should now read:
  
            "@aws-cdk/aws-ec2:restrictDefaultSecurityGroup": false,

4. In the left sidebar, click the menu icon to expand the menu.
5. Choose File, and then choose Save (not shown).
6. Click the X to close the file.
7. Go to the next step.

<img width="949" height="599" alt="Screenshot 2025-09-26 at 4 08 22 pm" src="https://github.com/user-attachments/assets/e2aba19c-c3fc-4a7b-ad1c-059c4873bd02" />



### Step 18:
1. In the left Explorer window, in the cdkapp subfolder, open (double-click) the cdkapp_stack.py file.
2. In the bottom footer bar on the Code Editor page, click Amazon Q.
3. In the top search box, next to Resume Auto-Suggestions, review that the Auto-Suggestions are already in RUNNING state.

- Auto-suggestions provide you with code snippets that can help streamline and speed up the coding process.

4. Go to the next step.

<img width="875" height="665" alt="Screenshot 2025-09-26 at 4 09 55 pm" src="https://github.com/user-attachments/assets/420dd393-0324-4525-b929-72f5f84bbc56" />




### Step 19:
- In the next steps, using Amazon Q suggestions, you define a stack with AWS CDK constructs to build a 3-tier web application. The application consists of an Application Load Balancer, an EC2 instance, and an Amazon Relational Database Service (Amazon RDS) DB instance that is deployed in a virtual private cloud (VPC).

1. In the top cdkapp_stack.py window, review the file contents.
2. In the bottom terminal window, to move up one level in the directory, run:

            cd ..

3. Go to the next step.

<img width="872" height="566" alt="Screenshot 2025-09-26 at 4 10 47 pm" src="https://github.com/user-attachments/assets/f35ed51b-690b-442a-97f1-7b586c8e8ddc" />


### Step 20:
1. In the top cdkapp_stack.py window, in the aws_cdk import block, delete the existing import values, and then copy-paste the following:
```bash
Duration,
Stack,
SecretValue,
aws_ec2 as ec2,
aws_rds as rds,
aws_iam as iam,
aws_elasticloadbalancingv2 as elbv2,
```
2. In the def init method, select (highlight) and delete the comments.
3. Go to the next step.

<img width="857" height="620" alt="Screenshot 2025-09-26 at 4 12 42 pm" src="https://github.com/user-attachments/assets/17b62509-6ef1-42f5-8c80-170b5edbd281" />


### Step 21:
- In the cdkapp_stack.py file, make sure to indent the newly added constructs to avoid errors in the deployment process.

- Make sure to properly close the constructs after adding the suggestions. Refer to the screenshots in the following steps for correct syntax and indentation, as AI generated code is not always 100% accurate.

- The resource names that you see might differ from the screenshot examples.

1. To create a VPC, in the top cdkapp_stack.py window, type:
```bash
# create a vpc with IpAddresses 10.10.0.0/16, a NAT gateway, a public subnet, PRIVATE_WITH_EGRESS subnet and a RDS subnet
```
and press Enter.

- You can also copy-paste this construct. If you receive an undefined value when you paste this, try again. The construct should look similar to what is displayed in the screenshot example.

- Make sure to include the comment hash symbol (#) at the beginning.

- Make sure to align the comment under def. If that does not work, align the comment under class instead.

- The suggestion might take a couple of seconds to appear.

2. Review the suggestion displayed by Amazon Q.
3. On your keyboard, press the Tab key to accept the suggestion.
4. Go to the next step.

<img width="944" height="634" alt="Screenshot 2025-09-26 at 4 15 29 pm" src="https://github.com/user-attachments/assets/9b563cd1-75ad-4275-b3ad-1c47a54f55f0" />


### Step 22:
1. To create a security group for the load balancer, type:
```bash
# create a security group for the load balancer
```
and press Enter.

- Make sure to align it under the vpc block.

2. Review the Amazon Q suggestion.

- The suggestion allows all outbound traffic only.

3. To accept the suggestion, press Tab.
4. Go to the next step.

<img width="821" height="585" alt="Screenshot 2025-09-26 at 4 18 44 pm" src="https://github.com/user-attachments/assets/d337de61-88e6-4a6d-8a3c-b3506b6742e2" />


### Step 23:
1. To create a security group for the RDS instance, type:
```bash
# create a security group for the RDS instance
```
and press Enter.

2. Review the Amazon Q suggestion.
3. To accept the suggestion, press Tab.

- Make sure to align it with alb_sg construct.
- If the closing parenthesis is not enclosed, make sure to add it before you proceed to the next step.

4. Go to the next step.

<img width="782" height="514" alt="Screenshot 2025-09-26 at 4 25 30 pm" src="https://github.com/user-attachments/assets/04d893ad-4685-4b54-973d-9d3d7602d8ea" />

### Step 24:
1. To create a security group for the EC2 instance, type:
```bash
   # create a security group for the EC2 instance
```
and press Enter.

2. Review the Amazon Q suggestion.
3. To accept the suggestion, press Tab.
4. Go to the next step.

<img width="843" height="604" alt="Screenshot 2025-09-26 at 4 26 24 pm" src="https://github.com/user-attachments/assets/b5ca3200-81cb-434a-8225-a86a7631ba0c" />


### Step 25:
1. To add inbound rules to the load balancer, type:
```bash
# add ingress rules for the load balancer security group to allow all traffic on port 80
```
and press Enter.

2. Review the Amazon Q suggestion.

- Amazon Q should suggest that you let any IP address access the load balancer on port 80.

3. To accept the suggestion, press Tab.
4. Go to the next step.

<img width="791" height="528" alt="Screenshot 2025-09-26 at 4 29 06 pm" src="https://github.com/user-attachments/assets/a8e88eb0-24e6-4879-8500-d05cf09d144c" />



### Step 26:
1. To allow traffic from the load balancer to the EC2 instance, type:
```bash
# add ingress rule for the EC2 instance security group to allow 8443 traffic from the load balancer
```
and press Enter.

2. Review the Amazon Q suggestion.
3. To accept the suggestion, press Tab.
4. Go to the next step.

<img width="893" height="582" alt="Screenshot 2025-09-26 at 4 32 42 pm" src="https://github.com/user-attachments/assets/57265fff-2375-478a-af21-1280549ecead" />



### Step 27:
1. To allow traffic for the RDS DB instance from the EC2 instance on port 3306, type:
```bash
# add ingress rule to RDS security group to allow 3306 traffic from EC2 security group
```
and press Enter.

2. Review the Amazon Q suggestion.
3. To accept the suggestion, press Tab.
4. Go to the next step.

<img width="869" height="577" alt="Screenshot 2025-09-26 at 4 40 27 pm" src="https://github.com/user-attachments/assets/1605470d-400e-4606-a1f1-6494bf1f36dc" />


### Step 28:
1. To allow traffic for the RDS DB instance from the EC2 instance on port 22, type:
```bash
# add ingress rule for the RDS security group to allow 22 from the EC2 instance
```
and press Enter.

2. Review the Amazon Q suggestion.
3. To accept the suggestion, press Tab.
4. Go to the next step.
   
<img width="837" height="524" alt="Screenshot 2025-09-26 at 4 40 54 pm" src="https://github.com/user-attachments/assets/16946307-1d19-4953-a920-add6d2cbc92a" />



### Step 29:
1. To create an Amazon Aurora MySQL-Compatible Edition cluster, type:

```bash
        # create an rds aurora mysql cluster
        cluster = rds.DatabaseCluster(self, "MyDatabase",
            engine = rds.DatabaseClusterEngine.aurora_mysql(version = rds.AuroraMysqlEngineVersion.VER_3_04_0),
            # credentials using testuser and password1234!
            credentials = rds.Credentials.from_password("testuser", SecretValue.unsafe_plain_text("password1234!")),
            # add default database name Population
            default_database_name = "Population",
            instance_props={
                "vpc": vpc,
                "security_groups": [rds_sg],
                "vpc_subnets": ec2.SubnetSelection(subnet_type = ec2.SubnetType.PRIVATE_ISOLATED)
            },
            instances = 1
            )
```
and press Enter.

- Make sure to indent the construct with the construct above it.

2. Go to the next step.

<img width="837" height="562" alt="Screenshot 2025-09-26 at 4 41 45 pm" src="https://github.com/user-attachments/assets/b455eb2a-8766-4b80-8a12-1153f80111bb" />

### Step 30:
1. Review the Aurora cluster construct. 

- The cluster is created with the default database name, "Population", and the credentials are provided to connect to the cluster.
- The instance properties define the RDS instance type, VPC, subnet, and security group.

2. Go to the next step.

<img width="889" height="579" alt="Screenshot 2025-09-26 at 4 42 04 pm" src="https://github.com/user-attachments/assets/b29e6a1b-7064-4154-817e-f01c763fd7b6" />


### Step 31:
1. To create an Amazon Linux 2023 image, type:
```bash
# define an Amazon Linux 2023 image amzn_linux
```

2. Review the Amazon Q suggestion.
3. To accept the suggestion, press Tab.
4. Go to the next step.

<img width="798" height="501" alt="Screenshot 2025-09-26 at 4 42 31 pm" src="https://github.com/user-attachments/assets/48b09aa1-fcc5-4ed0-8005-384a0daf6171" />



### Step 32:
1. To read the userdata.sh file, type:
```bash
# read userdata.sh file from cdkapp directory using readlines
```
and press Enter.

2. Review the Amazon Q suggestion.
3. To accept the suggestion, press Tab.
4. Go to the next step.
   
<img width="829" height="543" alt="Screenshot 2025-09-26 at 4 43 02 pm" src="https://github.com/user-attachments/assets/8a44d59c-4b72-4324-bee6-45f9a42531dc" />



### Step 33:
1. To add lines from the userdata.sh file to ec2 UserData, type:
```bash
# Add each line from the script to ec2 UserData
```
and press Enter.

2. Review the Amazon Q suggestion.
3. To accept the suggestion, press Tab.
4. Go to the next step.

<img width="880" height="546" alt="Screenshot 2025-09-26 at 4 43 45 pm" src="https://github.com/user-attachments/assets/7ec73081-03eb-467f-b467-16c3455d7f7f" />


### Step 34:
1. To create an EC2 instance for the web server in a private egress subnet, type:
```bash
# create a t3.micro ec2 instance for the web server in a private egress subnet and vpc.availability_zones[0]
ec2_instance = ec2.Instance(self, "MyInstance",
            instance_type = ec2.InstanceType("t3.micro"),
            machine_image = amzn_linux,
            vpc = vpc,
            vpc_subnets = ec2.SubnetSelection(subnet_type = ec2.SubnetType.PRIVATE_WITH_EGRESS),
            availability_zone = vpc.availability_zones[0],
            user_data = user_data,
            security_group = ec2_sg,
            # add an existing role with name ec2_instance_role
            role = iam.Role.from_role_name(self, "ec2_instance_role", "ec2_instance_role")
        )
```
and press Enter.

2. Go to the next step.

<img width="819" height="575" alt="Screenshot 2025-09-26 at 4 44 20 pm" src="https://github.com/user-attachments/assets/b13d7d2f-4292-4ae8-a9f9-1ae88f0de773" />



### Step 35:
1. Review the ec2 instance construct.

- A t3.micro instance is created with an Amazon Linux 2023 image in a private subnet and deploys the application specified in the userdata script.
- The ec2_instance_role already created as part of the lab prebuild process, is used for the EC2 instance.

2. To add a wait dependency on the RDS cluster, at the end of the construct, type:
```bash
# add depends to ensure
```
and press Enter.

3. Review the Amazon Q suggestion.
4. To accept the suggestion, press Tab.
5. Go to the next step.

<img width="820" height="521" alt="Screenshot 2025-09-26 at 4 44 54 pm" src="https://github.com/user-attachments/assets/00f5eee6-b02d-45a0-accc-e603c2b9a6b4" />


### Step 36:
1. To create a load balancer, type:
```bash
# create a load balancer in the public subnet
```
and press Enter.

2. Review the Amazon Q suggestion.
3. To accept the suggestion, press Tab.
4. Go to the next step.

<img width="863" height="552" alt="Screenshot 2025-09-26 at 4 45 18 pm" src="https://github.com/user-attachments/assets/28a7cd23-7f56-46d0-88fb-8dc36d74dc77" />


### Step 37:
1. To create a listener for the load balancer, type:
```bash
# add a listener on port 80 to the load balancer with open=True
```
and press Enter.

2. Review the Amazon Q suggestion.
3. To accept the suggestion, press Tab.
4. Go to the next step.

<img width="830" height="555" alt="Screenshot 2025-09-26 at 4 45 41 pm" src="https://github.com/user-attachments/assets/751ab984-5df1-4d5d-ad16-3c023948ccee" />


### Step 38:
1. To add targets to the load balancer, type:
```bash
# add targets to the load balancer using port 80
listener.add_targets("MyTargets", port=80 )
```
and press Enter.

2. Go to the next step.

<img width="830" height="506" alt="Screenshot 2025-09-26 at 4 48 55 pm" src="https://github.com/user-attachments/assets/15ed69f1-dc9b-41ca-bb4f-1930111e2478" />


### Step 39:
1. To deploy the web server after the the RDS DB cluster is available, type:
```bash
# add depends on for the listener to wait for the ec2 instance 
```
and press Enter.

2. Review the Amazon Q suggestion.
3. To accept the suggestion, press Tab.
4. Go to the next step.

<img width="856" height="553" alt="Screenshot 2025-09-26 at 4 49 10 pm" src="https://github.com/user-attachments/assets/c3cd16ee-9971-4391-9e67-7442ae696264" />


### Step 40:
1. In the other browser tab, return to the lab-bucket page on the Amazon S3 console. 
2. On the Objects tab, choose on the check box to select ci_genai_stack.py.

- This file contains the resources that you build in the next steps. 
- You can download and use this file as a reference to check that all the resources are configured in your stack.

3. Go to the next step.

<img width="869" height="551" alt="Screenshot 2025-09-26 at 4 49 27 pm" src="https://github.com/user-attachments/assets/e8de3680-672b-403e-81fd-779d676089b3" />


### Step 41:
- The bootstrap process has been run as part of the lab prebuild process.

1. Return to the Code Editor IDE browser tab.
2. To synthesize the CDK stack, in the bottom terminal window, run:
```bash
cdk synth
```
- Remember, if there are any errors when running cdk synth, you can reference the ci_genai_stack.py from a previous step to troubleshoot.

3. Go to the next step.

<img width="921" height="622" alt="Screenshot 2025-09-26 at 4 49 57 pm" src="https://github.com/user-attachments/assets/775ac478-925b-4250-b676-bf2ee45fa222" />


### Step 42:
1. Review the stack details.
2. To deploy the cdkapp stack, run:
```bash
cdk deploy
```
3. Go to the next step.

<img width="700" height="608" alt="Screenshot 2025-09-26 at 4 50 16 pm" src="https://github.com/user-attachments/assets/0bcc1644-5e3c-4bef-98e8-93a597508aa0" />


### Step 43:
1. Review the stack components.
2. For "Do you wish to deploy these changes (y/n)?", type:
```bash
    y
```
and press Enter.

3. Go to the next step.

<img width="858" height="652" alt="Screenshot 2025-09-26 at 4 50 53 pm" src="https://github.com/user-attachments/assets/f47dcfd4-5067-4b8a-9c94-08545923ddbe" />



### Step 44:
1. Review the stack components that are being deployed by the cdk process.

- The deployment takes up to 15 minutes to be completed.

2. Go to the next step.

<img width="812" height="604" alt="Screenshot 2025-09-26 at 4 51 05 pm" src="https://github.com/user-attachments/assets/4a26fdfa-cd6e-43b9-8368-115a9beb747e" />


### Step 45:
1. After the deployment is completed, review the stack ARN.
2. Go to the next step.

<img width="913" height="642" alt="Screenshot 2025-09-26 at 4 51 23 pm" src="https://github.com/user-attachments/assets/5f684a35-6e70-4a55-8c89-fc02f85f22f9" />



### Step 46:
1. In the AWS Management Console browser tab, navigate to the AWS CloudFormation console.
2. In the Stacks section, under Status, review to confirm that the status for the stack, CdkappStack, is CREATE_COMPLETE.
3. Click CdkappStack.
4. Go to the next step.

<img width="943" height="557" alt="Screenshot 2025-09-26 at 4 51 40 pm" src="https://github.com/user-attachments/assets/0fc8bc4e-cd03-446a-9dd8-551c6ec53c96" />



### Step 47:
1. In the CdkappStack window, click the Resources tab.

- The logical IDs might differ from the example screenshot.

2. Review the list of created resources.
3. Go to the next step.


<img width="927" height="568" alt="Screenshot 2025-09-26 at 4 51 56 pm" src="https://github.com/user-attachments/assets/e060e808-9018-4611-bf18-a2104e3fdae9" />


### Step 48:
1. Click to expand MyLoadBalancer.

- This logical ID might differ from the screenshot example.

2. For the available load balancer, under Physical ID, click the URL.

- The URL opens in a new browser tab (or window).

3. Go to the next step.

<img width="864" height="562" alt="Screenshot 2025-09-26 at 4 52 14 pm" src="https://github.com/user-attachments/assets/bee804b1-23a3-406f-8003-29a67003678c" />



### Step 49:
1. In the Details section, review the load balancer details.
2. Go to the next step.

<img width="914" height="533" alt="Screenshot 2025-09-26 at 4 52 37 pm" src="https://github.com/user-attachments/assets/3708049c-09b7-47d1-b21b-54e936fb1798" />



### Step 50:
1. On the Listeners and rules tab, under Default action, click the target group that starts with Cdkapp-.

- The target group opens in a new browser tab (or window).

2. Go to the next step.

<img width="896" height="544" alt="Screenshot 2025-09-26 at 4 52 50 pm" src="https://github.com/user-attachments/assets/e521ffe4-201a-4057-95cc-2b3f67426953" />




### Step 51:
1. In the Details section, review the target group details.
2. Go to the next step.

<img width="919" height="569" alt="Screenshot 2025-09-26 at 4 53 06 pm" src="https://github.com/user-attachments/assets/19346833-b241-481d-926e-2d986b0bdcba" />


### Step 52:
1. On the Targets tab, click Register targets.
2. Go to the next step.

<img width="922" height="585" alt="Screenshot 2025-09-26 at 4 53 17 pm" src="https://github.com/user-attachments/assets/8137eb68-319d-44a8-adc0-073316d26af8" />



### Step 53:
1. In the Available instances section, choose the check box to select the CdkappStack/WebServer instance.
2. For Ports for the selected instances, to replace the default value, type:

8443

3. Click Include as pending below.
4. Go to the next step.

<img width="911" height="554" alt="Screenshot 2025-09-26 at 4 53 27 pm" src="https://github.com/user-attachments/assets/3e595046-dff4-47e4-a1f7-f9afe5c64f15" />



### Step 54:
1. In the Review targets section, review the added instance.
2. Click Register pending targets.
3. Go to the next step.

<img width="951" height="573" alt="Screenshot 2025-09-26 at 4 53 38 pm" src="https://github.com/user-attachments/assets/325ab8e7-ec0a-4f70-b242-c796e3ed2b18" />


### Step 55:
1. On the Targets tab, review the instance details.
2. Go to the next step.

<img width="929" height="588" alt="Screenshot 2025-09-26 at 4 53 59 pm" src="https://github.com/user-attachments/assets/8b61582a-c83e-47b7-b6a1-efce97ca3d8d" />




### Step 56:
1. Under Health status, review to confirm that the health status is Healthy.

- To update the health status, click the section's refresh icon. 
- A healthy status indicates that the load balancer is able to connect to the EC2 instance, and the application on the EC2 instance is up and running.

2. Scroll up to Details.
3. Go to the next step.

<img width="936" height="569" alt="Screenshot 2025-09-26 at 4 54 09 pm" src="https://github.com/user-attachments/assets/542ffff3-a04e-4a51-a60d-870a7805bc23" />




### Step 57:
1. Under Load balancer, click the provided load balancer name.

- The load balancer opens in a new browser tab (or window).

2. Go to the next step.

<img width="902" height="548" alt="Screenshot 2025-09-26 at 4 54 26 pm" src="https://github.com/user-attachments/assets/5e881b0b-ad13-42c9-b522-3fe5939a2391" />


### Step 58:
1. Under DNS name, click the copy icon to copy the load balancer URL.
2. Go to the next step.

<img width="927" height="587" alt="Screenshot 2025-09-26 at 4 54 45 pm" src="https://github.com/user-attachments/assets/3e2aabe3-6554-482a-ac82-3c68209211cf" />


### Step 59:
1. To access the census application, in a new browser tab (or window) address bar, paste the load balancer URL that you just copied (not shown).

- You should see the Population Facts page with year and country options.

2. Review the Availability Zone in which the instance is deployed.

- In the upcoming DIY section of this solution, you must deploy another instance in a different Availability Zone.

3. Click Submit.
4. Go to the next step.

<img width="775" height="495" alt="Screenshot 2025-09-26 at 4 54 59 pm" src="https://github.com/user-attachments/assets/60908c66-a438-4a38-bd4b-44cb6cc1db68" />




### Step 60:
1. Review the details of the population facts of Afghanistan in the year 1990.
2. To return to the main page, click Back.

- You can view the population facts for different years and different countries.

3. Go to the next step.

<img width="773" height="493" alt="Screenshot 2025-09-26 at 4 55 20 pm" src="https://github.com/user-attachments/assets/f7b04ac6-b7f6-4dbb-bcee-2dc299384ec2" />


---

