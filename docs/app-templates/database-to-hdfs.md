# Database dump to HDFS application

## Summary

Ingest records from a Database table to hadoop HDFS. This application reads messages from configured MySQL table and writes each record as a comma separated line in HDFS files.

 The source code is available at:
[https://github.com/DataTorrent/examples/tree/master/tutorials/database-to-hdfs](https://github.com/DataTorrent/examples/tree/master/tutorials/database-to-hdfs).

Send feedback or feature requests to: [feedback@datatorrent.com](mailto:feedback@datatorrent.com)

This document illustrates step by step guide to launch, configure, customize
this application.

## <a name="steps_to_launch">Steps to launch application</a>

1. Click on the AppHub tab from the top navigation bar.
   ![AppHub link from top navigation bar](images/common/apphub_link.png)

1. Page listing the applications available on AppHub is displayed.
Search for Database to see all applications related to Database.
   ![AppHub search for Database](images/database-to-hdfs/apphub-search.png)

    Click on import button for "Database dump to HDFS App"

1. Notification is displayed on the top right corner after application package is successfully
   ![App import Notification](images/database-to-hdfs/import-notification.png)

1. Click on the link in the notification which navigates to the page for this application package.
   ![App details page](images/database-to-hdfs/app-details-page.png)

    Detailed information about the application package like version, last modified time, short description is available on this page. Click on launch button for "Database-to-HDFS" application.

1. <a name="launch-dialogue"></a>"Launch HDFS-line-copy" dialogue is displayed. One can configure name of the instance of the application after from this launch dialogue.
   ![Launch dialogue](images/database-to-hdfs/launch.png)

1. Select "Use saved configuration" option. This displays list of pre-saved configurations. If the application is being run in datatorrent sandbox edition, please select sandbox-memory-conf.xml. If the application is being run in cluster environment, please select cluster-memory-conf.xml.
    ![Select saved configuration](images/database-to-hdfs/saved-conf.png)

1. Select “Specify custom properties” option. Click on “add default properties” button.
   ![Specify custom properties](images/database-to-hdfs/specify-custom.png)

1. This expands key-value editor with mandatory properties for this application. Change the values for these properties based on your need.
   ![Properties editor](images/database-to-hdfs/property-editor.png)

    <a name="property-editor"></a>
    For example,  If one wishes to process all rows from table `test_event_table` from testDev database in MySQL server running on localhost port 3306. Suppose MySQL credentials are username= `root`, password=`mysql`. And one wish to write the output to `output.txt` under `/user/appuser/output` on HDFS:

    |name|value|
    |---|---|
    |dt.operator.JdbcPoller. prop.store.databaseDriver|com.mysql.jdbc.Driver|
    |dt.operator.JdbcPoller.prop.store.databaseUrl|jdbc:mysql://localhost:3306/testDev|
    |dt.operator.JdbcPoller.prop.store.password|mysql|
    |dt.operator.JdbcPoller.prop.store.userName|root|
    |dt.operator.JdbcPoller.prop.tableName|test_event_table|
    |dt.operator.JdbcPoller.prop.whereCondition||
    |dt.operator.fileOutput.prop.filePath|/user/appuser/output|
    |dt.operator.fileOutput.prop.outputFileName|output.txt|

    Details about configuration options are available in [Configuration options](#configuration_options) section.

1. Click on ‘Launch’ button on bottom right corner to launch the application.
Notification is displayed on the top right corner after application is launched successfully. It also specifies Application ID which can be used to monitor the application and finding application logs.
   ![Application launch notification](images/common/app_launch_notification.png)

1. Click on the “Monitor” tab from the top navigation bar.
   ![Monitor tab](images/common/monitor_link.png)

1. Page with listing of all running applications is displayed. Search for launched application based on name or application id or any other relevant field. Click on the application name or id to navigate to application instance details page.
   ![Apps monitor listing](images/common/apps_monitor_listing.png)
1. Application instance details page shows key metrics for monitoring the application status
   "Logical" tab shows application DAG, Stram events, operator status based on logical operators, stream status, key metrics chart.
   ![Logical tab](images/database-to-hdfs/logical.png)
1. Click on the “Physical” tab to look at the status of physical instances of the operator, containers etc.
   ![Physical tab](images/database-to-hdfs/physical.png)

## <a name="configuration_options">Configuration options</a>

### Mandatory properties
End user must specify the values for these properties.

|Property|Description|Type|Example|
|---|---|---|---|
|dt.operator.JdbcPoller. prop.store.databaseDriver|JDBC driver class. This has to be on CLASSPATH. MySQL driver is added as a dependency.|String|com.mysql.jdbc.Driver|
|dt.operator.JdbcPoller. prop.store.databaseUrl|JDBC connection URL| String|jdbc:mysql://localhost: 3306/testDev|
|dt.operator.JdbcPoller. prop.store.password|Password for Database credentials| String|mysql|
|dt.operator.JdbcPoller. prop.store.userName|Username for Database credentials| String|root|
|dt.operator.JdbcPoller. prop.tableName|Table name for input records|String|test_event_table|
|dt.operator.JdbcPoller. prop.whereCondition|Where clause condition (if any) for input records. Keep blank to fetch all records.|String||
|dt.operator.fileOutput. prop.filePath|Output path for HDFS|String|/user/appuser/output|
|dt.operator.fileOutput. prop.outputFileName|Output file name |String|output.txt|


### Advanced properties
There are pre-saved configurations based on the application environment. Recommended settings for [datatorrent sandbox edition](https://www.datatorrent.com/download/datatorrent-rts-sandbox-edition-download/) are saved under sandbox-memory-conf.xml. Recommended settings for cluster environment are saved under cluster-memory-conf.xml.

|Property|Description|Type|Default for<br/> cluster<br/>-memory<br/>- conf.xml|Default for<br/>  sandbox<br/>-memory<br/> -conf.xml|
|---|---|---|---|---|
|dt.operator.JdbcPoller. prop.partitionCount|Number of JDBC input partitions for parallel reading.|int|4|1|
|dt.operator.JdbcPoller. prop.batchSize|Batch size to read data from JDBC.|int|300|300|
|dt.operator.JdbcPoller. prop.key|Key column for the table. This will be used for partitoning of rows.|String|ACCOUNT_NO|ACCOUNT_NO|
|dt.operator.JdbcPoller. prop.columnsExpression|Key column for the table. This will be used for partitoning of rows.|String|ACCOUNT_NO, NAME, AMOUNT|ACCOUNT_NO, NAME, AMOUNT|
|dt.operator.JdbcPoller. port.outputPort.attr.TUPLE_CLASS|Fully qualified class name for the tuple class POJO(Plain old java objects) emitted by JDBC input|String|com.datatorrent.apps. PojoEvent|com.datatorrent.apps. PojoEvent|
|dt.operator.JdbcPoller. prop.pollInterval|Poll interval for scanning new records in milisec|String|1000|1000|
|dt.operator.formatter. prop.schema|Schema for CSV formatter|String|{"separator": "&#124;",<br/>"quoteChar": "\"",<br/>"lineDelimiter": "", "fields": [<br/>{<br/>"name": "accountNumber", <br/>"type": "Integer"<br/>},<br/> {<br/>"name": "name",<br/>"type": "String"<br/>},<br/>{<br/>"name": "amount",<br/>"type": "Integer"<br/>}<br/>]}|{"separator": "&#124;",<br/>"quoteChar": "\"",<br/>"lineDelimiter": "", "fields": [<br/>{<br/>"name": "accountNumber", <br/>"type": "Integer"<br/>},<br/> {<br/>"name": "name",<br/>"type": "String"<br/>},<br/>{<br/>"name": "amount",<br/>"type": "Integer"<br/>}<br/>]}|
|dt.operator.formatter. port.in.attr.TUPLE_CLASS|Fully qualified class name for the tuple class POJO(Plain old java objects) input to CSV formatter|String|com.datatorrent.apps. PojoEvent|com.datatorrent.apps. PojoEvent|

You can override default values for advanced properties by specifying custom values for these properties in the step [specify custom property](#property-editor) step mentioned in [steps](#steps_to_launch) to launch an application.

## Steps to customize the application

1. Make sure you have following utilities installed on your machine and available on `PATH` in environment variables
    - [Java](https://www.java.com/en/download/manual.jsp) : 1.7.x
    - [maven](http://maven.apache.org/download.cgi) : 3.0 +
    - [git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) : 1.7 +
    - [Hadoop]( http://www.michael-noll.com/tutorials/running-hadoop-on-ubuntu-linux-single-node-cluster/) (Apache-2.2)+

1.  Use following command to clone the examples repository

     ```
     git clone git@github.com:DataTorrent/app-templates.git
     ```

1. Change directory to 'examples/tutorials/database-to-hdfs'

    ```
    cd examples/tutorials/hdfs-line-copy
    ```

1. Import this maven in your favorite IDE (e.g. eclipse)

1. Change the source code as per your requirements. Some tips are given as commented blocks in the Application.java for this project

1. Make respective changes in the test case, properties.xml based on your environment.

1. Compile this project using maven

    ```
    mvn clean package
    ```

    This will generate application package with `.apa` extension inside target directory.

1. Go to DataTorrent UI Management console on web browser. Click on the "Develop" tab from the top navigation bar.
    ![Develop tab](images/common/develop_link.png)
1. Click on upload package button and upload the generated `.apa` file.
    ![Upload](images/common/upload.png)

1. Application package page is shown with the listing of all packages. Click on Launch button for the uploaded application package. Follow the [steps](#launch-dialogue) for launching an application.
