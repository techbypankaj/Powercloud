# Power Cloud
Java-17 (Maven) application 

Power Cloud !

Join with us!!!!



-----------------------------------------------
Installation of Tomcat on Amazon linux 2

#1: Install Java
#Install OpenJDK 17 JRE

sudo yum install  java-17-amazon-corretto
		
Copy Text
#Install OpenJDK 8 JDK

sudo yum install java-17-amazon-corretto-devel
		
Copy Text
export JAVA_HOME=/usr/lib/jvm/java-17-amazon-corretto.x86_64/bin/java
		
Copy Text
export PATH=${JAVA_HOME}/bin:${PATH}
		
Copy Text
#2: Install Tomcat

cd /opt
		
Copy Text
sudo wget http://archive.apache.org/dist/tomcat/tomcat-8/v8.5.100/bin/apache-tomcat-8.5.100.tar.gz
		
Copy Text
sudo tar -xvf apache-tomcat-8.5.100.tar.gz
		
Copy Text
sudo mv apache-tomcat-8.5.100 tomcat
		
Copy Text
#Create role and user

sudo vi /opt/tomcat/conf/tomcat-users.xml
		
Copy Text
role rolename="manager-script"/>
role rolename="manager-gui"/>
user username="tomcat" password="s3cret" roles="manager-script, manager-gui"/>

#if required Change the port from 8080 to 8282 (any port you want)

sudo vi /opt/tomcat/conf/server.xml
		
Copy Text
Connector port="8282" protocol="HTTP/1.1"
connectionTimeout="20000"
redirectPort="8443" />

#Start tomcat server

/opt/tomcat/bin/startup.sh
		
Copy Text
Check the webserver home is up and working
http://:8282/
