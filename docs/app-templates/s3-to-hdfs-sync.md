# S3 to HDFS Sync App

## Summary

Ingest and backup Amazon S3 data to hadoop HDFS for data download from Amazon to hadoop. This application moves files from the configured S3 location and moves them to the destination path in HDFS. The source code is available at: [https://github.com/DataTorrent/app-templates/tree/master/s3-to-hdfs-sync](https://github.com/DataTorrent/app-templates/tree/master/s3-to-hdfs-sync).

Send feedback or feature requests to: [feedback@datatorrent.com](mailto:feedback@datatorrent.com)

This document illustrates step by step guide to launch, configure, customize
this application.

## <a name="steps_to_launch">Steps to launch application</a>

1. Click on the AppHub tab from the top navigation bar.
    ![AppHub link from top navigation bar](images/common/apphub_link.png)

1. Page listing the applications available on AppHub is displayed. Search for S3 to see all applications related to S3.
    ![AppHub search for S3](images/s3-to-hdfs-sync/apphub-search.png)
    Click on import button for "S3 to HDFS Sync App"

1. Notification is displayed on the top right corner after application package is successfully
    ![App import Notification](images/s3-to-hdfs-sync/import-notification.png)

1. Click on the link in the notification which navigates to the page for this application package.
    ![App details page](images/s3-to-hdfs-sync/app-details-page.png)
    Detailed information about the application package like version, last modified time, short description is available on this page. Click on launch button for "S3-to-HDFS-Sync" application.

1. <a name="launch-dialogue"></a>"Launch S3-to-HDFS-Sync" dialogue is displayed. One can configure name of the instance of the application after from this launch dialogue.
![Launch dialogue](images/s3-to-hdfs-sync/launch.png)

1. Select "Use saved configuration" option. This displays list of pre-saved configurations. If the application is being run in datatorrent sandbox edition, please select sandbox-memory-conf.xml. If the application is being run in cluster environment, please select cluster-memory-conf.xml.
    ![Select saved configuration](images/common/saved-conf.png)

1. Select “Specify custom properties” option. Click on “add default properties” button.
    ![Specify custom properties](images/common/specify-custom.png)

1. This expands key-value editor with mandatory properties for this application. Change the values for these properties based on your need.
    ![Properties editor](images/s3-to-hdfs-sync/property-editor.png)
    <a name="property-editor"></a>
    For example, if one wishes to copy from all the files inside `directory1` from `com.example.s3test` using `ACCESS_KEY_ID:SECRET_KEY` combination to `/user/appuser/output` on the host cluster (on which app is running):

    |name|value|
    |-|-|
    |dt.operator.HDFSFileCopyModule. prop.outputDirectoryPath|/user/appuser/output|
    |dt.operator.S3InputModule. prop.files|s3n://ACCESS_KEY_ID:SECRET_KEY @com.example.s3test/directory1 |

    Details about configuration options are available in [Configuration options](#configuration_options) section.

1. Click on ‘Launch’ button on bottom right corner to launch the application.
Notification is displayed on the top right corner after application is launched successfully. It also specifies Application ID which can be used to monitor the application and finding application logs.
    ![Application launch notification](images/common/app_launch_notification.png)

1. Click on the “Monitor” tab from the top navigation bar.
    ![Monitor tab](images/common/monitor_link.png)

1. Page with listing of all running applications is displayed. Search for launched application based on name or application id or any other relevant field. Click on the application name or id to navigate to application instance details page.
    ![Apps monitor listing](images/common/apps_monitor_listing.png)
1. Application instance details page shows key metrics for monitoring the application status."Logical" tab shows application DAG, Stram events, operator status based on logical operators, stream status, key metrics chart.
    ![Logical tab](images/s3-to-hdfs-sync/logical.png)

1. Click on the “Physical” tab to look at the status of physical instances of the operator, containers etc.
    ![Physical tab](images/s3-to-hdfs-sync/physical.png)

## <a name="configuration_options">Configuration options</a>

### Mandatory properties
End user must specify the values for these properties.

|Property|Description|Type|Example|
|-|-|-|-|
|dt.operator.HDFSFileCopyModule. prop.outputDirectoryPath|HDFS path for destination directory| String|<ul><li>/user/appuser/<br/> output/directory1</li><li>hdfs://node1.company1.com<br/> /user/appuser/output</li></ul>|
|dt.operator.S3InputModule.prop.files|Access URL for S3 source|String|s3n://ACCESS_KEY_ID:<br/>SECRET_KEY<br/>@BUCKET_NAME/<br/>DIRECTORY |

### Advanced properties
There are pre-saved configurations based on the application environment. Recommended settings for [datatorrent sandbox edition](https://www.datatorrent.com/download/datatorrent-rts-sandbox-edition-download/) are saved under sandbox-memory-conf.xml. Recommended settings for cluster environment are saved under cluster-memory-conf.xml.

|Property|Description|Type|Default for<br/>cluster-<br/>memory-<br/> conf.xml|Default for<br/>  sandbox<br/>-memory -<br/>conf.xml|
|-|-|-|-|-|
|dt.operator.S3InputModule. prop.maxReaders|Maximum number of BlockReader partitions for parallel reading.|int|16|1|
|dt.operator.S3InputModule. prop.blocksThreshold|Rate at which block metadata is emitted per second|int|16|1|

You can override default values for advanced properties by specifying custom values for these properties in the step [specify custom property](#property-editor) step mentioned in [steps](#steps_to_launch) to launch an application.

## Steps to customize the application

1. Make sure you have following utilities installed on your machine and available on `PATH` in environment variables
    - [Java](https://www.java.com/en/download/manual.jsp) : 1.7.x
    - [maven](http://maven.apache.org/download.cgi) : 3.0 +
    - [git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) : 1.7 +
    - [Hadoop]( http://www.michael-noll.com/tutorials/running-hadoop-on-ubuntu-linux-single-node-cluster/) (Apache-2.2)+

1. Use following command to clone the examples repository

    ```
    git clone git@github.com:DataTorrent/app-templates.git
    ```

1. Change directory to 'examples/tutorials/s3-to-hdfs-sync'

    ```
    cd examples/tutorials/s3-to-hdfs-sync
    ```

1. Import this maven in your favorite IDE (e.g. eclipse)

1. Change the source code as per your requirements. This application is for copying files from source to destination. Thus, Application.java does not involve any processing operator in between.

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
