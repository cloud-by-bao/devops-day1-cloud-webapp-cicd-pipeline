<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Set Up a Web App in the Cloud

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-devops-vscode)

**Author:** Bao Luong  
**Email:** baodevops21@gmail.com

---

## Set Up a Web App Using AWS and VS Code

![Image](http://learn.nextwork.org/stimulated_brown_festive_kaffir_lime/uploads/aws-devops-vscode_7a1de541)

---

## Introducing Today's Project!

In this project, I will demonstrate the fundation of CI/CD pipline by creating a web app from stratch. I'm doing this project to learn how to launch an EC2 instance, connecting it to VS Code using SSH, then I will install Maven and Java and generate a basic web app.

This project is part one of a series of DevOps projects where I'm building a CI/CD pipeline! I'll be working on the next project tomorrow.

I did this project to sharpen my DevOps and Cloud journey and as part of the 7 day DevOps project. 

### Key tools and concepts

Services I used were VS Code and AWS EC2. Key concepts I learnt include using IDE, launching EC2, SSH connection, editing index.jsp file, and using key pair. 

### Project reflection

This project took me approximately about 3 hours. It was most rewarding to see a sucessful SSH connection to our EC2 instance, whether that's over the terminal or over VS Code SSH connection

One thing I didn't expect in this project was using the Terminal comparing to using IDE when editing file or navigating between folders/subfolders. IDE definitely made it a lot easier to use and edit code than terminal.

---

## Launching an EC2 instance

### What I did in this step

In this step, I will launch a new EC2 instance and set up a key pair for secure access. Also, I will need to set up network settings for the instance because I need to make sure EC2 instance and key pair will connect.

I started this project by launching an EC2 instance because it is the service that creates virtual computers/servers, and it will host the webapp project.

![Image](http://learn.nextwork.org/stimulated_brown_festive_kaffir_lime/uploads/aws-devops-vscode_7852fbf3)

### I also enabled SSH

SSH is a protocol used to make sure only authorized users can access a remote server.

I enabled SSH so that I can connect to the EC2 and only allows SSH traffic from my IP address adress for security. 

### Key pairs

A key pair in EC2 is like the keys to your virtual computer. Just like you need a key to unlock and start your car, a key pair lets you securely access your EC2 instance.

It's made of two halves: a public key that AWS keeps, and a private key that you download.

When you use the private key, it verifies that you're the one allowed to access that specific virtual machine, keeping everything secure and just for you.

### Downloaded key pair file

Once I set up my key pair, AWS automatically downloaded the private key pair .pem for save safekeeping.

---

## Set up VS Code

### What I did in this step

In this step, I will install VS Code in my computer.

Set up a terminal in VS Code, so I can communicate with my EC2 instance.

Update my key pair's permission settings, so I can use it to log into your EC2 instance later.

### What is VS Code?

VS Code is an IDE source code editor that offers fast, customizable environment for web and general programming.

I installed VS Code to write and edit the webapp's code today. 

![Image](http://learn.nextwork.org/stimulated_brown_festive_kaffir_lime/uploads/aws-devops-vscode_53d05e68)

---

## My first terminal commands

A terminal is where you send instructions to your computer using text instead of clicks.

The first command I ran for this project is CD which is change directory and it is used to navigate into the folder that you want to go to. 

### Updating file permissions

I also updated my private key's permissions by using Icacls (which stands for Integrity Control Access Control Lists) is a tool for Windows that lets you decide who can open or change the files on your system.

![Image](http://learn.nextwork.org/stimulated_brown_festive_kaffir_lime/uploads/aws-devops-vscode_9328ada1)

---

## SSH connection to EC2 instance

### What I did in this step

In this step, I will connect to EC2 because we will need to set up the web app.

### Connecting to EC2

To connect to my EC2 instance, I ran the command ssh -i .\nextwork-keypair.pem ec2-user@<DNS>

### This command required an IPv4 address

A server's IPV4 DNS is the public address for your EC2 server that the internet uses to find and connect to it. 

![Image](http://learn.nextwork.org/stimulated_brown_festive_kaffir_lime/uploads/aws-devops-vscode_e3069dca)

---

## Maven & Java

### What I did in this step

In this step, I will Install Apache Maven on the EC2 instance, and Amazon Corretto 8, a version of Java. These two tools that are going to help us build Java web apps.

### Why I'm using Maven

Apache Maven is a tool that helps developers build and organize Java software projects. It's also a package manager, which means it automatically download any external pieces of code your project depends on to work.

Maven is required in this project because it sets up all the necessary web files for us to create a web app structure. 

It uses something called archetypes, which are like templates, to lay out the foundations for different types of projects e.g. web apps.


### Why I'm using Java

Java is a popular programming language used to build different types of applications, from mobile apps to large enterprise systems.

Java is required in this project because Maven, which we just downloaded, is a tool that NEEDS Java to operate. So if we don't install Java, we won't be able to use Maven to generate/build our web app today.

---

## Create the Application

### What I did in this step

In this step, I will run Maven commands in your terminal to generate a Java web app.

### Creating the Java web app

I generated a Java web app using the command
mvn archetype:generate \
   -DgroupId=com.nextwork.app \
   -DartifactId=nextwork-web-project \
   -DarchetypeArtifactId=maven-archetype-webapp \
   -DinteractiveMode=false

```

### Installing Remote - SSH

I installed Remote - SSH, which is the computer or server you're connecting to using SSH. It's the target location where you want to run commands or manage files; in our case, the SSH Host is the EC2 instance we created.

### SSH configuration details

Configuration details required to set up a remote connection include the HostName, IndentityFile, and User.

![Image](http://learn.nextwork.org/stimulated_brown_festive_kaffir_lime/uploads/aws-devops-vscode_2939cf01)

---

## Create the Application

### Exploring the project structure

Using VS Code's file explorer, I could see folders and sub folders that are parts of a web app.

Two of the project folders created by Maven are src and webapp. The src (source) folder holds all the source code files that define how your web app looks and works.

src is further divided into webapp, which are the web app's files e.g. HTML, CSS, JavaScript, and JSP files, and resources, which are the configuration files a web app might need e.g. connection settings to a database.



![Image](http://learn.nextwork.org/stimulated_brown_festive_kaffir_lime/uploads/aws-devops-vscode_45f91fd7)

---

## Using Remote - SSH

### What I did in this step

In this step, I will install an extension in VS Code.
Use the extension to set up a connection between VS Code and EC2 instance.
Explore and edit Java web app's files using VS Code.

### Updating the web app

The index.jsp is  is a file used in Java web apps. It's similar to an HTML file because it contains markup to display web pages.

However, index.jsp can also include Java code, which lets it generate dynamic content.

This means content can change depending on things like user input or data from a database. Social media apps are great examples of web apps because the content you see is always changing, updating and personalised to you. HTML files are static and can’t include Java code. That's why it's so important to install Java in your EC2 instance - so you can run the Java code in your web app!

I edited index.jsp by changing the placeholder code with the changes that I want and then saving the code by ctrl + s. 

![Image](http://learn.nextwork.org/stimulated_brown_festive_kaffir_lime/uploads/aws-devops-vscode_7a1de541)

---

## Using nano

### Additional improvements

In this secret mission, I will Edit index.jsp using the terminal instead of an IDE.

### Terminal vs IDE

An alternative to using IDEs is within the terminal itself. To edit index.jsp, I ran the command CD commands to navigate to the right subfolder and then ran the nano command to edit the index.jsp file.

Compared to using an IDE, editing index.jsp in the terminal felt less intuitive as you have to use the keyword to navigate your coursor. I'd be more likely to use an IDE if there are a lots of code that needs to be updated/edit. IDE makes it easier see where all the folders and subfolders to make changes. 

### Verifying my work

To verify my editing work in the terminal, I opened the VS code window that had the SSH connection. 

It was possible to see my changes in VS Code right away because both the local terminal (connected via SSH) and the Remote - SSH session in VS Code are connected directly into the EC2 instance, so both are looking at the same files in real-time.

Any changes I make over one connection is instantly visible in the other because they’re communicating directly with the remote EC2 environment.

![Image](http://learn.nextwork.org/stimulated_brown_festive_kaffir_lime/uploads/aws-devops-vscode_a3324ad41)

---

---
