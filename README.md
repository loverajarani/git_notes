# git_notes
git related issues and notes
*************************************** chef starter kit moving ************
rajarani@rajarani:~/Downloads$ scp -i kavitha_awskey.pem chef-starter.zip ubuntu@18.224.37.82:/tmp


Listen <%=node["port"]%>------------------------>write in metadata.rb
Listen <%=node["secureport"]%>
https://help.ubuntu.com/community/ListOfOpenSourcePrograms
https://help.ubuntu.com/community/ListOfOpenSourcePrograms

************************update ubuntu **************************
*&&&&&&&&&&&&&&&  install and remove of a package   &&&&&&&&&&&&&&&&&&&&&&*

https://www.pontikis.net/blog/package-management-system-update-ubuntu-desktop 



****************** to update ubuntu os  ************************
sudo apt-get update && sudo apt-get -V upgrade


******************* https://www.tutorialspoint.com/jenkins/jenkins_git_setup.htm *****************

******************* for any linux related iso images ******************************************
http://iso.linuxquestions.org/


************************** TO CHANGE JENKINS PORT ***************************

java -jar jenkins.war --httpPort=8282

C:\Program Files (x86)\Jenkins\jenkins.xml
C:\Users\welcome\.jenkins\

***************************** TO CHANGE THE JENKINS PORT IN UBUNTU ************************
root@admin:/etc/default# ls
acpid	      apport	    cacerts	   dbus		  halt	      keyboard	nss	    rcS      snmpd		useradd
acpi-support  avahi-daemon  console-setup  devpts	  im-config   kibana	ntfs-3g     rsync    speech-dispatcher	virtualbox
alsa	      bind9	    crda	   docker	  irqbalance  locale	ntp	    rsyslog  ssh		whoopsie
anacron       brltty	    cron	   elasticsearch  jenkins     logstash	ntpdate     saned    sysstat		xinetd
apache2       bsdmainutils  cups	   grub		  kerneloops  nginx	pulseaudio  slapd    ufw
root@admin:/etc/default# pwd
/etc/default
root@admin:/etc/default# cat jenkins 
# defaults for Jenkins automation server

# pulled in from the init script; makes things easier.
NAME=jenkins

# arguments to pass to java

# Allow graphs etc. to work even when an X server is present
JAVA_ARGS="-Djava.awt.headless=true"

#JAVA_ARGS="-Xmx256m"

# make jenkins listen on IPv4 address
#JAVA_ARGS="-Djava.net.preferIPv4Stack=true"

PIDFILE=/var/run/$NAME/$NAME.pid

# user and group to be invoked as (default to jenkins)
JENKINS_USER=$NAME
JENKINS_GROUP=$NAME

# location of the jenkins war file
JENKINS_WAR=/usr/share/$NAME/$NAME.war

# jenkins home location
JENKINS_HOME=/var/lib/$NAME

# set this to false if you don't want Jenkins to run by itself
# in this set up, you are expected to provide a servlet container
# to host jenkins.
RUN_STANDALONE=true

# log location.  this may be a syslog facility.priority
JENKINS_LOG=/var/log/$NAME/$NAME.log
#JENKINS_LOG=daemon.info

# Whether to enable web access logging or not.
# Set to "yes" to enable logging to /var/log/$NAME/access_log
JENKINS_ENABLE_ACCESS_LOG="no"

# OS LIMITS SETUP
#   comment this out to observe /etc/security/limits.conf
#   this is on by default because http://github.com/jenkinsci/jenkins/commit/2fb288474e980d0e7ff9c4a3b768874835a3e92e
#   reported that Ubuntu's PAM configuration doesn't include pam_limits.so, and as a result the # of file
#   descriptors are forced to 1024 regardless of /etc/security/limits.conf
MAXOPENFILES=8192

# set the umask to control permission bits of files that Jenkins creates.
#   027 makes files read-only for group and inaccessible for others, which some security sensitive users
#   might consider benefitial, especially if Jenkins runs in a box that's used for multiple purposes.
#   Beware that 027 permission would interfere with sudo scripts that run on the master (JENKINS-25065.)
#
#   Note also that the particularly sensitive part of $JENKINS_HOME (such as credentials) are always
#   written without 'others' access. So the umask values only affect job configuration, build records,
#   that sort of things.
#
#   If commented out, the value from the OS is inherited,  which is normally 022 (as of Ubuntu 12.04,
#   by default umask comes from pam_umask(8) and /etc/login.defs

# UMASK=027

# port for HTTP connector (default 8080; disable with -1)
HTTP_PORT=8282

********************************** PUTTY COPY& PASTE OPERATIONS ************************************
https://www.ssh.com/ssh/putty/putty-manuals/0.68/Chapter3.html#using-selection
https://www.ssh.com/ssh/putty/putty-manuals/0.68/Chapter4.html#config-mouse
https://help.skytap.com/ssh-sra-configuring-OS.html
https://help.skytap.com/VMClient.html


# servlet context, important if you want to use apache proxying
PREFIX=/$NAME

# arguments to pass to jenkins.
# --javahome=$JAVA_HOME
# --httpListenAddress=$HTTP_HOST (default 0.0.0.0)
# --httpPort=$HTTP_PORT (default 8080; disable with -1)
# --httpsPort=$HTTP_PORT
# --argumentsRealm.passwd.$ADMIN_USER=[password]
# --argumentsRealm.roles.$ADMIN_USER=admin
# --webroot=~/.jenkins/war
# --prefix=$PREFIX

JENKINS_ARGS="--webroot=/var/cache/$NAME/war --httpPort=$HTTP_PORT"
root@admin:/etc/default# 

*********************** INSTALL STEPS IN UBUNTU APACHE TOMCAT **************************

https://www.digitalocean.com/community/tutorials/how-to-install-apache-tomcat-8-on-ubuntu-16-04

https://www.linux.com/blog/learn/chapter/Intro-to-Kubernetes/2017/5/set-cicd-pipeline-kubernetes-part-1-overview
