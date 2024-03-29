# tomcat-deployment-withJenkinsCICD

# Pre-Requisites:
    Jenkins Server
    Tomcat Server
    Install GIT and Maven in Jenkins Server
# Tomcat Server
  ![image](https://user-images.githubusercontent.com/58024415/103478357-1e3f0800-4dec-11eb-8fd0-f4ad9cf58cfb.png)
# Jenkins Server
  ![image](https://user-images.githubusercontent.com/58024415/103478368-34e55f00-4dec-11eb-8a88-e846572acef0.png)
# Add below plugin for copy sertting ssh connection between two servers
  Manage Jenkins  -->  Manage Plugins 
  In Available section, please select "Public Over SSH"
  
  ![image](https://user-images.githubusercontent.com/58024415/103478405-7aa22780-4dec-11eb-843e-b002014b81ab.png)
  
  Click on Install without restart
# Generate password for root user
    passwd ec2-user
    
# Change ownership for opt directory, since we installed tomcat at /opt directory
    chown -R ec2-user:ec2-user opt
    
# Configure Tomcat server with Jenkins
  Goto Manage Jenkins  -->  System
  
  ![image](https://github.com/Naresh240/tomcat-deployment-withJenkinsCICD/assets/58024415/5daca716-cea9-4920-bcb7-90d2ccd0af04)

# Create pipeline job to deploy web application into tomcat server
  Copy Jenkinsfile and copy to pipeline section
  
  ![image](https://user-images.githubusercontent.com/58024415/103479043-b17a3c80-4df0-11eb-992e-8837163259eb.png)

    For deploy stage goto pipeline syntax and provide details as shown below:
  
  ![image](https://user-images.githubusercontent.com/58024415/103479007-6a8c4700-4df0-11eb-8795-214317976a1d.png)
  
  Click on build
# Goto UI and check for output of our application
  http://3.236.240.247:8080/mavewebappdemo-2.0.0-SNAPSHOT/
  
  ![image](https://user-images.githubusercontent.com/58024415/103479064-e090ae00-4df0-11eb-8682-d0c98ab3587e.png)
