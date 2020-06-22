# Jenkinsfile_Selenium_Example

1.	Install Chrome browser on CentOS/Any machine: https://linuxize.com/post/how-to-install-google-chrome-web-browser-on-centos-7/ 
2.	Download chromedriver on CentOS/Any machine: https://www.tomordonez.com/install-chromedriver-linux/
Please note: chromedriver and Chrome browser should be compatible with version unless test will fail for version mismatch.
This is the directory where to download Chromedriver: https://sites.google.com/a/chromium.org/chromedriver/downloads
$ wget https://chromedriver.storage.googleapis.com/2.37/chromedriver_linux64.zip
$ unzip chromedriver_linux64_2.3.zip
$ sudo cp chromedriver /usr/bin/chromedriver
$ sudo chown root /usr/bin/chromedriver
$ sudo chmod +x /usr/bin/chromedriver
$ sudo chmod 755 /usr/bin/chromedriver
Then setup Chromedriver using the right location.
driver = webdriver.Chrome('/usr/bin/chromedriver')
3.	Update selenium script with the chromedriver location e.g. System.setProperty("webdriver.chrome.driver","/usr/bin/chromedriver");
4.	Install Git on CentOS/Any machine: Follow this: https://linuxize.com/post/how-to-install-git-on-centos-7/
5.	In Jenkins, Install Git plugin then go to manage Jenkins -> Global tool configuration-> Git-> Name: Default, Check ‘Install automatically’ if you don’t have installed in your machine or virtual instance, Path to Git Executable: Git
6.	In Jenkins, go to manage Jenkins -> Global tool configuration-> NodeJS-> Name: node, Check ‘Install automatically’, select the version from dropdown and left the other fields as it is. Jenkins will take care NodeJS installation.
7.	Install JDK on CentOS: sudo yum install java-1.8.0-openjdk-devel (this is JDK on JDK, not JDK on JRE unless won’t work)
https://linuxize.com/post/install-java-on-centos-7/
8.	In Jenkins, go to manage Jenkins -> Global tool configuration-> JDK->Uncheck ‘Check ‘Install automatically’-> Name: JAVA_HOME -> JAVA_HOME Path: /usr/lib/jvm/java. 
9.	Install maven on CentOS/Any machine: sudo yum install maven
To get installed location: whereis maven
10.	In Jenkins, go to manage Jenkins -> Global tool configuration-> Maven->Uncheck ‘Check ‘Install automatically’-> Name: MAVEN_HOME -> MAVEN_HOME Path: /usr/share/maven. 
11.	Create new Job: New Item -> Pipeline Script
12.	GitHub project: Project URL: https://github.com/hossain434/Selenium_Sample_Example 
13.	Pipeline: Definition-> Pipeline script form SCM
SCM-> Git
Repository URL: https://github.com/hossain434/Selenium_Sample_Example  (doesn’t need to provide .git URL)
Left the credentials blank since this is public link
Branch to build: Master
Repository browser: Auto
Script path: Jenkinsfile
Create a Jenkinsfile and add in the GitHub project. If you have more than one then name as Jenkinsfile_1, Jenkinsfile_2 etc.
Example: https://github.com/hossain434/Selenium_Sample_Example/blob/master/Jenkinsfile 
14.	Build Trigger: Setup schedule.

