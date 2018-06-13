
Assignment 1:
Install Jenkins using package.
Solution:

sudo yum install epel-release
 sudo yum update
 reboot
 java -version
 sudo yum install java-1.8.0-openjdk.x86_64
 java -version
 sudo cp /etc/profile /etc/profile_backup
 cd /etc/profile
 echo 'export JAVA_HOME=/usr/lib/jvm/jre-1.8.0-openjdk' | sudo tee -a /etc/profile
 echo 'export JRE_HOME=/usr/lib/jvm/jre' | sudo tee -a /etc/profile
  source /etc/profile
  echo $JAVA_HOME
  echo $JRE_HOME
  cd ~
   sudo wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins.repo
  yum install wget -y
   sudo wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins.repo
   sudo systemctl start jenkins.service
   sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io.key
   yum install jenkins
   sudo systemctl start jenkins.service
   sudo systemctl enable jenkins.service
   sudo firewall-cmd --zone=public --permanent --add-port=8080/tcp
   cat /var/lib/jenkins/secrets/initialAdminPassword
   952674f7f4824607a05f843b446afc51
   
   Assignment 2:
Install any five plugin and use them.
Solution:

SSH Remote
GIT Plugin
Build Timeout
AWS lambda
AWS Elastic Beanstalk deployement
Build publisher
Google login
Ansible


Install a plugin manually.
https://updates.jenkins-ci.org/download/plugins/Office-365-Connector/

I have also Office 365 connector plugin file (hpi) .
Then i have goto Manage Jenkin tab -> Manage Plugin -> Advance-> Upload the Plugin.

It is successfully installed.

Assignment 3:
Create a freestyle job to print "Hello world".
Solution : Created a freestyle job and successfully print message “Hello World”. 
Echo “Hello World”
Checked job logs and status is successful.

Create a freestyle job to which take absolute path of a directory then
i.List all files and directories inside that.
ii.Print a message "directory not exist" if directory doesn't exist on file system
iii.Print "Inappropriate permissions" if you don't have permissions to list files.


solution

cd /home/nishantkohli;ll

Created a project and define parameterized variable “path”

Commands execute in shell 
 ls $path
if [ $? -eq 0 ] 
	then	
           	echo "Directory exists in system"
  	
	else

	echo "Directory does not exists"
fi

Assignment4:
●Increase and decrease number of executors and observe the build queue.
Solution
The maximum number of Jenkins jobs is dependent upon what you set as the limits in the master and slaves. Usually, we limit by the number of cores, but your mileage may vary depending upon available memory, disk speed, availability of SSD, and overlap of source code.
For the master, this is set in Manage Jenkins > Configure System > # of executors
For the slaves (nodes), it is set in Manage Jenkins > Nodes > (each node) > Configure > # of executors
