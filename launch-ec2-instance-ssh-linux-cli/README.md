  # Launching EC2 Instance and SSHing into it using Linux CLI
  ![SSH-into-EC2](https://github.com/niazkhan0731/AWS-Projects/assets/135728087/b4d92307-80b8-4cd4-af75-7f3c14fa2ee7)

This is my first attempt at launching an EC2 instance using the AWS Management Console for the very first time and SSHing into it using the Bash Shell CLI on Linux. Here, I would like to document step by step how I accomplished it and the challenges I faced.

Using the CLI to control the EC2 instance offers several benefits:

- <b>Automation and Scripting:</b> The CLI allows for automation of repetitive tasks and the creation of scripts to streamline operations. It enables you to write scripts, perform batch operations, and automate the management of EC2 instances, enhancing efficiency and productivity.

- <b>Flexibility and Control:</b> The CLI provides fine-grained control over EC2 instance management. It offers a wide range of commands and options, enabling precise configuration, monitoring, and maintenance of instances. You can customize your commands to suit your specific requirements and have more control over your environment.

- <b>Remote Access</b>: With the CLI, you can remotely access and manage EC2 instances from anywhere using SSH. This allows for greater flexibility and convenience, as you can securely connect to your instances, execute commands, and troubleshoot issues without relying on a graphical user interface.

- <b>Integration with Other Tools:</b> The CLI seamlessly integrates with other tools, such as scripting languages, automation frameworks, and third-party applications. This enables you to incorporate EC2 instance management into your existing workflows and integrate it with your preferred development or deployment pipeline.

- <b>Efficiency and Speed:</b> The CLI often provides faster and more efficient management compared to the graphical user interface. It allows for quick execution of commands, retrieval of information, and configuration changes, making it ideal for situations that demand speed and agility.

By leveraging the power of the CLI, I not only gained a deeper understanding of EC2 instance management but also experienced firsthand the advantages it offers in terms of automation, control, remote access, integration, and overall operational efficiency.  
  ## Launching an EC2 Instance
First and foremost, I had to launch a new EC2 instance. I accomplished this by accessing my Sandbox environment, logging into the AWS Management Console, and then clicking on the <b>EC2</b> option. From there, I selected <b>Launch Instance</b>.

<img width="1136" alt="2" src="https://github.com/niazkhan0731/AWS-Projects/assets/135728087/8a5163be-cc21-4eb2-84a8-f8de04b10a74">

<br>From there, I named my EC2 instance <b>demo</b> and selected the <b><i>Amazon Linux 2 AMI</i></b>. I kept the instance type as <b><i>t2.micro</i></b> and clicked on <b><i>create new key pair</i></b>. I named the key pair and saved it to my downloads folder as a <b><i>.pem</i></b> file. Note that I used the .pem because I am connecting through Linux. If you are using Windows Putty to connect, you would download the .ppk file instead. I learned the hard way later on that knowing the location of this key pair is critical when using the terminal to SSH in because that is the file used to authenticate and establish the SSH connection.<br>
<br><img width="1270" alt="3" src="https://github.com/niazkhan0731/AWS-Projects/assets/135728087/f23f7c12-d363-4390-abd1-26450e5b25fe"><br>

<br><img width="1267" alt="4" src="https://github.com/niazkhan0731/AWS-Projects/assets/135728087/37ac4658-f6bd-4721-a976-365db7a6da5b"><br>
<br>Lastly, I selected my default security group and clicked on <b>Launch Instance</b>. This successfully created my EC2 instance called <b>demo</b>. I then waited for the instance state to show <b><i>Running</i></b> and the status check to display <b><i>checks passed</i></b>. Displaying the instance state and status check when launching an EC2 instance is important for real-time monitoring, validating a successful launch, troubleshooting, and being immediately aware of any failures. It provides visibility into the progress and health of the launched instances and ensures a smooth deployment process.<br>
<br><img width="1270" alt="5" src="https://github.com/niazkhan0731/AWS-Projects/assets/135728087/44ba466b-5a28-4780-8f3a-16141512cc55"><br>
## SSHing Into The EC2 Using Linux Bash CLI
Now that I've successfully launched my instance, it is now time to SSH into it remotely using the Linux Bash CLI. First, I opened my Bash terminal and changed directories to where my .pem file is located, which is my downloads folder, by typing the command <b><i>cd ~/Downloads</i></b>. Then, I used the command <b><i>ls</i></b> to quickly verify that the .pem file I am looking for is indeed in this directory.

<br><p align="center"><img width="731" alt="6" src="https://github.com/niazkhan0731/AWS-Projects/assets/135728087/44acd9b5-075b-4442-9166-7f7ca7749cad"></p><br>

<br>One challenge I faced when I got to this point is when I tried to SSH in, I kept getting denied access. After troubleshooting this issue, I realized that I first needed to change the permission of the file using the command <b><i>chmod 400 demokeypair.pem</i></b>. This allowed me to successfully establish an SSH connection to my EC2 instance. This step is important because it ensures that the file has the correct permissions and only the owner has read access, enhancing the security of the key pair. It prevents unauthorized users from accessing the key and strengthens the overall security of the SSH connection.<br>
<br><p align="center"><img width="733" alt="7" src="https://github.com/niazkhan0731/AWS-Projects/assets/135728087/8402459f-4c64-4dde-af98-563e80502e61"></p><br>

Now that is done I need to go back my EC2 Instance, go to the details tab and copy the public IPv4 address.<br>
<br><img width="1265" alt="8" src="https://github.com/niazkhan0731/AWS-Projects/assets/135728087/b155e199-54c4-47f6-88b8-cceb8647ccec"><br>

<br>Once successfully copied, I went back to my CLI and typed in the command <b><i>ssh -i demokeypair.pem ec2-user@52.25.104.60</i></b>, and voila! I am now remotely connected to my EC2 instance and able to perform tasks such as managing files, installing software, configuring server settings, and running various commands directly from my command line interface.<br>
<br><p align="center"><img width="734" alt="9" src="https://github.com/niazkhan0731/AWS-Projects/assets/135728087/a5f642f7-2d82-4cc7-b439-5194b281096e"></p>

