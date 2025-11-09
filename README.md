
# Set Up a Web App in the Cloud



**Author:** sandip kharel  
**Email:** kharelsundeep7@gmail.com

---

## Set Up a Web App Using AWS and VS Code

![Image](http://learn.nextwork.org/inspired_pink_joyful_camel/uploads/aws-devops-vscode_7a1de541)

---

## Introducing Today's Project!

In this project, I will demonstrate how to launch and configure an Amazon EC2 instance, connect to it remotely using Visual Studio Code, and set up a Java-based web application using Maven. I’m doing this project to learn the fundamentals of cloud infrastructure, remote development environments,

### Key tools and concepts

Services I used were Amazon EC2 for hosting the instance and VS Code with Remote-SSH for connecting and editing files. Key concepts I learnt include SSH connections, Java web app setup, and using Apache Maven to build and manage Java projects.

### Project reflection

One thing I didn’t expect in this project was how easily I could connect VS Code to my EC2 instance using SSH and work on it just like a local computer.

This project took me approximately 1 to 2 hours to complete. The most challenging part was connecting VS Code to the EC2 instance using SSH for the first time. It was most rewarding to see the Java web app structure successfully appear in VS Code and understand how each tool worked together.

This project is part one of a series of DevOps projects where I'm building a CI/CD pipeline! I'll be working on the next project in a few days to continue integrating automation and deployment steps into the pipeline.

---

## Launching an EC2 instance

I am launching an EC2 instance because it provides a virtual server environment on AWS where I can host, configure, and run my web application. Using EC2 allows me to work in a real cloud-based setup, gain hands-on experience with remote server management, and understand how infrastructure resources are deployed and maintained in the cloud.

### I also enabled SSH

SSH (Secure Shell) is a protocol that allows secure communication between two computers over a network. It encrypts all data transmitted, ensuring that sensitive information, such as login credentials and commands, remains protected. I enabled SSH so that I can securely connect from my local computer to my EC2 instance. This allows me to manage the server remotely through the terminal or VS Code, install software, and perform administrative tasks as if I were directly using the machine in the cloud.

### Key pairs

A key pair in EC2 is like the keys to our virtual computer. Just like we need a key to unlock and start our car, a key pair lets us securely access our EC2 instance.


Once I set up my key pair, AWS automatically downloaded a .pem file to my local computer. This is a private key file used for securely connecting to my EC2 instance via SSH. The .pem file acts as my authentication key, AWS stores the corresponding public key, and I use this private key to verify my identity and gain secure access to the virtual machine.

---

## Set up VS Code

Visual Studio Code is a lightweight yet powerful source code editor developed by Microsoft. It supports a wide range of programming languages and includes features such as syntax highlighting, debugging, version control, and integrated terminals.

I installed VS Code to connect to my Amazon EC2 instance and manage my project files directly from my local computer. Using the Remote SSH extension, I can securely access my EC2 server, edit code, install dependencies, and run commands as if I were working inside the server itself. This makes it easier to develop, test, and organize my web application in a single, efficient environment.

![Image](http://learn.nextwork.org/inspired_pink_joyful_camel/uploads/aws-devops-vscode_53d05e68)

---

## My first terminal commands

A terminal is a place where I can type commands to control my computer. The first command I ran for this project was cd ~/Desktop/DevOps to move into the folder where my .pem key file is stored. This helps the terminal find the key file needed to connect to my EC2 instance.

I also updated my private key’s permissions by running the command chmod 400 ec2-project-1.pem. This command makes the file readable only by me, which keeps my private key secure and allows me to connect safely to my EC2 instance.

![Image](http://learn.nextwork.org/inspired_pink_joyful_camel/uploads/aws-devops-vscode_9328ada1)

---

## SSH connection to EC2 instance

To connect to my EC2 instance, I ran the command:
ssh -i ~/Desktop/DevOps/ec2-project-1.pem ec2-user@54.146.243.65


### This command required an IPv4 address

A server’s IPv4 DNS is the public address that identifies and connects to the EC2 instance over the internet. It works like a web address that allows my local computer to find and securely communicate with my EC2 server.

![Image](http://learn.nextwork.org/inspired_pink_joyful_camel/uploads/aws-devops-vscode_e3069dca)

---

## Maven & Java

Apache Maven is a powerful build automation tool used for Java projects. It helps manage project dependencies, compile code, and package applications efficiently. Maven simplifies the development process by automating tasks like building, testing, and deploying software.

Maven is required in this project because it helps manage dependencies and automate the process of building Java applications. It simplifies compiling, packaging, and testing the code, making it easier to create and maintain the web app inside the EC2 instance.

Java is a popular programming language used to build a wide range of applications, from web apps to large enterprise systems. It’s reliable, platform-independent, and widely used for backend development. In this project, Java is used to run and build the web application inside the EC2 instance.

Java is required in this project because it’s the main programming language used to build and run the web application. It provides a stable and secure environment for developing backend systems, and tools like Maven rely on Java to compile and execute the application efficiently.

---

## Create the Application

I generated a Java web app using the Maven command mvn archetype: generate. This command creates a new project from a predefined template. I used -DartifactId=nextwork-web-project to name my project, -DarchetypeArtifactId=maven-archetype-webapp to specify it as a web application, and -DinteractiveMode=false to let Maven create the project automatically without asking for confirmation.

I installed Remote - SSH, which is an extension in VS Code that allows me to securely connect to my EC2 instance using SSH. I installed it to access and edit my project files directly on the remote server from within VS Code.

Configuration details required to set up a remote connection include the path to the .pem file, the EC2 username, and the public IPv4 DNS of the instance.


![Image](http://learn.nextwork.org/inspired_pink_joyful_camel/uploads/aws-devops-vscode_2939cf01)

---

## Create the Application

Using VS Code’s file explorer, I could see my project structure, including folders like src/main/webapp, WEB-INF, and files such as index.jsp and pom.xml. This helped me view and edit the Java web app’s files directly on my EC2 instance.

Two of the project folders created by Maven are src and webapp, which store the source code and web-related files. The src folder holds the Java code, while the webapp folder contains files like HTML, JSP, and web configurations for the web application.

![Image](http://learn.nextwork.org/inspired_pink_joyful_camel/uploads/aws-devops-vscode_45f91fd7)

---

## Using Remote - SSH

The index.jsp is a file used in Java web applications to display web pages. It works like an HTML file but can also include Java code, allowing it to generate dynamic content based on user input or data from a database.

I edited index.jsp by opening it in VS Code and modifying the code to change the web page’s content and layout, allowing me to customize what the Java web app displays.

![Image](http://learn.nextwork.org/inspired_pink_joyful_camel/uploads/aws-devops-vscode_7a1de541)

---


