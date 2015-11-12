DataTorrent RTS Configuration
================================================================================

This document covers all the information required to configure DataTorrent RTS
to run with Hadoop 2.2+. Basic understand of Hadoop 2.x, including HDFS and YARN
is required.  To learn more about Hadoop 2.x visit [hadoop.apache.org](https://hadoop.apache.org/).


## Installation

If you have not installed DataTorrent RTS already, follow the installation instruction in the [installation guide](installation.md).


------------------------------------------------------------------------

# Configuration Files

System configuration is stored in local files on the machine where
the DT Gateway was installed, as well as Apache Apex DFS root directory
selected during the installation.  Local files custom-env.sh can be used
to configure CLASSPATH, JAVA_HOME, and various runtime settings.

Depending on the installation type, these may be located under `/opt/datatorrent/current/conf` or `~/datatorrent/current/conf`.  See [installation guide](installation.md) for details.


### (install dir)/conf/custom-env.sh

This file can be used to configure behavior of DT Gateway service,
as well as dtcli command line utility.  After adding custom properties
to this file, dtgateway and dtcli utilities need to be restarted for
changes to take effect.

Example custom-env.sh configuration:

```bash
# Increase DT Gateway memory to 2GB
DT_GATEWAY_HEAP_MEM=2048m
```


Environment variables available for configuration

* *DT_GATEWAY_HEAP_MEM* - Maximum heap size allocated to DT Gateway service.  Default is 1024m.
* *DT_GATEWAY_DEBUG* - Set to 1 to enable additional debug information in the dtgateway.log
* *DT_CLASSPATH* - Classpath used to load additional jars or properties for dtcli and dtgateway

### (user home)/.dt/dt-site.xml

This file is used to customize DataTorrent platform and
applications behavior.  It can be particularly useful for changing
Gateway application connection address, or setting environment specific
settings, such as specific machine names, IP addresses, or performance
settings which may change from environment to environment.



Example of a single property configuration in dt-site.xml:


```xml
<configuration>
  <property>
      <name>dt.operator.MyCustomStore.host</name>
      <value>192.168.2.35</value>
  </property>
   …
</configuration>
```


#### Gateway Configuration Properties

* **dt.gateway.listenAddress** - The address and port DT Gateway listens to.  Defaults to 0.0.0.0:9090
* **dt.gateway.autoPublishInterval** - The interval in milliseconds DT Gateway should publish application information on the websocket channel.  Default is 1000.
* **dt.gateway.sslKeystorePath** - Specifying of the SSL Key store path enables HTTPS on the DT Gateway (See the [dtGatway Security](dtgateway_security.md) document)
* **dt.gateway.sslKeystorePassword** - The password of the SSL key store (See the [dtGatway Security](dtgateway_security.md) document)
* **dt.gateway.allowCrossOrigin** - Setting it to true allows cross origin HTTP access to the DT Gateway.  Default is false.
* **dt.gateway.authentication.(OPTION)** - Determines the scheme of Hadoop security authentication (See the [dtGatway Security](dtgateway_security.md) document).
* **dt.gateway.http.authentication** - Determines the scheme of DT Gateway HTTP security authentication (See the [dtGatway Security](dtgateway_security.md) document).
* **dt.gateway.staticResourceDirectory** - The document root directory where the DT Gateway should serve from for the /static HTTP path.


#### Application Configuration Properties

For a complete list of configurable application properties see the Attributes section below.


------------------------------------------------------------------------

# Resources Management and Performance Turning

Platform provides continuous information about CPU, Memory, and Network
usage for the system as a whole, individual running applications,
operators, streams, and various internal components.  These statistics
are available via [REST API](dtgateway_api.md), [dtCli](dtcli.md), and [dtManage](dtmanage.md).

The platform is also responsible for

-   Honoring the resource restrictions enforced by the YARN RM and take
    preventive action to meet them. This is done at both launch time
    (fit the execution plan to the number of containers and their
    sizes), as well as at run time.
-   Honoring resource restrictions an application developer
    may provide. This is more in terms of per container basis is used to
    decide when to add more partitions.


STRAM works on resource management on a continual basis will remain
aligned with all enhancements RM will do. As a multi-tenant application
it is very crucial to be able to perform within a given resource limit.
The resource limit is both in aggregate (number of containers), as well
as local (container limit). The design of the platform enables the
distribution of all three aspects of resource utilization (CPU, Memory,
I/O)

CPU
----------------

CPU is computed on a per thread basis within a container by the
StreamingContainer. It is a very useful data for STRAM to manage an
application at run time. Since each operator always is a single thread
application, it is possible to compute CPU utilization on a per operator
basis. CPU utilization is computed for operators, bufferserver as well
as common tasks within a container.

Network
--------------------

Network usage is not just needed to manage the application within
the container limit, or limit set by the users, but is also very useful
to compute parameters for SLA enforcement. Network I/O management is
very crucial as Yarn is not yet achieved a well defined control of
network I/O usage. A streaming application which at times is very heavy
on network I/O must therefore provide the extra management needed to
keep network I/O within limits.



RM puts limits on container use in terms of usage of network
interface card. STRAM works around this by usage of various stream
modes. As the the events generated within an application grow (sometimes
exponentially) various methods are used to manage the I/O within the
resource limits of containers, stream modes are very crucial part of
this effort. STRAM is fully cognizant of the impact of Stream modes on
NIC usage.



The network usage is not just the incoming rate of the tuples, but
also the number of events created within the application. For a lot of
applications one event has multiple dimensions. Which mean that
computations require ability to evaluate all combinations of these
dimensions. If the number of dimensions are D, then the number of events
is 2\*\*D - 1. For example 3 dimensional data produces 7 events (3C1 +
3C2 + 3C3 = 3 + 3 + 1 = 7). Adding one more dimension doubles the number
of events (15) and so forth. Management of network I/O used by the
application thus is very crucial to ability to run this application
successfully with 24x7 uptime, that too in a multi-tenant
environment.

RAM
----------------

RAM usage is not available per operator basis. STRAM keeps track
of resource usage on per container basis. In future we will provide
hooks to enable operator developers to add ability to provide hints to
STRAM on RAM usage.

Spike Management
-----------------------------

Streaming applications do not have same throughput (events/second)
for all 24 hours of the day. The incoming rate is one of the criteria of
resource requirement. Most streaming applications resolve this dichotomy
by providing resources for the peak. This means that the resource
utilization suboptimal for most of the day, and resource get locked up
in a multi-tenant environment.



The platform provides mechanisms to manage the spikes by adding
partitions during peak, and removing them once the spike goes away. In
future we will enable resource availability ahead of time to enable no
risk to SLA due to an upcoming spike. Ability to scale up and scale down
is a foundational aspect of resource management of the platform.

Partitioning
-------------------------

Partitioning and distribution of resource utilization across the
cluster is a foundational aspect of the platform. The platform follows
the essence of map-reduce. Atomic micro batches are computed across the
distributed containers, and partitions simply means that these micro
batches get partitioned accordingly. The partitions are done on two
aspects.

-   Fan-out, fan-in

    -   Nx1 partition
    -   NxM partition

-   Load split

    -   Load balance
    -   Sticky Key
    -   Skew Management
    -   Mixture of the above


In addition the partitioning the platform has following
features

-   Unifiers: Ability to provide merge points between two logical
    operators to enable partitioning to be relatively independent. The
    platform also inserts intermediate physical nodes (pass through) to
    enable better scale by reducing the fan-in. For example a 32x1
    partition means that the 1 downstream physical operator will need to
    listen to 32 upstreams. The fan in can be reduced by putting in four
    8x1 merge operators, that then fan into one 4x1 merge operator.
    Unifiers are critical in this aspect as these then run on the
    upstream node to allow unification. For example a “sum” operator in
    the above 32x1 fan in will get 32 sums from each partition per key.
    The unifier will then add these and pass along a single sum per key.
    A load balanced partition is much better than sticky key as it has
    no skew issues.
-   Bufferserver: This is the pivotal point of stream management,
    as the fan-out is done by the buffer server. STRAM keeps an active
    tab on the bufferserver data and a build up of queue is big input to
    possible partitioning call. The bufferserver size is also a critical
    input on the time it will take for a node recovery in at least once
    or exactly once mode, since the buffer server will replay the
    streaming windows.

Stream Modes
-------------------------

The platform support 5 stream modes, namely THREAD_LOCAL
(intra-thread), CONTAINER_LOCAL (intra process/jvm), NODE_LOCAL (intra
node), RACK_LOCAL (same rack), and unspecified. While determining
operation of an application the modes should be decided carefully. All
stream-modes are hints to the STRAM, and hence could be ignored if
resources are not available, and could be changed on a run-time basis.
There are pros and cons of each.

1.  **THREAD_LOCAL**: All the operators of the ports on this stream
    share the same thread. Tuples are thus passed via thread call stack.
    The performance is massive and go into 100s of millions
    of tuples/sec. Do note that if the operations are compute intensive,
    them THREAD_LOCAL may not perform better than CONTAINER_LOCAL.
    Thread call stack is extremely efficient in terms of I/O (there is
    no I/O here), but the same thread does both the upstream and
    downstream computation. One more limitation is that all downstream
    operators on this stream must have only one input port connected. If
    the JVM process is lost, all the operators are lost, and will be
    restarted again in another container.
2.  **CONTAINER_LOCAL**: All the operators of the ports on this
    stream are in the same process. Each denotes a separate thread, and
    tuples are passed via connectionBuffer as
    intra-process communication. There is no bufferserver in this mode.
    This mode has the very high throughput and can easily do more than
    million tuples/sec. There is no bufferserver, which means that
    tuples will be in memory, i.e. memory need may grow. Features that
    bufferserver provides (spooling, presistence) are not available.
    This mode relies on the downstream operator consuming tuples on an
    average at least as fast as they are emitted. If the JVM process is
    lost, all the operators are lost, and will be restarted again in
    another container.
3.  **NODE_LOCAL**: All operators on this stream are on the
    same node. The communication is inter-process and the engine will
    use local loopback. This mode is also very fast, as it is not NIC
    bound, but it has a bufferserver in between and all the features
    that buffer server provides (spooling, persistence) are available in
    this mode. If one container dies, then all the operators in that
    container are impacted, but other other operators as is. However if
    a node dies then the entire chain has to be restarted.
4.  **RACK_LOCAL**: All operators on this stream are in the
    same rack. This communication is not as fast, and is NIC bound. It
    has the bufferserver and all the features that
    bufferserver provides. Since the I/O is via local switch, the
    in-rack mode does better. Since most like all operators are separate
    node, the probability of multi operator outage is low. This mode is
    affected by switch outage.
5.  Unspecified: This is the default mode and STRAM does no
    attempt to put operators on the same rack or same node, or
    same process. There are no guarantees on whether the stream will
    cross switch boundaries in this mode. There is an assumption that
    this mode will generally result in slowest throughput.



![](images/configuration/image02.png)



------------------------------------------------------------------------


# Multi-Tenancy and Security

The platform is a YARN native application, and so all security features
available in Hadoop also apply for securing Apache Apex applications.  
The default security for the streaming application is kerberos based.


Kerberos Authentication
------------------------------------


Kerberos is a ticket based authentication system that provides
authentication in a distributed environment where authentication between
multiple users, hosts and services is needed. It is the de-facto
authentication mechanism supported in Hadoop. To use Kerberos
authentication, the Hadoop installation must first be configured for
secure mode with Kerberos. Please refer to the administration guide of
your Hadoop distribution on how to do that. Once Hadoop is running with
Kerberos security enabled, DataTorrent platform also needs to be
configured for Kerberos. There are two parts of the platform that need
to be configured, CLI and DT Gateway.



Hadoop Configuration
---------------------------------

The DataTorrent application uses delegation tokens to communicate
with ResourceManager (YARN) and NameNode (HDFS) and these tokens are
issued by those servers respectively. Since the application is long
running the tokens should be valid for the lifetime of the application.
Hadoop has a configuration settings for the maximum lifetime of the
tokens and they should be set to cover the lifetime of the application.
There are separate settings for ResourceManager and NameNode delegation
tokens.



The ResourceManager delegation token max lifetime is specified in
yarn-site.xml and can be specified as follows for example for a lifetime
of 1 year

```xml
<property>
  <name>yarn.resourcemanager.delegation.token.max-lifetime</name>
  <value>31536000000</value>
</property>
```


The NameNode delegation token max lifetime is specified in
hdfs-site.xml and can be specified as follows for example for a lifetime
of 1 year


```xml
<property>
   <name>dfs.namenode.delegation.token.max-lifetime</name>
   <value>31536000000</value>
 </property>
```



Also, DataTorrent RTS needs the DT Gateway user (default to be
dtadmin) to be a proxy user in the Hadoop configuration when running in
secure mode.  This will enable the DT Gateway to launch applications on
behalf of the logged-in user.  Please add the following in core-site.xml
and replace \[username\] with the user running the DT Gateway:

```xml
<property>
  <name>hadoop.proxyuser.[username].groups</name>
  <value>*</value>
</property>

<property>
  <name>hadoop.proxyuser.[username].hosts</name>
  <value>*</value>
</property>
```


CLI Configuration
------------------------------



The DataTorrent command line interface is used to launch
applications along with performing various other operations on
applications.  When Kerberos security is enabled in Hadoop, a Kerberos
ticket granting ticket or the Kerberos credentials of the user is needed
by the CLI program “dtcli” to authenticate with Hadoop for any
operation. Kerberos credentials are composed of a principal and either a
keytab or a password. For security and operational reasons only keytabs
are supported in Hadoop and by extension in DataTorrent platform. When
user credentials are specified, all operations including launching
application are performed as that user.



### Using kinit



A Keberos ticket granting ticket can be obtained by using the
Kerberos command “kinit”. Detailed documentation for the command can be
found online or in man pages. An sample usage of this command is

    kinit -k -t path-tokeytab-file kerberos-principal


If this command is successful the ticket granting ticket is
obtained, cached and available for other programs. The CLI program
“dtcli” can then be started to launch applications and perform other
operations.



### Using Kerberos credentials



The CLI program “dtcli” can also use the Kerberos credentials
directly without requiring a ticket granting ticket to be obtained
separately. This can be useful in batch mode where “dtcli” is not not
launched manually and also in scenarios where running a separate program
like “kinit” is not feasible.



The credentials can be specified in the dt-site.xml configuration
file. If only a single user is launching applications the global
dt-site.xml configuration file in the installation folder can be used.
In a multi-user environment the user can use the dt-site.xml file in his
home directory. The location of this file will be $HOME/.dt/dt-site.xml
If this file does not exist the user can create a new one.



The snippet below shows the how the credentials are specified in
the configuration file. They are specified as properties.


```xml
<property>
        <name>dt.authentication.principal</name>
        <value>kerberos-principal-of-user</value>
</property>
<property>
        <name>dt.authentication.keytab</name>
        <value>absolute-path-to-keytab-file</value>
</property>
```



The property dt.authentication.principal specifies the Kerberos
user principal and dt.authentication.keytab specifies the absolute path
to the keytab file for the user.



DT Gateway Configuration
-------------------------------------

DT Gateway is a service that provides the backend functionality
for the DataTorrent UI console. Refer to [dtManage](dtmanage.md) for
details on the UI console. The DT Gateway provides real-time information
about running applications, allows changes to applications, launching
new applications among various other operations. In Kerberos secure
mode, Kerberos credentials are required for DT Gateway to operate. The
credentials should match the user that the DT Gateway service is running
as.


In a multi-user installation DT Gateway is typically running as
user “dtadmin” and the Kerberos credentials specified should be for this
user. They are specified in the dt-site.xml configuration file in the
installation folder. For a single user installation where gateway is
running as the user, the Kerberos credentials will be the user’s and
they will be specified in the dt-site.xml in the home directory location
$HOME/.dt/dt-site.xml



The snippet below shows how the credentials are specified in the
configuration file. They are specified as properties.


```xml
<property>
        <name>dt.gateway.authentication.principal</name>
        <value>kerberos-principal-of-gateway-user</value>
</property>
<property>
        <name>dt.gateway.authentication.keytab</name>
        <value>absolute-path-to-keytab-file</value>
</property>
```




dtManage Authentication
-------------------------------

Access to the UI console can be protected by having users authenticate before they can access the contents of the console.
Different authentication mechanisms are supported including local password, Kerberos and LDAP. Please refer to  
[Gateway Security](dtgateway_security.md) document on the details of how to configure this.





Run-Time Management
===================================

Unlike mapreduce the streaming applications never end. They are designed
to run 24x7. This makes that run-time management of the applications is
a very critical. The platform provides strong support for various
operations. These include

-   Runtime metrics and stats on various components of the
    application including aggregated metrics
-   Ability to change the logical plan, physical plan, and
    execution plan of the application
-   Ability to dump the current state of the application to enable
    re-launch (in case of Hadoop grid outage)
-   Integration of STRAM state with Zookeeper (in
    later versions)
-   Debugger, charting, and other tools triggered in run
    time


Dynamic Functional Modifications
---------------------------------------------

Platform support changes in application at multiple stages.
Application design parameters (attributes, and properties) can be
changed as launch time via job config file, and during runtime via
cli/webservice. The runtime change is very critical for operability as
it enables  changes to application without being forced to kill it. This
is a critical need of streaming applications, and differentiates it from
map-reduce/batch application.



From an operational perspective, the platform will allow changes
in both the logical plan (query modification, or properties
modifications), physical plan (partitioning etc.; i.e. attribute
modification), or execution plan (attribute modifications).



Examples of dynamic changes to logical plan include

-   Adding or deleting sub-dag. Some examples are

  -   Change in persistence
  -   Insertion of charts, debugger etc.
  -   Query insertion on a particular stream

-   Changing property of an operator


Any change to a logical plan will change the physical and the
execution plan. Examples of dynamic changes only to physical plan
include

-   Change in attributes that triggers STRAM to change the number
    of physical operators.
-   Runtime changes in load or grid resources (via RM, or
    outages), that triggers STRAM to change the physical plan to meet
    SLA, latency, resources usage goals
-   Direct request to change the number of partitions of
    an operator. For example new input adapters to handle expected
    uptick in ingestion rate



Any change to a physical plan will change the execution plan.
Examples of dynamic changes only to the execution plan include

-   Changes in attributes that need a new execution plan
-   Changes to stream modes
-   Node recovery from an outage

Runtime Code
-------------------------

STRAM is able to reuse and move any code that is supplied with the
initial launch of the application. The default behavior is for the jar
to include all the library templates in addition to the application
code. This enables STRAM to make changes to the application as the code
is already available.



There are some features that platform intends to support in the
future that will need STRAM to get access to new code. Examples of these
include

-   Bucket testing
-   Upgrade of an existing operator for new functionality (or
    bug fixing)
-   Addition of new models to be used by STRAM



In future these features will be enabled by the platform by
allowing a re-start of the STRAM by bouncing it without shutting down
the app.

Load
-----------------

STRAM manages runtime changes to ensure that the application
scales up and down. This includes changes in load, changes in skew,
changes in resource behavior (network goes slow) etc. STRAM proactively
monitors the application and will make run time changes as
needed.

Uptime
-------------------

Node recovery is a change in the execution plan caused by external
events (node outage) or Rm taking resources back (pre-emption). The
platform enables node recovery in three modes, namely, at least once, at
most once, and exactly once. SLA enforcement in terms of latency,
uptime, etc. is done via runtime changes.

------------------------------------------------------------------------



# Attributes

Attributes specification is the process by which operational
customization is achieved. Currently modification of attributes on an
application that is already running is not supported. We intend to add
this in future versions on an attribute by attribute basis. Attributes
are parameters that the platform recognizes and acts on and are not part
of user code. Attributes are the mechanism by which platform features
can be customized. They are specified with a key and a value. In this
section we list the attributes, their default values, and briefly
explain what they do.



There are three kinds of attributes

-   Application
-   Operators
-   Ports



For implementation details look at the [javadocs](https://www.datatorrent.com/docs/apidocs/). Some very common attributes are

-   Application: Application window, Application name, Checkpoint
    window, Container JVM options, container memory, containers, max
    count, heartbeat interval, STRAM memory, launch mode, tuple
    recording, etc.  See [Context.DAGContext](https://www.datatorrent.com/docs/apidocs/com/datatorrent/api/Context.DAGContext.html)
-   Operators: Initial partitions, checkpoint window, locality
    host, locality rack, memory, recovery attempts, stateless, storage
    agent, etc. See [Context.OperatorContext](https://www.datatorrent.com/docs/apidocs/com/datatorrent/api/Context.OperatorContext.html)
-   Ports: Queue capacity, auto_record, partition parallel, etc.
    See [Context.PortContext](https://www.datatorrent.com/docs/apidocs/com/datatorrent/api/Context.PortContext.html)



These attributes are available via Context class and can be
accessed in setup call of an operator.



Application Configuration
==========================================

Starting from RTS release 2.0.0, applications are configured through Application Packages.  Please refer to the
[Application Packages](application_packages.md) for details.


Adjusting Logging Levels  <a name="logging"></a>
===========================================

## Application Logging


Logging levels for specific classes or groups of classes can be
raised or lowered at runtime from [dtManage](dtmanage.md) application view with “Set
Log Levels” button.  Explicit class paths or patterns like like
`org.apache.hadoop.*` or `com.datatorrent.*` can be used to adjust
logging to valid log4j levels such as DEBUG or INFO.  This
produces immediate change in the logs, but does not persist across
application restarts.

For a more permanent logging levels adjustment following lines in
dt-site.xml file can be applied. To specify multiple patterns, use comma separated list.

```xml
<property>
<name>dt.loggers.level</name>
<value>com.datatorrent.*:DEBUG,org.apache.*:INFO</value>
</property>
```

DataTorrent platform full DEBUG logging can be enabled by adding
following lines to dt-site.xml configuration file.

```xml
<property>
  <name>dt.attr.DEBUG</name>
  <value>true</value>
</property>
```


## Custom log4j Properties for Application Packages

There are two ways of setting custom log4j.properties in an Apex application package

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



## dtGatway Logging

DT Gateway log level can be changed to DEBUG by settings following
environment variable before launching DT Gateway (as of version
2.0).

    export DT_GATEWAY_DEBUG=1



# Hadoop Tuning


### YARN vmem-pmem ratio tuning

After performing a new installation, sometimes the following
message is displayed while launching an application:

```
Application application_1408120377110_0002 failed 2
times due to AM Container for appattempt_1408120377110_0002_000002
exited with exitCode: 143 due to:
Container\[pid=27163,containerID=container_1408120377110_0002_02_000001\]
is running beyond virtual memory limits. Current usage: 308.1 MB of 1 GB
physical memory used; 2.5 GB of 2.1 GB virtual memory used. Killing
container.

Dump of the process-tree for container_1408120377110_0002_02_000001 :


PID PPID PGRPID SESSID CMD_NAME USER_MODE_TIME(MILLIS) SYSTEM_TIME(MILLIS) VMEM_USAGE(BYTES) RSSMEM_USAGE(PAGES) FULL_CMD_LINE

27208 27163 27163 27163 (java) 604 19 2557546496 78566
/usr/java/default/bin/java
-agentlib:jdwp=transport=dt_socket,server=y,suspend=n -Xmx768m
-XX:+HeapDumpOnOutOfMemoryError -XX:HeapDumpPath=/tmp/dt-heap-2.bin
-Dhadoop.root.logger=DEBUG,RFA
-Dhadoop.log.dir=/disk2/phd/dn/yarn/userlogs/application_1408120377110_0002/container_1408120377110_0002_02_000001
```




To Fix this `yarn.nodemanager.vmem-pmem-ratio` in yarn-site.xml should be increased from 2 to 5
or higher.  Here is an example setting:


```xml
<property>
   <description>Ratio between virtual memory to physical memory when
   setting memory limits for containers. Container allocations are
   expressed in terms of physical memory, and virtual memory usage
   is allowed to exceed this allocation by this ratio.
   </description>
   <name>yarn.nodemanager.vmem-pmem-ratio</name>
   <value>10</value>
 </property>
```
