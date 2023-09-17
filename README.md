# URL Shortener 3

By Joseph White
September 16th, 2023


## Purpose: 
To automatically deploy an URL Shortener application to AWS Elastic Beanstalk using a Jenkins server installed on an EC2 for building and testing. 

## Steps: 
1.Launch an EC2 and install Jenkins.

⁃ Jenkins is used to pull the application from the Github repository for building, testing, and deployment. ⁃ The EC2 is running on previously configured security settings with access to Ports: 80, 8080, 22. ⁃

2. Install the Python packages python3.10-venv, python-pip, and unzip
 
- The python3.10-venv package is used to create isolated virtual environments for Python projects separate from your system wide python installation.

- The python-pip is used to install, upgrade, and manage Python packages and dependencies.

- The unzip utility is used to extract files from ZIP archives. 

3. Create a multibranch pipeline within your Jenkins server in order to build and deploy different branches of your code separately.

4. Select GitHub as the branch source which allows you to connect Jenkins with your GitHub repository automatically triggering builds when changes are made to your code. Run the build to ensure success.

<img width="790" alt="Screenshot 2023-09-17 at 12 47 31 PM" src="https://github.com/z0sun/Deployment-3/assets/135557197/d9f45c8f-3e7d-4b78-bf4f-ca231205a56e"> 
<img width="804" alt="Screenshot 2023-09-17 at 12 26 23 PM" src="https://github.com/z0sun/Deployment-3/assets/135557197/02354241-ccdd-4711-9c9b-01fdc0071f53">

5. Install AWS EB CLI.

6. Add the `deploy` stage to your Jenkins file stage ('Deploy') { steps { sh '/var/lib/jenkins/.local/bin/eb deploy' } }. This step defines a deployment stage in your pipeline which instructs Jenkins to deploy your application using the EB CLI.

<img width="790" alt="Screenshot 2023-09-17 at 12 47 31 PM" src="https://github.com/z0sun/Deployment-3/assets/135557197/d9f45c8f-3e7d-4b78-bf4f-ca231205a56e">
<img width="784" alt="Screenshot 2023-09-17 at 12 26 31 PM" src="https://github.com/z0sun/Deployment-3/assets/135557197/cad84dd9-ce53-44ea-b0be-949fe6b51a6f">
<img width="804" alt="Screenshot 2023-09-17 at 12 26 23 PM" src="https://github.com/z0sun/Deployment-3/assets/135557197/02354241-ccdd-4711-9c9b-01fdc0071f53">

7. Configure a Webhook in your GiHub repository which will allow GitHub to notify Jenkins whenever changes are pushed to your repository. This automation ensures the Jenkins build and deploy processes are triggered automatically.


## Issues:

**I encountered issues with AWS credentials while trying to install AWS CLI. Simple syntax corrections fixed this issue.**

<img width="832" alt="Screenshot 2023-09-15 at 3 29 00 PM" src="https://github.com/z0sun/Deployment-3/assets/135557197/1827b6cd-dcde-4d4b-b9bc-c010ea6d5ef0">

## ***

**Issues with occured when trying to make commits via the AWS EB CLI. Confirming the corrrect IAM permissions were given to the user fixed** this issue. 

<img width="832" alt="Screenshot 2023-09-15 at 3 58 17 PM" src="https://github.com/z0sun/Deployment-3/assets/135557197/9caee4b2-be2a-4064-9731-679665093016">

## ***

## System Diagram:

![Deployment3 drawio (2)](https://github.com/z0sun/Deployment-3/assets/135557197/d956713b-5c20-4541-837b-a45f1d786a91)

## Optimization:
