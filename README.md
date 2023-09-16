## Deploy 3 ! 

By Joseph White
September 16th, 2023


# Purpose: 
To automatically deploy an URL Shortener application to AWS Elastic Beanstalk using a Jenkins server installed on an EC2 for building and testing. 

# Steps: 
1.Launch an EC2 and install Jenkins.

⁃ Jenkins is used to pull the application from the Github repository for building, testing, and deployment. ⁃ The EC2 is running on previously configured security settings with access to Ports: 80, 8080, 22. ⁃

2. Install the Python packages python3.10-venv, python-pip, and unzip
 
 The python3.10-venv package is used to create isolated virtual environments for Python projects separate from your system wide python installation.

 The python-pip is used to install, upgrade, and manage Python packages and dependencies.

 The unzip utility is used to extract files from ZIP archives. 

3. Create a multibranch pipeline within your Jenkins server.

4. Install AWS CLI.

5. Install AWS Elastic Beanstalk CLI.

6. Add this stage to your Jenkins file stage ('Deploy') { steps { sh '/var/lib/jenkins/.local/bin/eb deploy' } }. This allows the application to be triggered automatically.

# Issues:


# System Diagram:



# Optimization:
