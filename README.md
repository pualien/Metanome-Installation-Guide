# Metanome-Installation-Guide
Step by step installation of Metanome Data Profiling Tool


##  Debian 8.1

### Dependencies

Download and install Java-JDK-7:
 ```
$ sudo apt-get install openjdk-7-jdk
$ apt-cache search jdk
```
Set up the environment, for example:
 ```
$ export JAVA_HOME=/usr/bin/jvm/java-7-openjdk-amd64
```
Download [Maven.zip][maven], unzip and set up the environment:
 ```
$ unzip apache-maven-3.3.9-bin.zip
$ export PATH=/home/"USER_NAME"/Downloads/apache-maven-3.3.9/bin:$PATH
```

#### Optional
Install Node.js, Npm, Bower:
 ```
$ apt-get install nodejs-legacy
$ apt-get install npm
$ npm install -g bower
```

### Metanome installation:
Download [Metanome][metanome], unzip and install:
 ```
$ unzip Metanome-master.zip
$ cd Metanome-master
$ mvn clean install
$ mvn -f deployment/pom.xml package
```

### Unzip Metanome Snapshot packaged with Jetty Web Server:
 ```
$ cd deployment/target
$ unzip deployment-0.0.2-SNAPSHOT-package_with_jetty.zip
$ cd deployment-"METANOME_VERSION"-SNAPSHOT
```

### Run Metanome:
 ```
$ chmod +x run.sh
$ ./run.sh
```
Or digit:
 ```
$ java -Xmx2g -jar jetty-runner.jar --config WEB-INF/jetty.xml
```



##  Windows

### Dependencies

Download and install [Java-JDK][windows-jdk]:

Set up the environment, for example:
* c:\Program Files\Java\jdk1.8.0_45 must be in your JAVA_HOME environment variable. You can add directories to your PATH in the control panel; the details vary by Windows version.

Download [Maven.zip][maven], unzip and set up the environment:
* c:\apache-maven-"VERSION_NUMBER"\bin must be in your PATH environment variable, just like the J2SE SDK commands. 

#### Optional
Install Node.js, Npm, Bower:
* Download and install [Node.js][node.js]
* The npm command-line tool is bundled with Node.js.
* Download and install Bower from command-line interface: ``` $ npm install -g bower```

### Metanome installation:
Download [Metanome][metanome], unzip and then install from command-line interface:
 ```
$ cd Metanome-master
$ mvn clean install
$ mvn -f deployment/pom.xml package
```

### Unzip Metanome Snapshot packaged with Jetty Web Server:
* ``` $ cd deployment/target ```
* Unzip deployment-0.0.2-SNAPSHOT-package_with_jetty.zip
*  ``` $ cd deployment-"METANOME_VERSION"-SNAPSHOT ```

### Run Metanome:
* Open run.bat
* Or digit from command-line interface:
 ```
$ java -Xmx2g -jar jetty-runner.jar --config WEB-INF/jetty.xml
```


[maven]: <https://maven.apache.org/download.cgi>
[metanome]: <https://github.com/HPI-Information-Systems/Metanome>
[windows-jdk]: <http://www.oracle.com/technetwork/java/javase/downloads/index.html>
[node.js]: <https://nodejs.org/en/>
