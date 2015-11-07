Troubleshooting DataTorrent RTS
===============================

## Download

###  Where can I get DataTorrent RTS software?

DataTorrent products are available for download from [https://www.datatorrent.com/download/](https://www.datatorrent.com/download)

-  **Community Edition**:  It is a packaged version of Apache Apex and enables developers to quickly develop their big data streaming and batch projects.
-  **Enterprise Edition**:  Designed for enterprise production deployment and includes security, advanced monitoring and troubleshooting, graphical application assembly, and application data visualization.
-  **Sandbox Edition**:  Enterprise Edition and demo applications pre-installed and configured with a single-node Hadoop cluster running in a virtual machine.  Optimized for evaluation and training purposes.
-  **dtIngest Application**: simplifies the collection, aggregation and movement of large amounts of data to and from Hadoop and is available for production use at no cost.

###  What is the difference between DataTorrent RTS editions?

Please refer to [DataTorrent RTS editions overview](https://www.datatorrent.com/product/edition-overview/)

###  Where can I find the Standard edition installer?

You can use the download link for Enterprise edition as the package is
same for both editions. But, you have to apply the license to enable the
Standard edition. You can upgrade the license by using dtManage.
Licenses are available in 2 types : evaluation and production.

###  What are DataTorrent RTS package contents of Community vs Enterprise edition?

Package contents for Community edition:

-   Apache Apex (incubating)
-   DataTorrent Demo Applications
-   DataTorrent dtManage
-   DataTorrent dtIngest

Package contents for Enterprise edition:

-   Apache Apex (incubating)
-   DataTorrent Demo Applications
-   DataTorrent Operator Library
-   DataTorrent Enterprise Security
-   DataTorrent dtManage
-   DataTorrent dtIngest
-   DataTorrent dtAssemble
-   DataTorrent dtDashboard

###  How do I confirm the package downloaded correctly?

You can verify the downloaded DataTorrent RTS package by comparing with
MD5 sum. The command to get md5 sum of downloaded package:

    # md5sum <DT_RTS_Package>

Compare the result with MD5 sum posted on the product download page.

###  How do I download the DataTorrent RTS package using CLI?

Use following curl command to download DataTorrent RTS package:

    curl -LSO <DT_RTS_download_link>

We recommend using ‘curl’ instead of ‘wget’, which lacks chunked transfer encoding support, potentially resulting in corrupted downloads.

###  What are the prerequisites of DataTorrent RTS ?

DataTorrent RTS platform has following Hadoop cluster requirements:

-   Operating system supported by Hadoop distribution
-   Hadoop (2.2 or above) cluster with HDFS, YARN configured. Make sure
    hadoop executable available in PATH variable
-   Java 7 or 8 as supported by Hadoop distribution
-   Minimum of 8G RAM available on the Hadoop cluster
-   Permissions to create HDFS directory for DataTorrent user
-   Google Chrome, Firefox, or Safari to access dtManage (DataTorrent UI
    console)

###  Where can I start from after downloading DataTorrent RTS?

-   After successful download of DataTorrent RTS, make sure all prerequisites are satisfied.
-   You will need to install DataTorrent RTS on Hadoop cluster using the downloaded installer. Refer to [installation guide](installation.md)
-   Once installed, you will be prompted to proceed to dtManage, the DataTorrent management console, where you will be able to launch and manage applications.

###  What are the supported Hadoop distribution by DataTorrent RTS?

DataTorrent RTS is a Hadoop 2.x native application and is fully
integrated with YARN and HDFS providing tight integration with any
Apache Hadoop 2.x based distribution.

<table>
<col width="50%" />
<col width="50%" />
<tbody>
<tr class="odd">
<td align="left"><p>Hadoop Distribution</p></td>
<td align="left"><p>Supported Version</p></td>
</tr>
<tr class="even">
<td align="left"><p>Amazon EMR</p></td>
<td align="left"><p>Hadoop 2.4 and higher</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Apache Hadoop</p></td>
<td align="left"><p>Hadoop 2.2 and higher</p></td>
</tr>
<tr class="even">
<td align="left"><p>Cloudera</p></td>
<td align="left"><p>CDH 5.0 and higher</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Hortonworks</p></td>
<td align="left"><p>HDP 2.0 and higher</p></td>
</tr>
<tr class="even">
<td align="left"><p>MapR</p></td>
<td align="left"><p>4.0 and higher</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Microsoft</p></td>
<td align="left"><p>HDInsight</p></td>
</tr>
<tr class="even">
<td align="left"><p>Pivotal</p></td>
<td align="left"><p>2.1 and higher</p></td>
</tr>
</tbody>
</table>

###  What is the Datatorrent Sandbox?

The Sandbox provides a quick and simple way to experience DataTorrent RTS without setting up and managing a complete Hadoop cluster. The Sandbox contains pre-installed DataTorrent RTS Enterprise Edition along with all the Hadoop services required to launch and run the included demo applications.

###  Where do I get DataTorrent Sandbox download link?

Sandbox can be downloaded by visiting [datatorrent.com/download](https://www.datatorrent.com/download/)

###  What are the system requirements for sandbox deployment?

The DataTorrent RTS Sandbox is a complete, stand-alone, instance of the
Enterprise Edition as a single-node Hadoop cluster on your local
machine. Following are prerequisites for DataTorrent RTS:

-  [VirtualBox](https://www.virtualbox.org/) 4.3 or greater installed.
-  6GB RAM or greater available for Sandbox VM.

###  What are the DataTorrent RTS package content details in sandbox?

-  Ubuntu 12.04 LTS + Apache Hadoop 2.2 (DataTorrent RTS 3.1 or earlier)
-  Lubuntu 14.04 LTS + Apache Hadoop 2.7 (DataTorrent RTS 3.2 or later)
-  Apache Apex (incubating), Apache Apex-Malhar (incubating)
-  DataTorrent Operator Library
-  DataTorrent Enterprise Security
-  DataTorrent dtManage
-  DataTorrent dtIngest
-  DataTorrent dtAssemble
-  DataTorrent dtDashboard
-  Demo Applications


### What is dtIngest applicaiton?

DataTorrent dtIngest simplifies the collection, aggregation and movement of large amounts of data to and from Hadoop and is available for production use at no cost.

###  Where do I get dtingest application?

Application can be downloaded by visiting [datatorrent.com/download](https://www.datatorrent.com/download/)

###  What are the dtingest package contents?

Package comprises of DataTorrent RTS and dtIngest application.

###  What are the prerequisites of dtIngest?

DataTorrent RTS 3.x and above. Please refer [dtIngest tutorial](dtingest.md) for more details.

###  Where can I start from after downloading dtingest?

-   Make sure all DataTorrent RTS prerequisites are satisfied before dtIngest installation.
-   Run the downloaded installer installer. Refer to DataTorrent RTS [installation guide](installation.md).
-   After DataTorrent RTS installation and configuration, you can configure and launch the
    dtIngest application from dtManage, the DataTorrent console. Refer to [dtIngest tutorial](dtingest.md) for more details.

###  How do I get specific DT version ?

You can find archive list of various DataTorrent RTS versions at the bottom of each product download page.

###  Where can I request new / upgrade current license?

Please follow the instructions at [License Upgrade](https://www.datatorrent.com/license-upgrade/)

###  Where do I find product documentation?

Please refer to: [DataTorrent Documentation](http://docs.datatorrent.com/)

###  Where can I learn more about Apache Apex?

You can refer Apex page for more details: [Apache Apex](http://apex.apache.org)

###  Do you need help?

You can contact us at [https://www.datatorrent.com/contact](https://www.datatorrent.com/contact)



# Installation

There are multiple installations available e.g. Sandbox Edition, Community Edition, Enterprise Edition, dtIngest. Supported operating systems are which support Hadoop platform (tested on CentOS 6.x and Ubuntu 12.04).

### Minimum hardware requirements, what happens if certain minimum configuration requirement has not been met?

Minimum of 8G RAM is required on the Hadoop cluster.

### What happens if java is not installed?

Following message can be seen when Java is not abilable on the system

    Error: java executable not found. Please ensure java
    or hadoop are installed and available in PATH environment variable
    before proceeding with this installation.

Install Java 7 from package manager of Linux Distribution and try running installer again.

### What happens if Hadoop is not installed?

Installation will be successful, however Hadoop Configuration page in dtManage (e.g. http://localhost:9090) will expect hadoop binary (/usr/bin/hadoop) & DFS location.

![HadoopConfiguration.png](images/troubleshooting/image02.png)

Install Hadoop \> 2.2.0 and update the configuration parameters above.

### How do I check if Hadoop is installed and running correctly?

Following commands can be used to confirm installed Hadoop version and if Hadoop services are running.

    $ hadoop version

    Hadoop 2.4.0
    Subversion [http://svn.apache.org/repos/asf/hadoop/common](http://svn.apache.org/repos/asf/hadoop/common) -r
    1583262
    Compiled by jenkins on 2014-03-31T08:29Z
    Compiled with protoc 2.5.0
    From source with checksum 375b2832a6641759c6eaf6e3e998147
    This command was run using
    /usr/local/hadoop/share/hadoop/common/hadoop-common-2.4.0.jar

    $ jps

    10211 NameNode
    10772 ResourceManager
    10427 DataNode
    14691 Jps
    10995 NodeManager


### What happens if the downloaded file is corrupted?

MD5 checksum will result in the following error:

    “Verifying archive integrity...Error in MD5 checksums: <MD5 checksum> is different from <MD5 checksum>”.

Downloaded installer could be corrupted.  Try downloading the installer again.  If using command line, use `curl` instead of `wget`.



### Why do I see the following permissions errors?

During installation following error message will be seen on screen

![Permissions Error](images/troubleshooting/image01.png)

These typically happen when specified directory does not exist, and the installation user does not have permissions to create it.  Following commands can be executed by user with sufficient privileges to resolve this issue:

    $ hadoop dfs -ls /user/<USER>/datatorrent
    $ hadoop dfs -mkdir /user/<USER>/datatorrent  
    $ hadoop dfs -chown <USER> /user/<USER>/datatorrent

# Upgrade

###  License agent errors cause problems during upgrade from DataTorrent RTS 2.0 to 3.0.

If your applications are being launched continuously, or you are unable to launch apps due to licensing errors, try running complete uninstall and re-installation of DataTorrent RTS.  See [installation guide](installation.md) for details.


# Configuration

Coming soon.

# Development

### Hadoop dependencies conflicts

Coming soon.  (Use provided scope, don’t bundle any Hadoop jars.)

### Getting this message in STRAM logs. Is anything wrong in my code?

    2015-10-09 04:31:06,749 INFO com.datatorrent.stram.StreamingContainerManager: Heartbeat for unknown operator 3 (container container_1443694550865_0150_01_000007)

Coming soon.


# Debugging

###  How to remote debug gateway service?

Update hadoop OPTS variable by running,

    export HADOOP_OPTS="-agentlib:jdwp=transport=dt_socket,server=y,suspend=y,address=5432 $HADOOP_OPTS

### How to setup DEBUG level while running an application?

Add the property :

    <property>
      <name>dt.application.<APP-NAME>.attr.DEBUG</name>
      <value>true</value>
    </property>


### My gateway is throwing the following exception.

      ERROR YARN Resource Manager has problem: java.net.ConnectException: Call From myexample.com/192.168.3.21 to 0.0.0.0:8032 failed on connection
      exception: java.net.ConnectException: Connection refused; For more  details see:[http://wiki.apache.org/hadoop/ConnectionRefused](http://wiki.apache.org/hadoop/ConnectionRefused) at
      sun.reflect.GeneratedConstructorAccessor27.newInstance(Unknown Source)
      at sun.reflect.DelegatingConstructorAccessorImpl.newInstance(DelegatingConstructorAccessorImpl.java:45)
      ...

Check if the host where gateway is running has yarn-site.xml file. You need to have all Hadoop configuration files accessible to dtGateway for it to run successfully.


# Log analysis

### How to set custom log4j properties for an app package

There are two ways of setting custom log4j.properties in Apex

1. Setting custom log4j.properties at the Application level.  This will ensure that custom log4j properties is used for all containers including Application Master.  Following attribute should be set at application level:

        <property>
          <name>dt.attr.CONTAINER_JVM_OPTIONS</name>
          <value>-Dlog4j.configuration=custom_log4j.properties</value>
        </property>

2. Setting custom log4j.properties at an individual operator level.  This sets the custom log4j properties only on the container that is hosting the operator.  Following attribute should be set at an operator level:

        <property>
          <name>dt.operator.<OPERATOR_NAME>.attr.JVM_OPTIONS</name>
          <value> -Dlog4j.configuration=custom_log4j.properties</value>
        </property>

Make sure that custom_log4j.properties is part of your application jar and is located under `src/main/resources`.  Following are examples of custom log4j properties files

1. Writing to a file

        log4j.rootLogger=${hadoop.root.logger} // this is set to INFO / DEBUG, RFA
        log4j.appender.RFA=org.apache.log4j.RollingFileAppender
        log4j.appender.RFA.layout=org.apache.log4j.PatternLayout
        log4j.appender.RFA.layout.ConversionPattern=%d{ISO8601} [%t] %-5p %c{2} %M - %m%n
        log4j.appender.RFA.File=${hadoop.log.dir}/${hadoop.log.file}

2. Writing to Console

        log4j.rootLogger=${hadoop.root.logger} // this is set to INFO / DEBUG, RFA
        log4j.appender.RFA=org.apache.log4j.ConsoleAppender
        log4j.appender.RFA.layout.ConversionPattern=%d{ISO8601} [%t] %-5p %c{2} %M - %m%n
        log4j.appender.RFA.layout=org.apache.log4j.PatternLayout


### How to check STRAM logs

You can get STRAM logs by retrieving YARN logs from command line, or by using dtManage web interface.  

In dtManage console, select first container from the Containers List in Physical application view.  The first container is numbered 000001. Then click the logs dropdown and select the log you want to look at.  

Alternatively, the following command can retrieve all application logs, where the first container includes the STRAM log.

    yarn logs -applicationId <applicationId>

### How to check application logs

On dt console, select a container from the Containers List widget
(default location of this widget is in the “physical” dashboard). Then
click the logs dropdown and select the log you want to look at.

![console-log-viewing.gif](images/troubleshooting/image00.gif)

### How to check killed operator’s state

On dt console, click on “retrieve killed” button of container List.
Containers List widget’s default location is on the “physical”
dashboard. Then select the appropriate container of killed operator and
check the state.

![RetrieveKilled.gif](images/troubleshooting/image03.gif)

### How to search for particular any application or container?

In applications or containers table there is search text box. You can
type in application name or container number to locate particular
application or container.

### How do I search within logs?

Once you navigate to the logs page,  

1. Download log file to search using your preferred editor  
2. use “grep” option and provide the search range “within specified range” or “over entire log”


# Launching Applications

### Application goes from accepted state to Finished(FAILED) state

Check if your application name conflicts with any of the already running
applications in your cluster. Apex do not allow two application with
same names run simultaneously.  
Your STRAM logs will have following error:  
“Forced shutdown due to Application master failed due to application
\<appId\> with duplicate application name \<appName\> by the same user
\<user name\> is already started.”  

### ConstraintViolationException while application launch

Check if all @NotNull properties of application are set. Apex operator
properties are meant to configure parameter to operators. Some of the
properties are must have, marked as @NotNull, to use an operator. If you
don’t set any of such @NotNull properties application launch will fail
and stram will throw ConstraintViolationException.    


#  Events

### How to check container failures

In StramEvents list (default location of this widget is in the “logical”
dashboard), look for event “StopContainer”. Click on “details” button in
front of event to get details of container failure.

### How to search within events

You can search events in specified time range. Select “range” mode in
StramEvents widget. Then select from and to timestamp and hit the search
button.

### tail vs range mode

tail mode allows you to see events as they come in while range mode
allows you to search for events by time range.

### What is “following” button in events pane

When we enable “following” button the stram events list will
automatically scroll to bottom when new events come in.

### Coming Soon

* Connection Refused Exception
* ClassNotFound Exception
* Launching apa vs jar
* DAG validation failed
* Multiple gateways running simultaneously, app not launched.
* HDFS in safe mode
* Application stays in accepted state
* Some containers do not get resources (specially in case of repartition)
* Insufficient memory set to operator causes operator kill continuously.
* Why is the number of events same/different at input and output port of each operator?

*  Shutdown vs kill option
*  Why shutdown doesn’t work? (if some containers are not running)
*  Can I kill multiple applications at same time?
*  Killing containers vs killing application
*  STRAM failures (during define partitions)
*  Thread local + partition parallel configuration
*  What to do when downstream operators are slow than the input  operators.
*  I am seeing high latency, what to do?
*  appConf in ADT (inside apa file) vs conf option in dtcli
*  Application keeps restarting (has happened once due to license agent during upgrade)
*  Operator getting killed after every 60 secs (Timeout issue)
*  How to change commit frequency
*  Difference between exactly once, at least once and at most once
*  Thread local vs container local vs node local
*  Setting operator memory
*  Turning Bufferserver memory
*  Turning STRAM memory
*  Cluster nodes not able to access edge node where Gateway is running
*  Developers not sure when to process incoming tuples in end window or when to do it in process function of operator

*  How partitioning works

    *  How the data is partitioned between different partitions.
    *  How to use stream-codec
    *  Data on which ports is partitioned? By default default partitioner partitions data on first port.
    *  How to enable stream-codec on multiple ports. (Join operator?? where both input-ports needs to receive same set of keys).

*   pom dependency management, exclusions etc. eg: Malhar library and
    contrib, Hive (includes hadoop dependencies, we need to explicitly
    exclude), Jersey(we work only with 1.9 version) etc

*  All non-transient members of the operator object need to be
    serializable. All members that are not serializable cannot be saved
    during checkpoint and must be declared transient (e.g. connection
    objects). This is such a common problem that we need to dedicate a
    section to it.

*   Exactly once processing mode. Commit operation is supposed to be
    done at endWindow. This is only best-effort exactly once and not
    100% guaranteed exactly once because operators may go down after
    endWindow and before checkpointing finishes.

*  How to check checkpoint size. (large checkpoint size cause instability in the DAG).
*  How to add custom metrics and metric aggregator.
*  Example of how to implement dynamic partitioning.
