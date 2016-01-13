DataTorrent RTS Release Notes
========================================================================================================================

Version 3.2.0
------------------------------------------------------------------------------------------------------------------------

### New Feature

* [SPOI-6351] - Add feature to REST API to get queue information from cluster

### Improvement

* [SPOI-5777] - Kafka start offset should have user option to read from latest or earliest
* [SPOI-5828] - Stackstraces should not be shown on errors
* [SPOI-6641] - Implement "forever" bucket in DimensionComputation
* [DTIN-40] - Observed unused variables in SplunkBytesInputOperator
* [DTIN-69] - Move Query Operators implementation to newer one
* [DTIN-50] - [dtIngest] add parameter "parallel readers"

### Bug

* [SPOI-5104] - Ingestion: Failed to copy data when inputs include a directory and a subdirectory
* [SPOI-5216] - FileSplitter fails with ConcurrentModificationException
* [SPOI-5571] - S3 : Copying data failed with RuntimeException saying 'Unable to move file'
* [SPOI-5809] - Kryo Exception In Stateful Stream Codec When Operator Is Killed From UI and Comes Back Up
* [SPOI-5823] - Downstream container falling behind when buffer spooling is enabled
* [SPOI-5899] - Ability to retrieve schemas from an app package
* [SPOI-6053] - Schema Generator - bool getter should be isBool and not getBool
* [SPOI-6073] - AbstractFileOutputOperator not finalizing the file after the recovery
* [SPOI-6079] - Installation wizard: 'continue' button is misplaced in last step of installation
* [SPOI-6098] - 'single run' doesnt work
* [SPOI-6202] - Sandbox 3.1 has community license instead of enterprise
* [SPOI-6204] - Sandbox 3.1 loses uploaded license after reboot
* [SPOI-6222] - HDFS recovery in sandbox causes license to degrade to community
* [SPOI-6236] - Add 1s aggregations to App Data Tracker
* [SPOI-6298] - Dimensions Store Can Become Blocked
* [SPOI-6383] - Sometimes expired query is still executed.
* [SPOI-6393] - Markdown code blocks render with invalid syntax highlights in console
* [SPOI-6446] - Merge PojoEnrichment and TupleEnrichment
* [SPOI-6505] - Exceptions from asm when uploading apps
* [SPOI-6603] - Warning messages shown on console are not completely visible
* [SPOI-6709] - Temporarily Remove Methods Which Override Their Return Type In MEGH From Semver Checks
* [SPOI-6846] - DT dashboard guide link is not working
* [SPOI-6855] - Broken links observed on summary page while DT RTS configuration 
* [SPOI-6856] - Correct docs index.html links and title
* [DTIN-51] - bandwidth option was removed during merge
* [DTIN-101] - For message-based-input to message-based-output, compression & encryption options should not be visible on config UI
* [DTIN-102] - [Ingestion UI] If kafka as output type, then Brokerlist is the configuration parameter, not zookeeper quorum
* [DTIN-112] - Message based input to FTP output fails with IOException while appending the data
* [DTIN-113] - Kafka input to kafka output fails in MessageWriter with EOFException while fetching output topic metadata
* [DTIN-123] - All files are not getting copied when bandwidth option is specified
* [DTIN-124] - For kafka to hdfs, if offset is set to 'Earliest', messages are not consumed from the beginning
* [DTIN-126] - 'Compact files' option should be disabled for message based Input type
* [DTIN-129] - StreamCorruptedException while decrypting AES/PKI encrypted file
* [DTIN-130] - Text box for 'Bandwidth to use' should accept integer values only
* [DTIN-155] - Messages are dropped when bandwidth option is enabled
* [DTIN-160] - Copying data from S3 to HDFS fails with NoSuchMethodError
* [DTIN-161] - Message based input to S3N output fails with IOException while appending the data
* [DTIN-162] - JMS messages are not fully consumed in case of JMS to kafka
* [DTIN-164] - Data values in 'Table' widget flicker when encryption is enabled
* [DTIN-165] - Data source names for dtingest should not contain 'null'
* [DTIN-174] - Append doesn't work for S3, FTP filesystems and ObjectOutputStream
* [DTIN-176] - Parallel read is not working in case of FTP and S3 as input
* [DTIN-186] - FileMerger failed with unable to merge file exception

### Task

* [SPOI-5173] - DAG validation: Attribute values Serializable
* [SPOI-5403] - Ingestion Splunk integration
* [SPOI-5801] - Make a MapR partner (datatorrent) sandbox
* [SPOI-5958] - dtView Integration for ingestion metric visualization
* [SPOI-6241] - Change in enterprise license
* [SPOI-6439] - Run benchmark for 3.2.0 release
* [SPOI-6691] - Decouple malhar version from dt version in dtingest pom dependancies
* [DTIN-20] - Accept bandwidth limit in units other than byes/s in dtingest script
* [DTIN-38] - Needs to check the Query frequency option is available for Splunk Input Operator
* [DTIN-47] - Merge code from release-1.0.1 branch to ingegration-1.1.0 branch
* [DTIN-54] - Disabling the splunk from dtIngest script
* [DTIN-71] - Integrate release 1.0.1 branch with integration-1.1.0


### Sub-task

* [SPOI-5369] - Integrate schema support in Cassandra Input/Output
* [SPOI-5437] - Create Jdbc Pojo input operator and integrate schema support in Jdbc POJO input/output
* [SPOI-5819] - Bandwidth control for file based sources
* [SPOI-5820] - Bandwidth control for message based sources
* [SPOI-5959] - Metrics for compression, encryption
* [SPOI-6337] - Expose bandwidth metrics
* [SPOI-6441] - Change console home page to be welcome screen instead of operations summary



Version 3.1.1
------------------------------------------------------------------------------------------------------------------------

### Improvement

* [SPOI-5828] - Stackstraces should not be shown on errors

### Bug

* [SPOI-5786] - AppDataTracker Custom Metric Store Deadlock
* [SPOI-6032] - App Builder should not show property from super class
* [SPOI-6049] - DimensionStoreHDHT Should always set meta data on aggregates in processEvent, even if the aggregate is received in a committed window.
* [SPOI-6073] - AbstractFileOutputOperator not finalizing the file after the recovery
* [SPOI-6090] - Ingestion: Error decrypting files for message based sources
* [SPOI-6147] - Launch issue with "Starter Application Pack"
* [SPOI-6202] - Sandbox 3.1 has community license instead of enterprise
* [SPOI-6203] - -ve Memory reported for Application Master
* [SPOI-6204] - Sandbox 3.1 loses uploaded license after reboot
* [SPOI-6222] - HDFS recovery in sandbox causes license to degrade to community
* [SPOI-6286] - App Data Tracker Number Format Exception In Idempotent Storage Manager
* [SPOI-6304] - Fix netlet dependency
* [SPOI-6313] - Work Around APEX-129
* [SPOI-6333] - RandomNumberGenerator in apex-app-archetype does not use numTuples property

### Task

* [SPOI-5755] - Gateway should show "HDFS is not up yet"
* [SPOI-6148] - Update website with release 3.1
* [SPOI-6241] - Change in enterprise license


Version 3.1.0
------------------------------------------------------------------------------------------------------------------------

### New Feature
* [SPOI-4670] - Enable message schema management in App Builder
* [SPOI-5844] - Retrieve older versions of schemas

### Improvement
* [SPOI-5611] - Simplify PubSub operators to supply Gateway connect address URI by default

### Bug
* [SPOI-4380] - MxN unifier not removed when partition is removed from physical plan.
* [SPOI-5338] - Cleanup OperatorDiscoverer class to remove reflection and use ASM
* [SPOI-5582] - Ingestion: Fails with "Unable to merge file" with FTP as destination
* [SPOI-5697] - Unable to launch ingestion app through Ingestion wizard
* [SPOI-5743] - App package import also needs to do the typegraph stuff as upload
* [SPOI-5831] - Add getter for properties for Twitter Demo
* [SPOI-5833] - Schema class not loaded during validation
* [SPOI-5841] - e2e files being added to app/index.html with gulp inject:scripts
* [SPOI-5857] - Gateway has trouble getting to STRAM until after restart
* [SPOI-5943] - chicken and egg problem for entering kerberos credentials data to dt-site.xml
* [SPOI-5946] - Port compatibility when port require schemas
* [SPOI-6002] - AppBuilder fails to load operator due to NullPointerException

### Task
* [SPOI-5307] - Mocha based tests for Gateway API calls
* [SPOI-5749] - Certify MapR sandbox
* [SPOI-5750] - Create Splunk forwarder operators
* [SPOI-5751] - Create splunk forwarder input operator
* [SPOI-5752] - Create splunk forwarder output operator
* [SPOI-5753] - Create splunk forwarder configuration specification
* [SPOI-5754] - Change node1 twitter demos settings to 5 mins in node1 conf demo conf file
* [SPOI-5755] - Gateway should show "HDFS is not up yet"
* [SPOI-5756] - Test license expiry on sandbox as part of sandbox testing
* [SPOI-5764] - Gateway to show better error messages on all 500 errors
* [SPOI-5803] - Support of custom aggregation for ADT
* [SPOI-5893] - Changes for retrieving container and operator history information

### Sub-task
* [SPOI-4946] - Handle new @useSchema and @description property metadata in UI
* [SPOI-4980] - Schema Management in the UI
* [SPOI-5505] - handle Object-to-Object port compatibility with and without schema
* [SPOI-5506] - handle Object-to-Pojo port compat with schema
* [SPOI-5513] - handle port compatibility with generic type ports
* [SPOI-5747] - Automatically generate new eval license when sandbox starts up


Version 3.0.0
------------------------------------------------------------------------------------------------------------------------

### Sub-task
* [SPOI-1901] - Dynamic property changes lost on AM restart 
* [SPOI-4820] - Add an api call to retrieve all the application, operator and port attributes available for the app-package
* [SPOI-4891] - Example for schema meta data and property doclet tag
* [SPOI-4968] - Capture @useSchema and @description doclet tags from docblocks
* [SPOI-4972] - Design Schema API for managing schemas
* [SPOI-4973] - Create a Schema resource which will contain schema calls
* [SPOI-4987] - Generate pojo class using schema provided in json
* [SPOI-4999] - Implement the rest call to save schema on the backend
* [SPOI-5211] - Support custom visualization link
* [SPOI-5237] - Type of attributes are wrong when it is an inner class or enum
* [SPOI-5357] - LogicalNode may swallow END_STREAM message in catchUp
* [SPOI-5361] - Button for dt.phoneHome.enable property on system config page
* [SPOI-5527] - Implement Queue Option


### Bug
* [SPOI-4321] - Datatorrent Core Trigger Jenkings Job hangs
* [SPOI-4633] - Resolve type variable across the type hierarchy 
* [SPOI-4789] - Time calculated from window Id using WindowGenerator.getMillis is incorrect at times 
* [SPOI-4884] - Intermittent failure for CustomMetricTest
* [SPOI-4896] - Kafka operator stop consuming from kafka cluster after it is restarted.
* [SPOI-4941] - For kafka operator in app builder certain properties need to be set twice
* [SPOI-5006] - If incompatible change made in platform, we need to recompute the typegraph automatically
* [SPOI-5074] - Code/fix code that leads to classloader leaks in Gateway
* [SPOI-5087] - Bucket ID Tagger In app data tracker has very high latency
* [SPOI-5323] - Malhar operators are not packaged with distribution for 3.0
* [SPOI-5359] - License Type, License ID, and Features should not just be empty on LicenseInfo page
* [SPOI-5360] - When license upload fails with no message, install wizard should not have an unaddressed colon
* [SPOI-5379] - NoClassDefFoundError due to indirect reference to dt-common classes
* [SPOI-5385] - No error message is returned when DTCli gets an NPE
* [SPOI-5389] - Support for RM and HDFS delegation token renewal in secure HA environments
* [SPOI-5433] - Asm code not working for jdk 1.8
* [SPOI-5469] - Datatorrent DTX trigger Jenkins Job fails on timeout
* [SPOI-5472] - Undeploy heartbeat requests are not processes if container is idle
* [SPOI-5484] - Ingestion FTP as output does not work with vsftpd
* [SPOI-5497] - Could not open pi demo in 3.0.0 RC2
* [SPOI-5498] - Typegraph exception with 3.0.0 RC2
* [SPOI-5500] - Saving an app whose streams have an assigned schema (not handwritten java class) fails with 404
* [SPOI-5504] - Make temporary file names unique to avoid lease expiry
* [SPOI-5530] - Failed to edit pidemo JSON based application
* [SPOI-5536] - App jar is missing from typegraph
* [SPOI-5552] - Non-concrete classes being returned with assignableClasses call
* [SPOI-5562] - Boolean Operator Property Values Are Blank In the Operator Properties Table
* [SPOI-5569] - Launching AdsDimensionsDemoGeneric fails with ClassNotFoundException 
* [SPOI-5577] - Sometimes CustomMetrics Store Returns No Data When There is Data
* [SPOI-5578] - Sometimes Custom Metrics Data Source Is Not Accessible From Widgets
* [SPOI-5582] - Ingestion: Fails with "Unable to merge file" with FTP as destination
* [SPOI-5583] - DFS root directory check is failing on MapR cluster
* [SPOI-5593] - App Builder search tooltip
* [SPOI-5597] - Bad log level WARNING in UI
* [SPOI-5604] - Pressing "Enter" in newDashboardModal closes the modal
* [SPOI-5607] - Sales Enrichment operator needs to be recovered and added to Sales Dimensions demo
* [SPOI-5612] - AppBuilder can not deserialize instance of java.net.URI with PubSubWebSocketAppData operators
* [SPOI-5627] - error message from install script from 3.0.0-RC4 
* [SPOI-5628] - Update dt-site of sandbox for new Sales demo enrichment operator
* [SPOI-5629] - Data visualization links broken with APPLICATION_DATA_LINK 
* [SPOI-5632] - If there are no uncategorized operators, dont show an uncategorized group
* [SPOI-5636] - dtcp is not getting packaged in installation (RC4)
* [SPOI-5637] - Allatori Configuration errors in ingestion pom.xml
* [SPOI-5640] - dtcp: When invalid value is provided for scan interval no error is thrown by dtcp, just exits out
* [SPOI-5643] - When An Application Is Restarted Under A Different User Name Custom Metrics Data is Not Saved.
* [SPOI-5644] - isChar validation should strip \u000 character
* [SPOI-5646] - Megh demos is failing release build
* [SPOI-5647] - launchPkgApplicationDropdown tries to push an alert to scope.alerts, which is undefined
* [SPOI-5653] - When Gateway Restarts App Data Tracker It Should Do It Using HA Mode
* [SPOI-5655] - If gateway fails to launch (e.g., port 9090 is in use), installer should inform user
* [SPOI-5656] - Update Bucket ID Tagger To use only user name for determining bucket Ids
* [SPOI-5661] - Set default store in HDHTReader
* [SPOI-5662] - Improve defaults of Enrichment Operator In Sales Demo
* [SPOI-5664] - Omit Aggregator Registry From UI
* [SPOI-5672] - App Data Tracker Compliation is failing
* [SPOI-5673] - Unable to launch ingestion app with JMS as input source 
* [SPOI-5675] - Kafka keys population error
* [SPOI-5676] - Fix API doc generation
* [SPOI-5685] - Complete App Builder category and property name fixes
* [SPOI-5688] - Correct interactive demo tutorials available in the Learn section
* [SPOI-5689] - Installer produces error message about removing docs directory
* [SPOI-5690] - Images missing from lean section tutorials after installing release build
* [SPOI-5693] - Console does not upload default DT application packages
* [SPOI-5697] - Unable to launch ingestion app through Ingestion wizard
* [SPOI-5704] - App package references in docs
* [SPOI-5705] - Build version incorrect
* [SPOI-5706] - api and user docs not viewable through gateway
* [SPOI-5707] - Packaging utilities jar in Ingestion
* [SPOI-5708] - Update netlet dependency to release for 3.0
* [SPOI-5712] - Unable to launch dtingest app using dtingest command line utility but able to launch via UI


### Improvement
* [SPOI-4513] - Expose app data tracker stats as "pseudo-datasource" for each application
* [SPOI-4889] - Make BucketIdTagger fault tolerant
* [SPOI-5320] - License URL should open in new window 
* [SPOI-5494] - Support "queue" query parameters from launch app modal
* [SPOI-5535] - Console should validate duplicate app name in the same app package
* [SPOI-5548] - Check compaction keys from UI
* [SPOI-5603] - Add syntax highlighting to Markdown code blocks
* [SPOI-5611] - Simplify PubSub operators to supply Gateway connect address URI by default
* [SPOI-5623] - License upgrade link should open in separate tab
* [SPOI-5633] - Improve markdown content display styles
* [SPOI-5657] - Redirect to welcome screen of the Learn section after install
* [SPOI-5694] - Ingestion default app-config should populate meaningful defaults


### New Feature
* [SPOI-4672] - Support for secure HA environments
* [SPOI-5288] - Add "launch" button to each item in the list of app packages
* [SPOI-5304] - Support ingestion install mode
* [SPOI-5313] - Obfuscate ADT in the distribution build
* [SPOI-5561] - Markdown documentation support in the Console


### Task
* [SPOI-4228] - The location of App Data Tracker from installation and from devel mode
* [SPOI-4658] - App Data Tracker Technical Doc
* [SPOI-4879] - Hide operators that have no input ports from App builder
* [SPOI-4983] - Installer for Ingestion app
* [SPOI-4984] - Obfuscate ingestion jar
* [SPOI-5029] - Move new x-java dependencies in appDataFramework branch to core
* [SPOI-5032] - Review comparison for appDataFramework pull request to the master
* [SPOI-5050] - Licensing-related changes to the UI for 3.0
* [SPOI-5255] - Support enhancements to uiTypes
* [SPOI-5314] - Include obfuscated App Data Tracker in the install bundle
* [SPOI-5370] - Megh obfuscation
* [SPOI-5502] - Allatori obfuscates operator class names even config has keep-name on class * implements com.datatorrent.api.Operator
* [SPOI-5555] - [dtcp] set default app package for ingestion
* [SPOI-5574] - Update installer README
* [SPOI-5608] - Docs for backward compatibility in 3.0 
* [SPOI-5610] - Add testing to Markdown support models, pages, directives
* [SPOI-5621] - Include Ingestion utilities in DT installer
* [SPOI-5624] - [Ingestion] Hide message output destination when input is file source
* [SPOI-5635] - Changing product name to dtIngest
* [SPOI-5638] - Post ingestion packge to central DT maven repository
* [SPOI-5639] - App Data Tracker Release Job
* [SPOI-5645] - support "short" primitive type in app builder
* [SPOI-5658] - Dummy ticket for Apex-17 - Change CustomMetric annotation to AutoMetric and enhancements


### Bug
* [MLHR-1726] - Bug in PojoUtils
* [MLHR-1742] - Create a wrapper method in POJOUtils that returns the appropriate getter for primitives
* [MLHR-1752] - PojoUtils create/constructSetter does not handle boxing/unboxing
* [MLHR-1756] - Exclude hadoop-common and other hadoop libraries from application
* [MLHR-1789] - Complete Category and property name fixes


### Improvement
* [MLHR-1725] - Add Support for Setters to PojoUtils
* [MLHR-1757] - change scope of dt-engine in maven build


Version 2.1.0
------------------------------------------------------------------------------------------------------------------------

### Bug
* [SPOI-3732] - Get User Info APIs creates users
* [SPOI-3816] - Ingestion UI: Node server should store pipelines on hdfs rather than local filesystem
* [SPOI-3820] - Ingestion UI: Rest calls to gateway from Node server fails
* [SPOI-3845] - BlockSynchronizer  sometimes misbehaves when BlockReader is killed. 
* [SPOI-3862] - Ingestion UI - left/right margins have no width
* [SPOI-3876] - Review the changes done to DimensionsComputation for HadoopWorld Demo
* [SPOI-3940] - Demo app package version stuck at v1.0-SNAPSHOT
* [SPOI-4029] - PiJavaScript demo pi calc operator fails to re deploy
* [SPOI-4067] - Launch of ingestionApp using DTCP is failing
* [SPOI-4070] - Stray directory /opt/datatorrent/current/datatorrent  is created after installation.  
* [SPOI-4077] - Ingestion UI: Create option to scan the directory recursively
* [SPOI-4079] - Gateway does not retain listen address specified during installation
* [SPOI-4080] - Gateway guard hides errors with restarts
* [SPOI-4081] - Ingestion UI: pipeline table doesn't auto refreshes
* [SPOI-4085] - UI: wrong application selection after sorting in pipeline instances table
* [SPOI-4087] - Relaunch functionality keeps relaunching multiple apps
* [SPOI-4094] - Ingestion app tests failing and empty directory getting created under target that are not removed
* [SPOI-4128] - Need to explain difference between properties & state holding data structure
* [SPOI-4175] - Remove directory prop from base block reader and ftp block reader from ingestion 
* [SPOI-4229] - committed function not getting invoked in local mode
* [SPOI-4352] - App Builder uiType not present for several classes
* [SPOI-4362] - Remove dependencies on DirectoryScanner from OperatorDiscoverer when used in stram
* [SPOI-4691] - DT console shows negative memory size for killed application
* [SPOI-4702] - IndexOutOfBoundsException in Stram due to counters in AbstractBlockReader


### Improvement
* [SPOI-3592] - Clean up appInstance widget definitions
* [SPOI-3783] - Remove gateway port automatic re-selection on startup feature
* [SPOI-3932] - demos ui references web services v1
* [SPOI-3944] - Ingestion UI : Display pipelines progress
* [SPOI-3945] - UI: Add multiple input support
* [SPOI-3946] - Create an auto scaling scheme for the Block Reader and Writer 
* [SPOI-4003] - Ingestion app: add a feature to re-try failed blocks
* [SPOI-4026] - Aggregated counters are not published via web-socket in the logical operators topic
* [SPOI-4048] - Block application launch during critical system issues
* [SPOI-4078] - Gateway address argument validation during installation and launch
* [SPOI-4551] - Enhance Gateway API to return AppIDs for a given application name
* [SPOI-4578] - Allow supporting archive jars in configuration definition for app packages
* [SPOI-4728] - Support -originalAppId when launching apps through the DT Gateway API
* [SPOI-4751] - Upgrade sniffer maven plugin to the latest version


### New Feature
* [SPOI-3028] - [HDHT] Hive Interoperability
* [SPOI-3029] - [HDHT] Export to ORC Format
* [SPOI-4050] - AppData UI Dashboard page
* [SPOI-4093] - Ingestion UI: Control for triggering scan of files
* [SPOI-4636] - Added $? feature in dtcli and use it in CLIProxy
* [SPOI-4718] - CLI commands to support variable arguments


### Task
* [SPOI-3242] - Rethrow the exceptions being caught in catch block of operators.
* [SPOI-3502] - Create the landing page for the UI of ingestion application
* [SPOI-3504] - [Ingestion UI] Create views for creating a pipeline and its description
* [SPOI-3762] - Provide installation version option for installer
* [SPOI-3763] - Update document export tokens
* [SPOI-3870] - Implement transformation functions for rainier poc1
* [SPOI-3871] - Filter records based field values for rainier poc1
* [SPOI-3872] - Generate audit and bad record logs for rainier poc1
* [SPOI-3970] - Ingestion UI : Use the console package 
* [SPOI-3981] - Remove unused imports
* [SPOI-4040] - Add an operator that keeps track of failed files
* [SPOI-4122] - [UI] : Display list of skipped files on UI when overwrite flag is false
* [SPOI-4172] - After effects of removing threshold property from BlockReader in ReaderWriter partitioner/stats-listener  
* [SPOI-4369] - [AppData][AppDataTracker] Deserializer operator 
* [SPOI-4385] - Create metrics aggregators - sum, min, max, count
* [SPOI-4544] - Custom metrics can be cumulative or per window which can be statically declared by the operator developer
* [SPOI-4653] - Create Aggregators registry in AppDataTracker
* [SPOI-3767] - Auto scaling of BlockReader using partitioning
* [SPOI-4748] - Add data query to custom metrics store


### Bug
* [MLHR-1614] - AbstractFSWriter in append mode is not fault-tolerant
* [MLHR-1620] - Remove close file from AbstractFSWriter
* [MLHR-1637] - Cleanup skipping of records from setup of FSDirectoryInputOperator 
* [MLHR-1643] - FileSplitter recovery fails
* [MLHR-1644] - Add Mock Server Libraries in unit tests of database/key value store operators
* [MLHR-1653] - Remove JavaScriptOperatorBenchMark form library
* [MLHR-1656] - AbstractFileOutputOperator LeaseExpired exception when cache reaches its threshold
* [MLHR-1668] - Stateless Partitioner in case of parallel partition ignores parallel partition count (except the first time define partitions is called)
* [MLHR-1687] - AbstractBlockReader threshold breaks the idempotency
* [MLHR-1708] - Duplicate data read from kafka if kafka partitions are less than DT partitions
* [MLHR-1712] - The directory under which the idempotent state is stored should be relative to the app directory so that the state is copied on relaunch
* [MLHR-1723] - FTPStringInputOperatorTest fails on Windows OS


### Improvement
* [MLHR-1547] - Integration of Idempotent storage manager to Directory scanner
* [MLHR-1621] - Parititon Couchbase Output Operator
* [MLHR-1632] - Add couchbase mock to couchbase tests.
* [MLHR-1634] - Improve the BlockReader partitioning scheme to accommodate ingestion rate
* [MLHR-1641] - Improve the BlockReader
* [MLHR-1661] - Ability to override the stream-codec of input port in AbstractFileOutputOperator
* [MLHR-1684] - Improve file splitter not to emit all files  in one shot and hold scanned file names in memory
* [MLHR-1694] - BasicCounters improvements

### New Feature
* [MLHR-1355] - Supports secure hadoop cluster in the installer
* [MLHR-1497] - Operators for ElasticSearch
* [MLHR-1578] - UI Auth: UI to show different tabs and/or buttons for different user permissions


Version 2.0.1
------------------------------------------------------------------------------------------------------------------------

### Bug
* [SPOI-4379] - Operator removed from physical plan due to invalid SHUTDOWN status
* [SPOI-4381] - Queue size missing on physical operator page 
* [SPOI-4382] - queueSize port metric reports bogus values
* [SPOI-4384] - Recovery fails due to corrupted checkpoints.
* [SPOI-4437] - DTCli not recognizing $HOME variable set

### Improvement
* [SPOI-4728] - Support -originalAppId when launching apps through the DT Gateway API
* [SPOI-4390] - Replace 'start time' on console to 'Up time'


Version 2.0.0
------------------------------------------------------------------------------------------------------------------------

### Bug
* [SPOI-4046] - Gateway /containers?states={state} call returns erroneous state information
* [SPOI-4057] - License can not be upgraded to Evaluation / Production License
* [SPOI-4037] - CONTAINERS_MAX_COUNT in sandbox prevents demos launch from dtcli
* [SPOI-4008] - HDHT Error while flushing write cache
* [SPOI-3837] - Partitioner interface semantics broken in 2.0.0 physical plan implementation]
* [SPOI-3901] - twitter demo app package launch throws NoClassDefFoundError
* [SPOI-3900] - Gateway gets 400 error when phone home
* [SPOI-3922] - dtcli does not show output port attributes.
* [SPOI-3934] - DT CLI Needs to validate user inputs
* [SPOI-3054] - # Of Tuples Produced != Number Of Tuples Output By Unifier When Repartitioning
* [SPOI-3210] - HDHT DTFile reader bug
* [SPOI-3340] - Settings in ~/.dt/dt-site.xml don't override app package defaults
* [SPOI-3349] - Can we document how to enable password security in gateway
* [SPOI-3365] - Launch App Package does not honor -local option
* [SPOI-3369] - Implement the pam authentication as a hadoop authentication handler
* [SPOI-3396] - launch command should be able to specify local conf file when launching app package
* [SPOI-3397] - DT Gateway doesn't start on Mapr 4.0.1
* [SPOI-3402] - Checking the UID for Dtadmin
* [SPOI-3419] - KafkaAdsDimensionsDemo demo available with installer fails
* [SPOI-3420] - Installation issues on HDP 2.2
* [SPOI-3469] - gateway, dtcli fail to start in development mode
* [SPOI-3503] - AppPackage tests produce 100+GB files
* [SPOI-3522] - MaxEventsPerSecond for Flume Ingestor should adjust for partitioned instances
* [SPOI-3528] - Installer does not show relevant error if nonexistent env file passed as argument and finishes silently with defaults
* [SPOI-3548] - browser inconsistencies with table
* [SPOI-3550] - Confusing Breadcrumb navigation on Application Page
* [SPOI-3555] - Unifier names should not be links to nonexistent pages
* [SPOI-3594] - Systems Diagnostic produces conflicting results for Hadoop installation
* [SPOI-3595] - Correctly Implement the clone method in platform.
* [SPOI-3608] - User Profile and User Management should not show when auth is disabled
* [SPOI-3613] - RBAC Configuration screen is completely missing after recent changes
* [SPOI-3628] - Pubsub websocket auth not working with kerberos frontend authentication
* [SPOI-3638] - Cant assign roles to user in console
* [SPOI-3644] - Develop Tab Can not be seen on naviagation bar 
* [SPOI-3646] - Error creating new config xml file in package
* [SPOI-3647] - MR Operator demo throws null pointer exception
* [SPOI-3648] - Cant add admin permissions to existing roles
* [SPOI-3654] - In passwd policy user can not change own password using ui console
* [SPOI-3657] - Can't Launch Apps Using ui console if user is not the same as dtgateway user
* [SPOI-3663] - modify certification scripts and gateway proxy to upload demo jars from repackaged malhar demos
* [SPOI-3665] - DataTorrent logo link broken in console
* [SPOI-3670] - Update DTCliTest to create app package like AppPackageTest.java
* [SPOI-3672] - Uploaded license not used when launching app
* [SPOI-3674] - License info not updated after license upload until page reload
* [SPOI-3675] - Display Error in Sandbox. License Manager Error:null
* [SPOI-3682] - doubleclick select active kills containers
* [SPOI-3684] - Gateway deletes JSON app silently (no error) on PUT
* [SPOI-3685] - Error message in launch app modal is not red
* [SPOI-3686] - Launch properties do not get sent with the launch request
* [SPOI-3689] - AppPackages APIs give 404 not found messages
* [SPOI-3690] - APIs falsely report role assignments
* [SPOI-3691] - API /ws/v1/config/hadoopInstallDirectory does not work
* [SPOI-3708] - Gateway shows License error after license agent gets back to normal
* [SPOI-3710] - Sandbox packaging invalid due to HDFS dependency
* [SPOI-3712] - Exclamation point in DT cli tries to expand "event"
* [SPOI-3713] - When CLI has a problem running a CLIProxy command, there is out of memory error from the gateway
* [SPOI-3714] - Launch button from other screens should bring up launch modal
* [SPOI-3716] - locality performance benchmarks operators failing with OOM exception
* [SPOI-3717] - Insufficient license memory for Node Local Performance benckmark application
* [SPOI-3718] - change high availability certification benchmarking to compare number of active containers instead of total number of containers
* [SPOI-3720] - License manager not found returned from Gateway even though it returns valid license including agent info
* [SPOI-3721] - Changes to XMLConfig to incorporate changed properties
* [SPOI-3725] - NullPointerException in Certification-initDemo for PerformanceBenchmarkForFixedNumberOfTuples
* [SPOI-3729] - Thread local validation failure for multiple ports between two operators
* [SPOI-3732] - Get User Info APIs creates users
* [SPOI-3733] - Can't Launch Apps Using UI or gateway APIs in kerberos environment
* [SPOI-3734] - Remove macro from cli  for application or add relevant application
* [SPOI-3754] - Gateway can only restore roles once

### Improvement
* [SPOI-2036] - Ensure that definePartitions and partitioned are called for parallel partitioned operators
* [SPOI-2955] - Provide tool-tip capability to RTS UI
* [SPOI-3194] - Support PAM authentication mechanism as an agent for LDAP
* [SPOI-3304] - Reorganize code to ensure easy consumability
* [SPOI-3345] - Delete OperatorContext.PartitionTPSMax and .PartitionTPSMin 
* [SPOI-3346] - Delete OperatorContext.InitialPartitionCount
* [SPOI-3366] - Update Eval license for RTS 2.0
* [SPOI-3401] - Switch installer, gateway, console from using HADOOP_PREFIX to hadoop executable
* [SPOI-3404] - Provide support for viewing/collecting YARN logs across the cluster
* [SPOI-3415] - Remove defaults from dt-site.xml and add version
* [SPOI-3418] - Remove dependency on /etc/datatorrent
* [SPOI-3447] - Partitioning of couchbase input operator
* [SPOI-3525] - Messages shown in installer and uninstaller are longer than 80 characters
* [SPOI-3554] - Log-Level Setter for angular
* [SPOI-3626] - appPackageDisplayName in /ws/v1/appPackages
* [SPOI-3667] - Confirmation box to shutdown or kill apps should have "warm" colors
* [SPOI-3668] - DTGateway logs are flooded with permission WARN logs
* [SPOI-3694] - Populate launch properties with required properties of app
* [SPOI-3697] - Add content-disposition so that app package download has a reasonable file name when downloaded from browser
* [SPOI-3698] - Support URI codec out the box so that UI can set URI operator properties
* [SPOI-4066] - Portable environment settings across releases

### New Feature
* [SPOI-3393] - Track recordings by a generated ID rather than startTime
* [SPOI-3422] - Restore default roles with backend
* [SPOI-3683] - Add download button to app package
* [SPOI-3753] - "Reset to Defaults" for user roles

### Task
* [SPOI-3927] - Support per application configuration defaults and required properties
* [SPOI-2809] - Implement password authentication as a hadoop authentication type
* [SPOI-3115] - Update document with password authentication once UI supports user mgmt
* [SPOI-3239] - HDHT store removal support
* [SPOI-3351] - Abstract the reconciler used in Guava and Rainier to malhar
* [SPOI-3368] - Configuration handling on major version upgrade
* [SPOI-3371] - CLI to doAs the user specified by HADOOP_USER_NAME if security is enabled
* [SPOI-3372] - Gateway REST service to only return rows the user is authorized to view
* [SPOI-3373] - Gateway Websocket service to only publish to subscribers with info individual subscribers are authorized to view
* [SPOI-3374] - Gateway to return 403 Forbidden for resources the user is not authorized to view or operations the user is not authorized to perform
* [SPOI-3375] - Gateway support for permission based authorization
* [SPOI-3376] - Gateway REST call to show what permissions the current user has
* [SPOI-3377] - Gateway REST call to support role and permission management
* [SPOI-3378] - HTTP Header auth support in Gateway 
* [SPOI-3381] - Implement Kerberos group to role mapping
* [SPOI-3385] - Gateway ACL support at the application level
* [SPOI-3390] - LDAP/AD support in Gateway
* [SPOI-3405] - Implement Kerberos security context and security context filter in Gateway
* [SPOI-3443] - Ingestion Application repo and package
* [SPOI-3472] - Installer testing
* [SPOI-3485] - Console repository relocation
* [SPOI-3486] - Create HDHT section in Application Developer Guide
* [SPOI-3517] - Document JVM_OPTIONS and QUEUE_NAME features in user docs
* [SPOI-3519] - Add PAM auth user docs
* [SPOI-3520] - Update RBAC user docs
* [SPOI-3521] - Console user docs updates
* [SPOI-3536] - Create hdfs output operator to write table files
* [SPOI-3537] - write hdfs writer for small files to copy to vertica
* [SPOI-3538] - Combine small file writer with vertica writer
* [SPOI-3540] - Sandbox updates to support app package launches from console
* [SPOI-3593] - Clean up import functionality for demo apps
* [SPOI-3610] - Implement RBAC features for App Packages
* [SPOI-3619] - Update console for the new app package REST API
* [SPOI-3627] - Convert our REST API from v1 to v2 as we have made some backward incompatible changes in the REST API
* [SPOI-3631] - Test HDHT recovery
* [SPOI-3632] - Upgrade and test demos on 2.0.0
* [SPOI-3633] - Set certain sensitive permissions "admin" role only
* [SPOI-3634] - Allow default app instance and app package permissions for each user
* [SPOI-3635] - Remove INITITAL_PARTITION_COUNT from demo app pkg properties
* [SPOI-3636] - Upgrade and test demos on 2.0.0
* [SPOI-3650] - Test demos on sandbox on dt 2.0.0
* [SPOI-3651] - benchmarks for dt 2.0.0
* [SPOI-3652] - list of current benchmarks
* [SPOI-3653] - Document property changes needed run demos on 2.0.0
* [SPOI-3661] - Update security section in operations guide
* [SPOI-3662] - Operations Guide: Update application configuration section
* [SPOI-3669] - Remove gateway jars api usage from benchmarking and use app pkg api instead
* [SPOI-3695] - Documentation on System Alerts in the Gateway
* [SPOI-3700] - run app memory usage benchmarks for 2.0
* [SPOI-3701] - run performance benchmarks for 2.0
* [SPOI-3702] - run high availability benchmarks for 2.0
* [SPOI-3703] - Run Fs output operator benchmark
* [SPOI-3704] - run performance across tuple size benchmarks for 2.0
* [SPOI-3705] - Change jars api usage to apps package api usage in certification
* [SPOI-3706] - Convert Malhar benchmark module to app package
* [SPOI-3730] - Getting Started Guide updates

### Bug
* [MLHR-1237] - Scrolling log viewer with mouse does not trigger getting more log content
* [MLHR-1242] - "last heartbeat" in killed container list shows date in 1969
* [MLHR-1443] - Attempt reconnect if web socket connection is dropped
* [MLHR-1523] - Physical operator ids sorted lexicographically
* [MLHR-1552] - Port JMS Input operator changes to library.
* [MLHR-1553] - shutdown and kill cmds still visible when ended apps are selected
* [MLHR-1588] - New installation does not walk through welcome steps
* [MLHR-1590] - App Instance dashboard cannot find Logical DAG widget for starting app
* [MLHR-1591] - pending undeploy does not have an icon or color associated
* [MLHR-1592] - webSocket does not reconnect if user logs out then logs back in
* [MLHR-1593] - Installer should be ok with 404 errors when fetching HadoopLocation and dfsRootDirectory
* [MLHR-1594] - DFS permissions error during install does not provide resolution steps
* [MLHR-1595] - Installer asks for login even if auth is disabled
* [MLHR-1606] - Change EDIT_AND_KILL_OTHERS_APPS to MANAGE_OTHERS_APPS
* [MLHR-1609] - Physical Operators have an invalid heartbeat when PENDING_DEPLOY
* [MLHR-1611] - Do not try to put or edit admin role in auth management page
* [MLHR-1612] - New containers from websocket do not get jvm name
* [MLHR-1615] - Feedback for retrieving ended apps
* [MLHR-1619] - When launching app package, allow launch time parameters to be specified
* [MLHR-1622] - YahooFinanceApplication throws null pointer exception on 2.0
* [MLHR-1627] - Make twitter credentials into requiredProperties in app package
* [MLHR-1631] - NullPointerException in launching HDFSBenchmarking App:TupleSize property missing in appResponse

### Improvement
* [MLHR-1190] - Infinite scroll mechanism in stram events widget
* [MLHR-1234] - Add version information to system diagnostics screen
* [MLHR-1555] - Remove dashboard component from main operations page
* [MLHR-1571] - Height of app list should be determined by available space
* [MLHR-1596] - Extract two-way infinite scroll behavior into directive
* [MLHR-1597] - Fix FTP Input operator
* [MLHR-1602] - Partitioning of couchbase input operator

### New Feature
* [MLHR-1228] - create profile storage object
* [MLHR-1261] - AngularJS Migration - Tuple Viewer
* [MLHR-1262] - AngularJS Migration - Tuple Recording
* [MLHR-1354] - Auth management support in the UI

### Story
* [MLHR-975] - Migration from Backbone to Angular

### Task
* [MLHR-1292] - Recording View
* [MLHR-1331] - Update the tuple recording topic
* [MLHR-1586] - Remove DirectoryScanInputOperator from library
* [MLHR-1601] - Re-arrange logstream app in dt application package format
* [MLHR-1608] - Create a Block reader which emits Slice and doesn't read ahead of a block boundary
* [MLHR-1617] - Sensitive permission assignment need dialog box warning with consequences
* [MLHR-1618] - Update console for the new app package REST API
* [MLHR-1623] - Create synchronizer for asynchronously processing streaming data for committed windows
* [MLHR-1626] - Write unit tests for AbstractSynchronizer

### Bug
* [SPOI-2946] - Provide a tool that generates a license report based on license audit logs
* [SPOI-2974] - Better error handling when license is expired
* [SPOI-3147] - Issues with dynamic partitioning of Block readers 
* [SPOI-3192] - Send proxy user when making web service calls from gateway
* [SPOI-3267] - HDHT Operator crash when launching application against existing store
* [SPOI-3271] - Change port stats propogation test to check for cumulative buffer server bytes
* [SPOI-3286] - HDHT WAL recovery crashing with NegativeArraySizeException
* [SPOI-3287] - Research the types of data that can be stored in hive orc files
* [SPOI-3288] - NullPointerException in StreamingContainerManager-> fillLogicalOperatorInfo
* [SPOI-3289] - App Packages launch not reading required properties from dt-site.xml
* [SPOI-3293] - Incorrect application name when launching JSON app.
* [SPOI-3294] - Configuration setting from property.xml not effective for JSON app
* [SPOI-3296] - npm install fails for malhar-ui-console
* [SPOI-3297] - Remove keys from metric list in app dashboard widget.
* [SPOI-3300] - Two operators named "Dimension Computation"
* [SPOI-3305] - Create Sales Demo JSON Input Generator
* [SPOI-3306] - Change Event Schema to default to Sales Schema
* [SPOI-3309] - DT flume sink not draining under some circumstances
* [SPOI-3313] - Setting attributes with JSON and properties app needs cleanup
* [SPOI-3319] - NPE in FSStatsRecorder
* [SPOI-3320] - The platform should use user folder in hdfs for storage
* [SPOI-3323] - Gateway resource leak when RM is not running and/or during network problem 
* [SPOI-3325] - HDHT DTFile clean cache when reader close
* [SPOI-3338] - Application level operator properties do not override "global" operator properties
* [SPOI-3343] - Gateway was stuck

### Improvement
* [SPOI-2918] - Document Counters
* [SPOI-3188] - Ability to interpret an input operator as a regular operator 
* [SPOI-3312] - OperatorAnnotation that enforces checkpointing to happen at application window boundary
* [SPOI-3317] - Add sales generator tuples per window randomization controls
* [SPOI-3318] - Add more dimensions and aggregates to Sales demo
* [SPOI-3321] - Improve data variation between categories, regions, and discounts
* [SPOI-3329] - Implement simple variable substitution in properties files

### New Feature
* [SPOI-2014] - Support for doc link for an operator 
* [SPOI-2931] - Make sure app packages work in sandbox
* [SPOI-2989] - HDHT - Recovery

### Task
* [SPOI-2663] - Certify datatorrent on a CDH5 secure cluster
* [SPOI-2702] - HDS - Generic time series query
* [SPOI-2843] - Tracker ticket for work related to app package in Malhar
* [SPOI-2945] - Allow application to start even if license manager is not running for production license file
* [SPOI-2950] - Generate monthly alerts when the memory used crosses the licensed memory
* [SPOI-3022] - Run jpa and jdbc tests on vertica installation in cluster
* [SPOI-3098] - Scrub all components that make it to the release list of jiras
* [SPOI-3119] - Generate audit logs in the applications as well
* [SPOI-3153] - Certify datatorrent on HDP secure cluster
* [SPOI-3156] - Tool to generate license report from a single Hadoop grid
* [SPOI-3158] - Webservice for license report
* [SPOI-3160] - Uptime debugging for license mgr
* [SPOI-3161] - license mgr should write memory reported by each app in the logs
* [SPOI-3184] - Test case to reproduce locality issue in CDH
* [SPOI-3229] - New app will launch for production license even if no memory is available in license
* [SPOI-3261] - Kafka one to many dynamic partitioning pilot
* [SPOI-3269] - Support contact update
* [SPOI-3278] - Research elastic search functionality to build operators
* [SPOI-3280] - Create a model parser that loads the model mapping file and generates sql mapping
* [SPOI-3282] - Create a vertica output operator
* [SPOI-3283] - Start License Manager as part of Installation
* [SPOI-3284] - Watch dog process for License Manager in Gateway
* [SPOI-3299] - O15 demo: Dictionary for keys
* [SPOI-3307] - Add Enrichment operator data file
* [SPOI-3315] - O15 demo: Update widget configuration for sales schema
* [SPOI-3335] - Kafka offset manager
* [SPOI-3339] - Move FSStorageAgent to Malhar
* [SPOI-3352] - Process OperatorCommand returned by stats listener
* [SPOI-3411] - Create a feed processor operator that converts input event to table rows
* [SPOI-3412] - Create gzip input operator
* [SPOI-3413] - Create pluggable functions for each column based given function name and parameters
* [SPOI-3414] - Create Table controller to handle value generation for each column including user defined functions
* [SPOI-3561] - Recording View: links to start and stop recording
* [SPOI-3562] - Recording View: page module
* [SPOI-3565] - Container Page (angular)

### Bug
* [MLHR-1267] - AngularJS Migration - Dashboard Layout Lock
* [MLHR-1352] - Custom directive for breadcrumbs
* [MLHR-1489] - Create a hive output operator that can write to hive orc files
* [MLHR-1500] - Cleanup of the junit.framework.Assert 
* [MLHR-1505] - Stram event error closes when clicking on stack trace
* [MLHR-1506] - Stram event collection removes events
* [MLHR-1512] - UI Console - Dashboard Reset
* [MLHR-1532] - Table says "loading" when active filter result is 0 rows
* [MLHR-1541] - Add orc file output to adsdimension demo
* [MLHR-1542] - App Data Framework - WebSocket Support
* [MLHR-1585] - Installer fails with auth enabled

### Improvement
* [MLHR-1256] - Create a new landing dashboard
* [MLHR-1432] - Add confirm for deleting an app package
* [MLHR-1451] - Loading feedback for malhar-angular-table
* [MLHR-1452] - Loading feedback for app packages and package apps
* [MLHR-1454] - Performance Tuning for malhar-angular-table
* [MLHR-1499] - Idempotent State Manager
* [MLHR-1531] - App overview does not show started time
* [MLHR-1540] - Remove stram events from physical view
* [MLHR-1543] - Switch to gulp in malhar-angular-table
* [MLHR-1549] - Short operator properties should be shown in line

### New Feature
* [MLHR-1282] - AngularJS Migration - App Instance Page - Alerts Recordings View
* [MLHR-1301] - AngularJS Migration - Physical Operator Page - Recordings
* [MLHR-1317] - AngularJS Migration - App Instance Page - Logical View - Log Levels
* [MLHR-1362] - AngularJS Migration - App Instance Page - Stram Events Widget Resize
* [MLHR-1370] - AngularJS Migration - Container View - Chart
* [MLHR-1428] - Dashboard Component - Option to Disable Vertical Resize
* [MLHR-1462] - Socket.IO Kafka Communication Protocol
* [MLHR-1463] - UI Console - Client Settings
* [MLHR-1464] - Kafka App Data - Server Socket.IO Node.js
* [MLHR-1465] - Kafka Socket.IO Service - Latency
* [MLHR-1466] - Kafka Server - Query Cache
* [MLHR-1470] - Dashboard Builder Integration
* [MLHR-1486] - UI Console - Deploy Scripts
* [MLHR-1488] - App Package Dag Viewer - Handle Case when DAG is empty
* [MLHR-1491] - App Data UI - Runtime Configuration for Default Dashboard/Widgets/Queries
* [MLHR-1495] - Kafka Debug Widget - Kafka Producer/Consumer Topics
* [MLHR-1498] - Provide Ability to Reset Dashboard Configuration 
* [MLHR-1502] - App Data Server - Fetch Latest Kafka Offset
* [MLHR-1514] - App Data Server - EventEmitter
* [MLHR-1515] - App Data Server - UML Diagrams
* [MLHR-1520] - App Data UI - Table Widget
* [MLHR-1521] - App Data UI - WebSocket Support
* [MLHR-1530] - App Data UI - Table Widget

### Story
* [MLHR-1295] - AngularJS Migration - Logical Operator Page
* [MLHR-1296] - AngularJS Migration - Physical Operator Page

### Task
* [MLHR-1270] - Container Page (angular)
* [MLHR-1272] - Container Page: memory gauge
* [MLHR-1274] - Container Page: metric chart
* [MLHR-1281] - Stream View
* [MLHR-1286] - Stream View: sources table
* [MLHR-1287] - Stream View: sinks
* [MLHR-1288] - Port View
* [MLHR-1290] - Port View: overview
* [MLHR-1291] - Port View: chart
* [MLHR-1293] - Recording View: page module
* [MLHR-1294] - Recording View: links to start and stop recording
* [MLHR-1307] - Installation Wizard
* [MLHR-1310] - Info Menu Links
* [MLHR-1312] - Lock Layout (malhar-angular-dashboard)
* [MLHR-1453] - System Diagnostics Page
* [MLHR-1460] - Installation Wizard: welcome page
* [MLHR-1461] - Installation Wizard: hadoop config page
* [MLHR-1467] - Installation Wizard: license screen
* [MLHR-1482] - Installation Wizard: summary screen
* [MLHR-1483] - Installation Wizard: license upload
* [MLHR-1496] - Create an operator for Solr
* [MLHR-1516] - Annotate new FS output operators
* [MLHR-1518] - WebSocket support for dimension demo
* [MLHR-1574] - UI Auth: support for current password auth
* [MLHR-1575] - UI Auth: Managing role and permissions

### Sub-task
* [SPOI-3123] - Add troubleshooting section to Operations and Installation Guide
* [SPOI-3124] - Check for vmem/pmem ratio during System Diagnostics test
* [SPOI-3129] - Integrate Kafka query protocol for AdsDimension demo.
* [SPOI-3154] - Setup AdsDimension demo on cluster
* [SPOI-3226] - Create JSON AdInfo Generator for App Builder Demo
* [SPOI-3227] - Crate JSON to Map converter for App Builder Demo
* [SPOI-3228] - Create shared dimensions computation schema for App Builder Demo

### Bug
* [SPOI-1667] - Drop of Performance for Machine demo
* [SPOI-2742] - Core dumps on EMR
* [SPOI-2942] - Disable physical plan locking when there is no available license memory
* [SPOI-2947] - Provide a tool that distributes memory and generates licenses that can be deployed on multiple clusters
* [SPOI-3018] - Investigate raw performance of vertica jdbc
* [SPOI-3024] - Adding Virtual Mem to Physical Memory setting in Readme file
* [SPOI-3025] - Can't see the container logs from DT Console in Pivotal installation
* [SPOI-3053] - Continual Repartitioning Of Operator Causes Out Of Memory Exception
* [SPOI-3081] - Core StatsTest.testPortStatsPropagation Failing
* [SPOI-3107] - Failed to load Logical Plan 
* [SPOI-3132] - User Interface Guide URL  specified in current Sandbox gives 404
* [SPOI-3181] - dtgateway script: $PATH is being appended to repeatedly when gateway has trouble starting
* [SPOI-3187] - HDHT query results partition duplication
* [SPOI-3190] - HDHT AdsDimension demo last bar should grow
* [SPOI-3195] - Operator class exception when loading app package
* [SPOI-3196] - CLI returns Perm Gen Space errors when there are too many classes to inspect in app package
* [SPOI-3197] - Provide meta information for operators that can be used by DAG builder
* [SPOI-3198] - App Package archetype is erroneously including app package manifest in the low level jar file
* [SPOI-3213] - Newer maven versions (>3.1) do not work with copy-maven-plugin in app package archetype
* [SPOI-3215] - Duplicate streams in OperatorDeploymentInfo with default partition/parallel partitioning 
* [SPOI-3232] - Mobile demo not dynamically partitioning
* [SPOI-3262] - Issue with serialization of xml cartesian product operator
* [SPOI-3319] - NPE in FSStatsRecorder

### Improvement
* [SPOI-1967] - Accept Password for Private Key
* [SPOI-2997] - License file content updates
* [SPOI-3083] - Ability to save DAG as a DT App Package
* [SPOI-3084] - Operator Library Browser
* [SPOI-3087] - Properties Section
* [SPOI-3088] - Attributes Section
* [SPOI-3089] - Operators needed for demo
* [SPOI-3102] - FileSplitter needs to be idempotent
* [SPOI-3136] - Add a check to see if stram is connected to THIS gateway

### New Feature
* [SPOI-3142] - Ability to take Logical Plan Serialization JSON to construct a DAG and launch it
* [SPOI-3148] - App Package REST API needs to allow PUT of json logical plan for adding/replacing application in app package
* [SPOI-3149] - Ability to launch a json-specified app within app package
* [SPOI-3185] - Import demo app packages from dtgateway fs
* [SPOI-3186] - Group app packages under demos folder in release
* [SPOI-3189] - Add display name and description to app package's manifest
* [SPOI-3199] - XML Javadoc
* [SPOI-3266] - Provide Ability to Allow Cross Origin Access

### Task
* [SPOI-3039] - Print data upon license mgr app start
* [SPOI-3061] - Add port tuple type in logical plan serialization
* [SPOI-3067] - Remove time-bombed public/private key pair from the code
* [SPOI-3068] - Make sure the release process (sandbox, installer binary) is okay with the time bound key pair removed from the code
* [SPOI-3069] - Remove the entire request blob process and generate license straight from customer info and license info
* [SPOI-3070] - Device ID change in license
* [SPOI-3071] - Generate License web tool to prompt for password for the private key
* [SPOI-3126] - O15 - Generic Dimension Computation/Store Operator
* [SPOI-3128] - HDHT - AdsDimension app integration for internal demo 
* [SPOI-3130] - HDHT - Test files with varying block sizes
* [SPOI-3134] - Add a organization field in license file
* [SPOI-3162] - Kafka ingestion demo
* [SPOI-3164] - Integrate Kafka Query frontend into demos
* [SPOI-3165] - Ability to return JSON app as-is from app package through REST
* [SPOI-3166] - Ability to delete JSON apps from app package
* [SPOI-3167] - Ability to save incomplete json-based app to an app package
* [SPOI-3179] - Investigate how IDEs parse javadoc
* [SPOI-3182] - Complete dag annotations spec
* [SPOI-3193] - Investigate pluggable authorization mechanisms supported by Hadoop
* [SPOI-3200] - Generate resource file containing javadoc comments and custom tags
* [SPOI-3201] - Configure default javadoc doclet in pom to include custom tags
* [SPOI-3202] - Transform xml javadoc resources file to contain only comments and tags
* [SPOI-3203] - Add javadoc resource file to the class jar at maven build
* [SPOI-3206] - Add field and method comments to transformed xml javadoc
* [SPOI-3217] - Limit events DTFlumeSink pumps into the dag
* [SPOI-3219] - Help diagnose launch issue
* [SPOI-3225] - Check and fix machine and twitter hash tag demos
* [SPOI-3236] - displayName should be available from appPackage/applications call

### Bug
* [MLHR-1347] - Create a block reader in library which is capable of dynamic partitioning itself
* [MLHR-1366] - HdfsBucketStore is not completely covered by unit test cases
* [MLHR-1367] - Add Counter Aggregators For Monitoring AbstractThroughputFSDirectoryInputOperator
* [MLHR-1373] - Container log download link
* [MLHR-1404] - App Package File Upload
* [MLHR-1407] - App List Kill App Selection Issue
* [MLHR-1410] - Add a "remove" option to the "set/subscribe" method of BaseCollection
* [MLHR-1412] - App Package archetype is erroneously including app package manifest in the low level jar file
* [MLHR-1419] - Xml cartesian product operator has kryo serialization errors in some cases
* [MLHR-1422] - UI Physical tab-> sorting by operator id is by lexical order not numerical
* [MLHR-1423] - app instance page does not update when state goes ACCEPTED => RUNNING
* [MLHR-1426] - favicon not being handled in gulp build
* [MLHR-1436] - Uptime shows -1 day even when the app is runing for some time
* [MLHR-1438] - AdsDimensionsWithHDSDemo - Expose Aggregation in Operator Properties
* [MLHR-1442] - Move the recipient property for the machine data to config
* [MLHR-1557] - subscribe handler on app instance alters original ws message
* [MLHR-1558] - Palette in the Apps List does not update after one app gets killed

### Improvement
* [MLHR-1427] - Make app name link to instance page as well in AppsList

### New Feature
* [MLHR-1388] - Base DAG Viewer
* [MLHR-1389] - App Package List Page
* [MLHR-1390] - Applications/Package Info Page
* [MLHR-1391] - App Package REST API Integration
* [MLHR-1392] - App Package CRUD
* [MLHR-1406] - UI Support of app package import
* [MLHR-1408] - Allow Shutting Down/Killing Multiple Applications
* [MLHR-1424] - UI Grid 3 Integration - Fonts
* [MLHR-1429] - Dashboard Component - Configurable Widget
* [MLHR-1430] - Kafka UI Demo
* [MLHR-1431] - Visual Data Demo Update

### Story
* [MLHR-1241] - App Package support in UI
* [MLHR-1357] - UI Dashboard Front Page Design

### Task
* [MLHR-1079] - Normalize timestamps for info pages
* [MLHR-1104] - Design App Package and Upload/Launch Feature
* [MLHR-1105] - Polish simplified (current) app data alert feature
* [MLHR-1207] - Convert demo apps to app packages
* [MLHR-1309] - License Info
* [MLHR-1363] - Create file splitter that breaks file into blocks and emits block metadata and a block reader 
* [MLHR-1415] - Clean-up Hdfs Output operators in library and incorporate the features of fault-tolerant Writer
* [MLHR-1503] - Remove deprecated jdbc package from contrib



Version 1.0.4
------------------------------------------------------------------------------------------------------------------------

### Bug
* [SPOI-2346] - ExactlyOnceTest#testLinearInputOperatorRecovery hangs
* [SPOI-2511] - ResourceManager HA support
* [SPOI-2625] - uninstall.sh should print message that reminds users of running DT applications
* [SPOI-2922] - Counters Aggregator gets lost when an operator is parallel partitioned - test fix
* [SPOI-2939] - AppBundles test resource refers to fixed version
* [SPOI-2967] - Mobile demo dies after couple of days
* [SPOI-2979] - App Bundle unit test should load properties.xml
* [SPOI-2991] - [kafka-yarn] Archive resource to use less space in HDFS
* [SPOI-2993] - appBundle with conflicting names in config and ApplicationAnnotation can't launch in CLI with either name
* [SPOI-2995] - Generate MANIFEST.MF automatically instead of requiring user to change it
* [SPOI-2999] - Investigate application integration to Vertica
* [SPOI-3012] - launch application throws NPE when yarn.application.classpath is not defined
* [SPOI-3015] - DTGateway log grows indefinitely
* [SPOI-3019] - Investigate how many objects per second (with a single field) using JPA can be written to vertica
* [SPOI-3027] - Sandbox GATEWAY_CONNECT_ADDRESS change to support VMWare
* [SPOI-3055] - NullPointerException When Repartitioning Too Frequently
* [SPOI-3074] - NullPointerException in AppMaster
* [SPOI-3079] - NPE while launching application
* [SPOI-3080] - Content-disposition: attachment for container logs
* [SPOI-3091] - Null Pointer Exception/Internal Server Error When Getting Operator Stats
* [SPOI-3092] - DefaultUnifier of a port in an operator does not function correctly when the port has more than one sinks

### Improvement
* [SPOI-2821] - Add bucket processed time
* [SPOI-2891] - DTGateway default log setting too verbose
* [SPOI-2938] - Document AppBundles development and deployment
* [SPOI-3044] - gateway should show the full stack trace of the origin upon error when proxying

### New Feature
* [SPOI-2720] - API Call for determining if an application's stram can connect to the gateway
* [SPOI-2981] - HDS - File Format
* [SPOI-2982] - HDS - Writing Data Files
* [SPOI-2983] - HDS - Bucket Meta Data
* [SPOI-2984] - HDS - WAL
* [SPOI-2986] - HDS - Bucket Management
* [SPOI-3031] - Add ability to specify number of recording windows
* [SPOI-3032] - Delete request for recording
* [SPOI-3033] - Provide byte offset for each line when grepping container log
* [SPOI-3049] - Ingestion streamlet design for first cut

### Task
* [SPOI-1734] - Licensing Agent Logging for Audit
* [SPOI-2810] - Update document with details on password authentication
* [SPOI-2906] - Write documentation on App Bundle
* [SPOI-2908] - Prototype kafka-on-yarn
* [SPOI-2934] - Add application id to the tuple record topic
* [SPOI-2962] - Create operator to write events in bucket file and write index files for keys
* [SPOI-2963] - Change query processor operator to fetch events based on indices
* [SPOI-2996] - Support launch-app-bundle command without the appname argument
* [SPOI-3006] - Create a LATLON to MGRS converter utility
* [SPOI-3009] - Create a utility to calculate MD5 hash
* [SPOI-3010] - Create a utility for Blowfish
* [SPOI-3014] - Update sandbox release docs
* [SPOI-3026] - Change the name app bundle to app package and the extension zip to jar
* [SPOI-3036] - Review issue with ingestion
* [SPOI-3050] - A first cut at design for ingestion streamlet
* [SPOI-3051] - License work
* [SPOI-3108] - Add REST API to get the entire hadoop configuration
* [SPOI-3121] - HDS - File Format - Performance testing TFile / DTFile
* [SPOI-2985] - HDS - File Format - Performance testing - HFile
* [SPOI-2987] - HDS - File Format - Performance testing - MapFile
* [SPOI-3122] - HDS - File Format - HFile implementation
* [SPOI-3017] - HDS - File Format - Common Interface
* [SPOI-3100] - Create the SinglePointCalculator 
* [SPOI-3103] - Create Synchronizer Operator
* [SPOI-3104] - Create Persister to store the data


### Bug
* [MLHR-1223] - JDBC Store doesn't support connection properties
* [MLHR-1253] - documenting keyhashvalpair
* [MLHR-1255] - db api in malhar lib has KeyValueStore interface which is similar to db/cache/Store api 
* [MLHR-1260] - AngularJS Migrations - Metrics Grouping
* [MLHR-1268] - AbstractBatchTransactionableStoreOutputOperator add to library db is same as public abstract class AbstractAggregateTransactionableStoreOutputOperator
* [MLHR-1269] - Mobile demo dies after couple of days
* [MLHR-1319] - AngularJS Migration - WebSocket Service
* [MLHR-1320] - AngularJS Migration - Page Visibility API
* [MLHR-1323] - stram events links broken (angular)
* [MLHR-1325] - Wrong "track by" in physical operators list
* [MLHR-1328] - "inspect" button in appslist broken
* [MLHR-1335] - dtPageHref directive does not update href of element on changes
* [MLHR-1336] - Container shorthand directive not watching value changes
* [MLHR-1342] - Allow DAG widgets to be vertically resized (using jquery resizable)
* [MLHR-1344] - AngularJS Migration - Metrics Chart
* [MLHR-1345] - AngularJS Migration - Physical Operator Page - Chart
* [MLHR-1346] - Test for AbstractFSDirectoryInputOperator fails sporadically
* [MLHR-1359] - AngularJS Migration - Dashboard Widgets Vertical Resize
* [MLHR-1364] - BucketManager while reading values doesn't ensure that latest value for a key is read
* [MLHR-1368] - AngularJS Migration - App Instance Page - Overview Grouping
* [MLHR-1374] - Remove all occurrences of dag.setAttribute(DAG.APPLICATION_NAME, "xxx") in demos code


### Improvement
* [MLHR-1263] - Migrate JDBC non-transaction output operator to new db api and move it to lib
* [MLHR-1322] - Changing Machine Data Operator and Stream Names
* [MLHR-1324] - appState directive should be renamed to something more generic
* [MLHR-1327] - Assume lodash is global throughout console
* [MLHR-1343] - Use userStorage to store height of stram events
* [MLHR-1351] - Allow transformResponse to set a fetchError
* [MLHR-1353] - Centralize location of breadcrumbs
* [MLHR-1360] - Put dashboards on the left

### New Feature
* [MLHR-419] - DAG Widget with AngularJS
* [MLHR-1220] - Send the "unsubscribe" webSocket message for topic when no more listeners
* [MLHR-1239] - AngularJS Migration - Physical DAG View
* [MLHR-1240] - AngularJS Migration - Logical DAG View
* [MLHR-1243] - Angular JS Migration - Current/Recover Window Id Metrics
* [MLHR-1245] - AngularJS Migration - Partitions/Container Metrics
* [MLHR-1246] - AngularJS Migrations - DAG View Zoom
* [MLHR-1247] - AngularJS Migration - Physical View
* [MLHR-1248] - AngularJS Migration - Container View
* [MLHR-1249] - AngularJS Migration - Landing Page High-Level Metrics
* [MLHR-1250] - AngularJS Migration - Charts
* [MLHR-1251] - AngularJS Migration - Gauge Widget
* [MLHR-1252] - AngularJS Migration - DAG View Base Renderer
* [MLHR-1278] - AngularJS Migration - App Instance Page - Logical View
* [MLHR-1279] - AngularJS Migration - App Instance Page - Physical View
* [MLHR-1280] - AngularJS Migration - App Instance Page - Physical DAG View
* [MLHR-1283] - AngularJS Migration - App Instance Page - Metric View
* [MLHR-1298] - AngularJS Migration - Physical Operator Page - Overview
* [MLHR-1299] - AngularJS Migration - Physical Operator Page - Port List
* [MLHR-1300] - AngularJS Migration - Physical Operator Page - Properties
* [MLHR-1303] - AngularJS Migration - Logical Operator Page - Overview
* [MLHR-1305] - AngularJS Migration - Logical Operator Page - Partitions
* [MLHR-1306] - AngularJS Migration - Logical Operator Page - Chart
* [MLHR-1308] - AngularJS Migration - Logical Operator Page - Properties
* [MLHR-1313] - AngularJS Migration - App Instance Page - Physical View - Container List
* [MLHR-1314] - AngularJS Migration - App Instance Page - Physical View - Operators
* [MLHR-1315] - AngularJS Migration - App Instance Page - Logical View - Chart
* [MLHR-1316] - AngularJS Migration - App Instance Page - Logical View - Stream List
* [MLHR-1321] - AngularJS Migration - Distribution Build with Gulp
* [MLHR-1334] - Front-End Build with Gulp - WebSocket Proxy
* [MLHR-1337] - Front-End Build with Gulp - JS/CSS Revisions
* [MLHR-1338] - Front-End Build with Gulp - Angular Templates Injection
* [MLHR-1341] - create userStorage service for user settings
* [MLHR-1358] - Breadcrumbs to jump between collection elements
* [MLHR-1361] - Logical/Physical DAG - Stream Locality Legend
* [MLHR-1365] - AngularJS Migration - Widget Settings Modal - Height Management

### Task
* [MLHR-1208] - Convert contrib apps to app bundles
* [MLHR-1244] - Update tuple recorder topic to use "applications.<appid>.tupleRecorder.<startTime>"
* [MLHR-1254] - Create a test case for UniqueValueCountAppender
* [MLHR-1264] - Start Logical Operator Page
* [MLHR-1265] - Start Physical Operator Page
* [MLHR-1266] - Start Container Page View
* [MLHR-1271] - Container Page: overview
* [MLHR-1273] - Container Page: operator list
* [MLHR-1275] - Container Page: log viewer
* [MLHR-1276] - Container Page: page module
* [MLHR-1284] - Stream View: overview
* [MLHR-1285] - Stream View: page module
* [MLHR-1289] - Port View: page module
* [MLHR-1302] - Operations Landing Page: memory gauge
* [MLHR-1311] - Vertical Resize (malhar-angular-dashboard)
* [MLHR-1318] - Move webSocket service to malhar-angular-widgets
* [MLHR-1326] - Create .jshintrc for IDE/editor, grunt tasks
* [MLHR-1330] - Document gulp usage in README
* [MLHR-1333] - add "gulp coverage" task
* [MLHR-1339] - Need a dynamic partitioner for File processing operator where the count of the operator instances is controlled by the backlog present
* [MLHR-1348] - Change app bundle to app package on all demos
* [MLHR-1349] - Link tables to userStorage service
* [MLHR-1372] - Adding the tool-tip capability to console
* [MLHR-1376] - Add counters and counters aggregator to mobile demo



Version 1.0.3
------------------------------------------------------------------------------------------------------------------------

### Bug
* [SPOI-2620] - S3 reader error
* [SPOI-2673] - Move the Kafka Exactly Once Producer to Malhar Library
* [SPOI-2775] - Log file being processed on seperate port to monitor progress by input operators.
* [SPOI-2813] - Send top gateways in descending order
* [SPOI-2814] - Change field name of input event in CDREvent
* [SPOI-2815] - Show top 3 gateways using a widget
* [SPOI-2816] - No query poll in alert information view
* [SPOI-2817] - For non-finalized buckets threshold flags should not be set
* [SPOI-2819] - Send data continuously to the application
* [SPOI-2820] - Provide more alerts in the UI
* [SPOI-2837] - Operators crashing sporadically when alert information requested from frontend
* [SPOI-2838] - Clear out the cdr event files and aggregates are cleared
* [SPOI-2844] - Machine data demo waits long before starting
* [SPOI-2845] - Recovery is failing in cdr events output operator after upstream operator redeploys
* [SPOI-2854] - Buckets are not being finalized correctly when there is a bucket gap in input data
* [SPOI-2861] - GATEWAY_CONNECT_ADDRESS not set during install
* [SPOI-2866] - Change lablel of top gateways to top 3 gateways
* [SPOI-2867] - Change null to empty value in the UI for alert event information
* [SPOI-2869] - Need a cleanup script to delete old files from hdfs
* [SPOI-2882] - Backup the allatory log file for flume integration build as well
* [SPOI-2883] - NPE in bufferserver
* [SPOI-2892] - DTGateway WS fails to get YARN logs
* [SPOI-2894] - Investigate bucket manager for cdr event storage
* [SPOI-2900] - First few events for an application do not get published
* [SPOI-2902] - Documentation for sandbox missing images
* [SPOI-2910] - PartitioningTest.testDynamicDefaultPartitioning sometimes fails and sometimes succeeds 
* [SPOI-2913] - Events API returns no events when limit and offset not supplied
* [SPOI-2919] - Change cleanup to cleanup folders older than an hour
* [SPOI-2920] - make stats recorder asynchronous so that it won't block stram
* [SPOI-2921] - Test Node Locality feature on HDP
* [SPOI-2932] - Historical containers don't show up on gateway if there is a second attempt on application
* [SPOI-2936] - Historical data store high level design
* [SPOI-2937] - Gateway throwing exception while launching app 

### Improvement
* [SPOI-2811] - Show input record in alert information dialog
* [SPOI-2812] - Show top gateways for all defect aggregates and possibly all aggregates
* [SPOI-2881] - Show actual memory usage in dashboard
* [SPOI-2891] - DTGateway default log setting too verbose
* [SPOI-2911] - Create a Bean2String codec

### New Feature
* [SPOI-2228] - Gateway to load and to allow manipulation of app bundles
* [SPOI-2753] - Front End POC - Aggregates Table
* [SPOI-2757] - Front End POC - Kafka Operations
* [SPOI-2758] - Front End POC - Historical Data Navigation
* [SPOI-2808] - Support YARN log aggregation for dead container log retrieval in the gateway
* [SPOI-2826] - Maven archetype for assembling app bundle
* [SPOI-2827] - CLI to load app bundles
* [SPOI-2828] - Supports launching apps in app bundle in CLI
* [SPOI-2829] - Gateway to allow uploading and changing configuration of existing App Bundles
* [SPOI-2849] - Demonstrate Datatorrent RTS as front end ingestion for Spark.
* [SPOI-2879] - Kafka Request/Response Debug Collapsible Panel
* [SPOI-2896] - Unique identifier for stram events

### Story
* [SPOI-2835] - Streamlet Design - 1.0.3
* [SPOI-2836] - Kafka integration for 1.0.3
* [SPOI-2851] - Platform Excellence - 1.0.3

### Task
* [SPOI-2212] - Determine logistics of application bundles
* [SPOI-2521] - Add counters for checkpointo operations
* [SPOI-2546] - Pi demo does not seem to work in 512MB
* [SPOI-2547] - Twitter demo needs 1024MB
* [SPOI-2684] - Automated distro certification - collect minimum requirements
* [SPOI-2786] - Include setters and getters for output fields in the event
* [SPOI-2795] - Add top 3 gateways to alert aggregate csv in HDFS
* [SPOI-2802] - Dynamic partitioning for S3 input operator.
* [SPOI-2822] - Add operator to write cdr events to hdfs
* [SPOI-2823] - Fetch events from hdfs for alert events query response
* [SPOI-2846] - Partition Aggregations operator
* [SPOI-2859] - Separate out query processing from aggregations operator
* [SPOI-2870] - Application template classpath does not include malhar libraries
* [SPOI-2874] - Add Port Queue Capacity usage as part of the operator stats
* [SPOI-2878] - Move the gateway randomization to generator
* [SPOI-2890] - Update support contacts to malhar-users group
* [SPOI-2914] - Configure Store operator to join logger and tracker stream.

### Sub-task
* [SPOI-2747] - Total emitted window of an operator keeps on increasing even when it has stopped emitting
* [SPOI-2850] - Sort out the dependencies for dt-flume so we do not include the jars which are already part of dt dist and hadoop dist
* [SPOI-2873] - Deprecate ShipContainingJars.
* [SPOI-2895] - launch -license does not work
* [SPOI-2907] - Counters appear in physical plan only when a Counters aggregator or a stats listener is set on the operator


### Bug
* [MLHR-1176] - Update demo section of README.md
* [MLHR-1219] - Non-chrome browsers cannot parse date format from date picker
* [MLHR-1227] - AbstractKafkaOutputOperator fails with java.lang.NoClassDefFoundError: com/yammer/metrics/Metrics
* [MLHR-1235] - close button on gateway info modal does not close the modal

### Improvement
* [MLHR-1213] - Use trackBy for malhar-angular-table
* [MLHR-1216] - DB key value store manager enhancement
* [MLHR-1218] - Clicking on an open stram log event should close it in UI

### New Feature
* [MLHR-1212] - Make scrollbar draggable on malhar-angular-table
* [MLHR-1225] - Logical Operator Table
* [MLHR-1226] - Stram Event widget
* [MLHR-1229] - Provide better widget options dialog
* [MLHR-1231] - Custom template/controller for widget options

### Task
* [MLHR-1205] - Restructure directory structure in angular console
* [MLHR-1206] - Change malhar pom to use provided scope to prevent DT and hadoop jars from being sucked into the runtime classpath
* [MLHR-1210] - Create script to automatically add scripts to index.html
* [MLHR-1224] - Kafka enabled AdsDimensions demo



Version 1.0.2
------------------------------------------------------------------------------------------------------------------------

### Bug
* [SPOI-431] - Fix mergeSort operator to actually do mergeSort
* [SPOI-2499] - Provide license delegation tokens in secure environment
* [SPOI-2500] - Provide new delegation token before an old one expires in secure enviroment
* [SPOI-2501] - dt.log not written under CDH5 GA
* [SPOI-2506] - [MapR]FileSystem.mkdirs() doesn't work for existing folders in MapRFileSystem
* [SPOI-2605] - DT install as root cannot use /user/chetan/dt0528 as DFS location and not printing out detailed error
* [SPOI-2608] - LicensingAppMaster's name should not be obfuscated
* [SPOI-2617] - Memory usage counted by license agent and not released after app is killed
* [SPOI-2619] - Front End Server - fill missing slots for time series
* [SPOI-2630] - Not able to launch apps in cloudera cluster
* [SPOI-2634] - Uninstall is removing entire datatorrent folder as opposed to the release folder only
* [SPOI-2639] - dtcli allows apps to be launched before configuration is finished
* [SPOI-2668] - Parent jira for Kafka work for 1.0.2
* [SPOI-2678] - Put Fraud demo into the demo UI
* [SPOI-2679] - Front End Server - Query ID as Query JSON
* [SPOI-2683] - Appmaster Logs are not shown in the Console
* [SPOI-2689] - set-operator-property produces NPE on stram 
* [SPOI-2699] - Mobile demo app mis-behaving 
* [SPOI-2703] - Gateway fails to start in devel mode with hadoop 2.3.0
* [SPOI-2705] - Demo UI instructions missing from install README
* [SPOI-2706] - Logical plan change fails w/ obfuscated build
* [SPOI-2709] - Partition events should not be registered if same no. partitions result
* [SPOI-2710] - Containers running the unifier are not released
* [SPOI-2723] - Design and develop the File Ingestion app
* [SPOI-2737] - Gateway installation replaces dt-site.xml with invalid version
* [SPOI-2744] - ZIP of version's docs not being made available for download
* [SPOI-2748] - dtdemos service fails to stop in sandbox
* [SPOI-2749] - docs distribution files at root path
* [SPOI-2759] - Installation instructions for user setup
* [SPOI-2760] - Get container log content fails with 500
* [SPOI-2761] - Remove dtadmin reference from install wizzard
* [SPOI-2762] - EMR configuration issues
* [SPOI-2779] - dtcli failed to read the license file which was uploaded through UI
* [SPOI-2798] - Request for log content outside of range results in 500, long request time
* [SPOI-2839] - set-operator-property broken in master

### Improvement
* [SPOI-2602] - Containers published via websocket should only contain live containers and recently finished containers
* [SPOI-2610] - Parent: Automatic unobfuscation tool
* [SPOI-2613] - Create web tool to run unobfuscator
* [SPOI-2614] - Automate transfer of allatori-log.xml to web server
* [SPOI-2712] - Add window_width to app info REST call
* [SPOI-2736] - Merge /systemAlerts/alerts and /systemAlerts/inAlerts API calls
* [SPOI-2751] - Include sandbox README.html with docs.zip and on website

### New Feature
* [SPOI-950] - Specify memory requirements on per operator basis (duplicate)
* [SPOI-2220] - Gateway App Bundle API spec
* [SPOI-2339] - Enable container size for each operator(s)
* [SPOI-2515] - Ability to dynamically change the logger level for any instantiated loggers within the application
* [SPOI-2523] - System alerts for application state and metrics
* [SPOI-2525] - Add operator serialization check in local mode
* [SPOI-2528] - Expose "counters" in REST API 
* [SPOI-2575] - Kafka Pub/Sub Protocol
* [SPOI-2588] - Record physical counters per window
* [SPOI-2589] - Expose counters logical and physical through web services/ web socket
* [SPOI-2606] - Initializing loggers with levels specified in the configuration
* [SPOI-2627] - Front End Server - "Countdown" usage
* [SPOI-2629] - Front End Server - Support of Multiple Partitions
* [SPOI-2631] - Front End Server - Cache Expiration Strategy
* [SPOI-2632] - Front End Server - Kafka Reconnect
* [SPOI-2633] - Front End Server - Page Performance (Visibility API)
* [SPOI-2638] - Front End Server - Kafka Errors Handling
* [SPOI-2645] - Front End Server - Kafka SimpleConsumer
* [SPOI-2652] - Develop and Stage Hadoop Summit Landing Page
* [SPOI-2696] - Front End Server - Top N Metrics
* [SPOI-2697] - Front End Server - Dynamic Publisher and Site
* [SPOI-2698] - Front End Server - Kafka Troubleshooting
* [SPOI-2752] - Front End Server - LRU Cache
* [SPOI-2756] - Front End POC - Alert Modal
* [SPOI-2804] - Create a hbase operator that uses a config to map incoming csv tuples to hbase table data and saves them in hbase

### Story
* [SPOI-2455] - HDFS storage layer for 1.0.2
* [SPOI-2565] - Front End Server - Define cache policy for push data in Node.js
* [SPOI-2571] - Parent jira for Hadoop Summit work
* [SPOI-2590] - Parent: GA Testing
* [SPOI-2611] - Parent jira for facilitating trouble shooting and debugging in 1.0.2
* [SPOI-2615] - Parent jira for security work in 1.0.2
* [SPOI-2662] - Parent jira for licensing security for 1.0.2
* [SPOI-2664] - HDFS Storage, Ingestion, Access application data and file storage for 1.0.2
* [SPOI-2667] - Automate distro certification and make it part of CI for 1.0.2
* [SPOI-2781] - Determine which fields are present in output that are not present in input

### Task
* [SPOI-2341] - Update on authentication and authorization in Yarn-open source
* [SPOI-2434] - Short document on deduper checkpointing scheme
* [SPOI-2440] - Kafka support in POC for 1.0.2
* [SPOI-2509] - Investigate how to use Kafka to replace the pub/sub mechanism in Gateway
* [SPOI-2532] - Join Operator
* [SPOI-2534] - Add support of getting container info of dead applications and dead containers
* [SPOI-2535] - Add support for retrieving Aggregated Counters from Response processStats of StatsListener
* [SPOI-2542] - Get user to look at instructions before .bin file download
* [SPOI-2544] - Twitter demo "feedMultiplier" should be RW and test to ensure that it can be changed in runtime
* [SPOI-2548] - Memory gauge always shows 100%
* [SPOI-2549] - Total memory on right corner needs to be discussed
* [SPOI-2552] - Need to list certified Distros on site
* [SPOI-2558] - Help set up Kafka operations
* [SPOI-2568] - Making Kafka Producer Exactly Once
* [SPOI-2569] - Add the Rewind Feature 
* [SPOI-2573] - Integrate the Scoring of the quality logs  into the DAG
* [SPOI-2574] - Add counter calculation in hdfs operator
* [SPOI-2584] - DT counters as Key,Val (String,Number)
* [SPOI-2585] - Troubleshooting work for reporting min, max, ave, ... on resources
* [SPOI-2591] - GA Testing: CDH5 end-to-end
* [SPOI-2592] - GA Testing: HDP2 end-to-end
* [SPOI-2593] - GA Testing: MapR end-to-end
* [SPOI-2594] - GA Testing: UI end-to-end
* [SPOI-2595] - GA Testing: dtcli / gateway end-to-end
* [SPOI-2596] - GA Testing: Apache Hadoop end-to-end
* [SPOI-2597] - GA Testing: High Availability / Recovery
* [SPOI-2598] - GA Testing: Application configuration and launch
* [SPOI-2599] - GA Testing: Sandbox functionality
* [SPOI-2600] - GA Testing: Sandbox UX
* [SPOI-2621] - Top 10 support
* [SPOI-2622] - Partitioning of DimensionStore operator
* [SPOI-2624] - Front End Server - Architecture
* [SPOI-2626] - Setting up of number of partitions for Kafka Producer
* [SPOI-2636] - Twitter demo app with hashtag top 10
* [SPOI-2640] - Setup UI server for HDP grid for Hadoop Summit
* [SPOI-2641] - Setup Ambari for Hadoop Summit Demo
* [SPOI-2642] - Run Twitter demo on HDP cluster for Hadoop Summit
* [SPOI-2643] - Setup Mobile demo for HDP demo at Hadoop Summit
* [SPOI-2644] - Set up machine data demo on HDP cluster for Hadoop Summit
* [SPOI-2646] - Setup Ads demo on HDP cluster for Hadoop Summit
* [SPOI-2647] - Add the new Twitter HashTag top 10 demo to Frontend server for Summit
* [SPOI-2650] - Change default license memory settings
* [SPOI-2651] - Milestone 1 update
* [SPOI-2670] - Launch twitter hashtags on CDH and HDP clusters
* [SPOI-2671] - Update CDH cluster DT UI
* [SPOI-2672] - Move the HDFSOutputOperator to Malhar Library
* [SPOI-2676] - Get events, tuple records from kafka
* [SPOI-2680] - Make more managable kafka cluster
* [SPOI-2682] - Customer Demos Support
* [SPOI-2685] - Automated distro certification - virtualization review
* [SPOI-2686] - Automated distro certification - provisioning review
* [SPOI-2687] - Certify DT on Pivotal HD
* [SPOI-2688] - Make twitter HashTags links in demo
* [SPOI-2690] - Upgrade security sections in guides
* [SPOI-2700] - Test DimensionStore operator checkpointing and recovery
* [SPOI-2714] - Document stram event types
* [SPOI-2732] - Create a multi level key map with multiple keys
* [SPOI-2733] - Create a CSV lookup class to load CSV and lookup values based on row keys
* [SPOI-2735] - Ensure all dimemsions are implemented and covered by test
* [SPOI-2763] - Create a csv parser framework that can handle the different csv file formats
* [SPOI-2764] - Create a template application
* [SPOI-2765] - Create the template configuration file
* [SPOI-2766] - Create kafka input for the application 
* [SPOI-2767] - Add a directory scan operator that progressively scans for new folders and files for input data to the application
* [SPOI-2768] - Add a kafka upload script to upload data to the application
* [SPOI-2769] - Create an upload script that uploads application files to hdfs
* [SPOI-2773] - Add a property to clear the aggregates in the AggregationsOperator
* [SPOI-2785] - Include the input event string in the CDR event
* [SPOI-2789] - Add query support for getting events for alerts
* [SPOI-2790] - Scale the input events into millions
* [SPOI-2792] - Send top 3 gateway list in alert event details
* [SPOI-2793] - Add the capability to finalize a bucket 
* [SPOI-2794] - Add ability to clear out old results when replaying data
* [SPOI-2797] - Add query support to send the latest five minute buckets and aggregates
* [SPOI-2800] - Install a kafka web-console in our cluster
* [SPOI-2805] - Investigate yarn log aggregation to see how this fits into our container logs API

### Sub-task
* [SPOI-2725] - Create skeleton App
* [SPOI-2728] - Convert the Skeleton Operators into Real Operators - Part I
* [SPOI-2739] - File input operator
* [SPOI-2740] - DAG level unit test
* [SPOI-2776] - Test and Certify RPM packaging for Cloudera
* [SPOI-2777] - Gateway throws a bunch of exceptions when trying to install using rpm


### Bug
* [MLHR-724] - RabbitMQ test timing issue
* [MLHR-1128] - Breadcrumbs should say physical operator, not operator on port page
* [MLHR-1129] - DAG should not display underneath controls
* [MLHR-1137] - Memory gauge always shows 100%
* [MLHR-1142] - Front End Server - Kafka Reconnect
* [MLHR-1143] - KafkaOutputOperator is not configurable for Kafka Producer properties
* [MLHR-1144] - Container Actions - use wording that's not confusing
* [MLHR-1157] - Parent JIRA for Front End Server
* [MLHR-1159] - Stop Recording function does not give visual indication of stopped recording unless refreshed
* [MLHR-1169] - Update readme for console repo
* [MLHR-1170] - Appmaster Logs are not shown in the Console
* [MLHR-1185] - Stram Event widget should check physical plan for existence of operator
* [MLHR-1186] - some numbers in logical dag hidden behind control
* [MLHR-1189] - AbstractHdfsTupleFileOutputOperator output port is not optional
* [MLHR-1192] - Parametrize the demos
* [MLHR-1195] - App master container is not showing proper metrics
* [MLHR-1202] - failureCount missing for physical operators

### Improvement
* [MLHR-1132] - Improvements to errors in the stram events widget
* [MLHR-1146] - Only get active containers for initial container list
* [MLHR-1167] - UI support for searching log levels of classes
* [MLHR-1168] - Validate input for log level widget
* [MLHR-1194] - Align app counts with labels in cluster overview widget
* [MLHR-1209] - Support JMS providers other than ActiveMQ

### New Feature
* [MLHR-921] - Installer - List of Errors/Codes
* [MLHR-1111] - Container Log Widget, using new REST call
* [MLHR-1121] - Front End Server - Kafka Query JSON
* [MLHR-1122] - Front End Server - Kafka Keep Alive
* [MLHR-1123] - Front End Server - Kafka Parameterized Queries
* [MLHR-1124] - Front End Server - Kafka Response Debug/Format
* [MLHR-1125] - Front End Server - Kafka Pub/Sub Protocol for Widgets
* [MLHR-1130] - Widget to change the log levels of classes dynamically
* [MLHR-1133] - Put "float" control in widget config popup
* [MLHR-1134] - Front End Server - Editable JSON request
* [MLHR-1135] - Front End Server - Setup Instructions
* [MLHR-1136] - Front End Server - Packaging/Distribution
* [MLHR-1147] - Front End Server - Selecting Metrics
* [MLHR-1149] - Front End Server - Use Latest Kafka Offset
* [MLHR-1151] - Front End Server - Data Validation
* [MLHR-1152] - Front End Server - Page Performance (Visibility API)
* [MLHR-1175] - Widget Library - Select Widget
* [MLHR-1179] - AngularJS Migration - Application Instance Page
* [MLHR-1181] - AngularJS Migration - Application Overview Widget
* [MLHR-1182] - Angular JS Migration - App Structure
* [MLHR-1187] - UI for adding system alerts
* [MLHR-1193] - Create Basic Counters and its aggregator in library

### Story
* [MLHR-1178] - AngularJS Migration for 1.0.2

### Task
* [MLHR-960] - Create a Tableau output adapter
* [MLHR-1090] - Create first resource objects (models) for angular console
* [MLHR-1106] - Improve ended app page
* [MLHR-1139] - Add HTTP Get Operator
* [MLHR-1140] - Add HDFS output operator that writes to file names specified in tuple
* [MLHR-1160] - Create HDFS Output Operator to write with exactly once semantics
* [MLHR-1162] - Implement app list with angular
* [MLHR-1164] - Wireframe for UI DAG builder
* [MLHR-1171] - Make twitter hashTab a link in twitter demo
* [MLHR-1172] - Create a Cassandra read operator
* [MLHR-1173] - Create a Cassandra write operator

### Sub-task
* [MLHR-1163] - Wireframe for DAG builder




Version 1.0.1
------------------------------------------------------------------------------------------------------------------------

### Bug
* [SPOI-1404] - Create seperate environment for node0 for demos
* [SPOI-1952] - Operation and Install guide review
* [SPOI-2203] - Configure adsDimesions and machine data to use minimum memory
* [SPOI-2340] - License Agent is persisting state in a wrong location
* [SPOI-2397] - Monitoring and fixing the bugs in Customer demos
* [SPOI-2408] - Verify DT Platform on HDP 2.1
* [SPOI-2410] - Master script to restart hadoop on the cluster
* [SPOI-2411] - Not able to starte license with 0.9.5 release
* [SPOI-2420] - Core doesn't compile with hadoop 2.4
* [SPOI-2448] - Test xml ingestion demo on a cluster
* [SPOI-2449] - Test golden gate demo on a cluster
* [SPOI-2450] - Test twitter sentiment demo on a cluster
* [SPOI-2474] - Containers not provisioned diagnostics error
* [SPOI-2477] - LicenceAgent client fails with NPE
* [SPOI-2489] - Operator downstream of EXACTLY_ONCE operator not checkpointing
* [SPOI-2490] - HDFS 
* [SPOI-2491] - Testing the HDFS drain for Flume Sink
* [SPOI-2493] - Add HDFS operator updates into Malhar
* [SPOI-2496] - viewdag does not work any more
* [SPOI-2503] - Provide a rewind feature to replay tuples from a previous time
* [SPOI-2505] - Sandbox demos need customization
* [SPOI-2512] - Apps fail to start due to serialization errors on CDH5
* [SPOI-2533] - Fraud app needs debugging
* [SPOI-2543] - Applications not reporting the license information to License Agent if LA is restarted
* [SPOI-2550] - License Agent Dying
* [SPOI-2554] - Third party libraries which are required for demos are missing from /opt/datatorrent/releases/version/lib/
* [SPOI-2556] - Add demo guides to documentation index


### Improvement
* [SPOI-2210] - Default license generation should be part of build process
* [SPOI-2468] - README for certifications and benchmarks
* [SPOI-2482] - DTCli should handle ^C more gracefully
* [SPOI-2494] - Add HTTP Get operator to Malhar
* [SPOI-2555] - Include README, LICENSE, and CHANGELOG in docs

### New Feature
* [SPOI-406] - Document and test download to work with Hortonworks HDP 2.0
* [SPOI-408] - Certify with MapR (Hadoop 2.3) release in 1.0.1
* [SPOI-1146] - API for retrieving raw Container Logs
* [SPOI-1834] - Pub-Sub/REST mechanisms for exceptions thrown by an application
* [SPOI-2080] - Application to certify installation
* [SPOI-2253] - Username/password feature in the installer
* [SPOI-2381] - dt-site.xml logistics
* [SPOI-2387] - Aggregate Logical Operators on Gateway
* [SPOI-2402] - Update dt-site.xml with container memory less than 512MB  after getting the app-memory-automation results for all the apps.
* [SPOI-2460] - dt-site.xml new logistics implementation
* [SPOI-2470] - Create a certification property file for Distro/Install Certification
* [SPOI-2486] - Workaround for "FileSyste.getScheme is not overrided by MapRFileSystem"
* [SPOI-2519] - add grep feature when getting container log
* [SPOI-2526] - Add REST call to return info of historical containers

### Task
* [SPOI-62] - Buffer Server logging
* [SPOI-1206] - Review Licensing of Third Party Libraries
* [SPOI-1745] - Document Demo Application Setup
* [SPOI-1784] - License agent app to have webservice
* [SPOI-2199] - Readme file for AWS installation
* [SPOI-2223] - Test if all the applications with reduced container memory sizes run in sandbox 0.9.4.
* [SPOI-2348] - Enable checkpoint for aggregator operator
* [SPOI-2354] - Certify demos on 0.9.4 sandbox
* [SPOI-2370] - Fully automate Hadoop cluster restart
* [SPOI-2379] - Certify DT with Hadoop 2.3/CDH
* [SPOI-2392] - Add more basic demos to sandbox launcher
* [SPOI-2393] - Certify Amazon EMR Hadoop 2 version
* [SPOI-2414] - Stop the nightly benchmarking jenkins jobs 
* [SPOI-2415] - remove the "page has not loaded since 60 second" message at top
* [SPOI-2422] - Add HDFS cache limit on FlumeAgent operator
* [SPOI-2424] - Log metrics across all poc operators to a file
* [SPOI-2425] - Compare HDFS with customer site
* [SPOI-2426] - Benchmark HDFS drain rate by agent operator
* [SPOI-2427] - Enable dedupper to be run with checkpointing turned OFF
* [SPOI-2428] - Evaluate bigger bucket size for checkpointing for deduper
* [SPOI-2430] - Number validation for poc
* [SPOI-2432] - Compute the checkpoint I/O for dedupper
* [SPOI-2439] - Compute deduper HDFS I/O for current checkpointing scheme
* [SPOI-2441] - Estimate the feed time for HDFS agent replay
* [SPOI-2445] - Certify Cloudera CDH 5.0 GA
* [SPOI-2451] - Gateway Load Test
* [SPOI-2457] - Widget Library
* [SPOI-2458] - Generate certification report for HDP 2.1
* [SPOI-2466] - Monitoring and notifications for cluster
* [SPOI-2475] - Document process to certify demo re-start
* [SPOI-2476] - Document process for grid restart
* [SPOI-2483] - Node.js Kafka Client POC
* [SPOI-2513] - Create demos ui service wrapper compatible with CentOS
* [SPOI-2517] - Configure customer demos ui for as a service
* [SPOI-2531] - HDFSOutputOperator write with exactly once semantics
* [SPOI-2535] - Add support for retrieving Aggregated Counters from Response processStats of StatsListener
* [SPOI-2537] - Need to list previous versions on datatorrent site
* [SPOI-2540] - Fix URL for AWS EMR document
* [SPOI-2551] - Define a process on backend to ensure archive of previous downloads works for customers
* [SPOI-2553] - Holding ticket for Malhar maintenance work


### Sub-task
* [MLHR-774] - Terms of service license
* [MLHR-976] - Implement table module for angular


### Bug
* [MLHR-998] - Compilation error while using UniqueValueCount operator.
* [MLHR-1054] - Update topic and rest calls for Logical/Physical Split
* [MLHR-1056] - Rename demo apps to include Demo suffix
* [MLHR-1089] - Error handling for license page
* [MLHR-1093] - AbstractKafkaInputOperator is not committing the txn to Kafka in commit call back
* [MLHR-1096] - Get last N events when tailing stram events
* [MLHR-1108] - Logical DAG resizing
* [MLHR-1113] - AdsDimension demo fails to launch
* [MLHR-1114] - FraudDetect demo fails to launch
* [MLHR-1115] - MachineData demo fails to launch
* [MLHR-1127] - HdfsTextFileInputOperator Fails during checkpointing
* [MLHR-1138] - Remove unused CPU columns in logical operator table


### Improvement
* [MLHR-1092] - Add environment variable override to rename demo apps
* [MLHR-1098] - Improved code coverage for malhar-angular-dashboard
* [MLHR-1099] - Extend dataModelOptions with non-serializable defaults
* [MLHR-1100] - Improved widget directive in malhar-angular-dashboard
* [MLHR-1116] - Use negative offset to get last N events for stram events widget
* [MLHR-1119] - Add a confirm box when killing app master container
* [MLHR-1120] - Save range selection between page loads for stram events

### New Feature
* [MLHR-783] - DAG should adjust in height as the widget height changes
* [MLHR-784] - WidgetOutputOperator - Schema Update
* [MLHR-984] - STRAM decisions widget
* [MLHR-1070] - Web Demos - Upgrade to AngularJS 1.2.16
* [MLHR-1076] - Widget Library - WebSocket
* [MLHR-1077] - Widget Library - Data Models
* [MLHR-1087] - Dashboard Component - AngularJS Scope Documentation
* [MLHR-1088] - Dashboard Web App - Dependencies Documentation
* [MLHR-1095] - Node.js Kafka Integration
* [MLHR-1097] - Implement storage on malhar-angular-dashboard
* [MLHR-1118] - Add storage hash for clearing out invalid dashboards

### Story
* [MLHR-719] - Time Series Forecasting
* [MLHR-1060] - Widget Library
* [MLHR-1061] - Dashboard Component
* [MLHR-1082] - Parent jira for Real Time ETL Application

### Task
* [MLHR-700] - Develop operator for calculating Coefficient of Determination (RSquare)
* [MLHR-841] - Demo guide for machine data application
* [MLHR-850] - Demo guide for Ads Dimension demo
* [MLHR-852] - Demo guide for Twitter (rolling topwards) demo application
* [MLHR-874] - Demo guide for charting demo - Yahoo finance
* [MLHR-896] - widget output operator - widget type should not be decided in backend
* [MLHR-950] - Create a demo for distributed distinct
* [MLHR-953] - Set up "upgrade path" for CustomerApplications
* [MLHR-983] - UI to expose the "events" API of the gateway
* [MLHR-1042] - ETL: Consolidate output operators properties
* [MLHR-1063] - Create contributing section on the main page of malhar repo
* [MLHR-1064] - Create contributing secion on main page of UI repos
* [MLHR-1065] - create line chart operator
* [MLHR-1075] - add .travis.yml file to ui-console
* [MLHR-1078] - Update license header script, keep year updated
* [MLHR-1080] - create real time chart output operator
* [MLHR-1083] - Consolidate realtime output operator properties
* [MLHR-1084] - Consolidate aggregate operator properties
* [MLHR-1085] - Consolidate linechart operator properties
* [MLHR-1104] - Design App Bundle and Upload/Launch Feature





Version 1.0.0
------------------------------------------------------------------------------------------------------------------------

### Bug
* [SPOI-2086] - creation of logs directory under .dt folder of user
* [SPOI-2497] - Remove hard-coded "hdfs" scheme 
* [SPOI-2501] - dt.log not written under CDH5 GA
* [SPOI-2577] - After installation, I cannot launch license agent
* [SPOI-2604] - The example DFS directory should be changed from /home/... to /user/...
* [SPOI-2607] - Install page should only list error (not warnings) issues
* [SPOI-2609] - When yarn.scheduler.minimum-allocation-mb is set to 256, PiDemo fails with NPE

### Improvement
* [SPOI-2522] - Replace InputPort.getStreamCodec method with an attribute on InputPort called StreamCodec
* [SPOI-2576] - Change local install from .datatorrent to datatorrent directory
* [SPOI-2603] - installer complains about gateway has trouble starting but it actually runs OK
* [SPOI-2637] - Improve the Getting Started Guide

### Task
* [SPOI-2520] - Change the name of the CustomStats to Counters
* [SPOI-2578] - Check dir before mkdir call (MapR requirement)
* [SPOI-2579] - Take out launch from gateway webservice spec document
* [SPOI-2649] - Update software license

### Bug
* [MLHR-1101] - Install errors formatting
* [MLHR-1103] - Change installer instructions for DFS directory path


Version 0.9.5.1
------------------------------------------------------------------------------------------------------------------------

### Bug
* [SPOI-2554] - Third party libraries which are required for demos are missing from /opt/datatorrent/releases/version/lib/
* [MLHR-1113] - AdsDimension demo fails to launch
* [MLHR-1114] - FraudDetect demo fails to launch
* [MLHR-1115] - MachineData demo fails to launch


Version 0.9.5
------------------------------------------------------------------------------------------------------------------------

### Sub-task
* [SPOI-1692] - Certify fault tolerance for multiple containers failure
* [SPOI-1693] - Develop automated test scenario for StrAM failure to certify one of high availability aspects. 
* [SPOI-2008] - Setup virtual cluster for high availability certification
* [SPOI-2009] - WordCount app to be used in certification of high availability
* [SPOI-2127] - Error/Warning message not clear - nightly build installer (datatorrent-dist-0.9.4-SNAPSHOT.bin) if executed as non-root user.
* [SPOI-2128] - Nightly build installer needs to check if port 9090 is available before attempting to run dtgateway service.
* [SPOI-2129] - Error/Warning message not clear while updating the Hadoop configuration through Installer-Web-based UI
* [SPOI-2247] - Gateway user authentication REST API spec
* [SPOI-2248] - Implement user authentication and basic authorization in gateway
* [SPOI-2255] - Password protect the web socket
* [SPOI-2257] - Support HTTPS in gateway
* [SPOI-2277] - Support HTTPS and auth in pubsub connection from stram to Gateway
* [SPOI-2291] - Copy GW configurations to HDFS on every write

### Technical task
* [SPOI-2005] - Verify and add Machine demo to app memory usage automation

### Bug
* [SPOI-1801] - Mobile app has two logical input gen - Need to handle containers on servers with two diff clocks
* [SPOI-1890] - Application behavior when resources are not available
* [SPOI-1954] - Incorrect Processed Stats
* [SPOI-1995] - Sandbox instructions are outdated
* [SPOI-1998] - Killing of node manager on node running License AM
* [SPOI-2067] - Move apps from contrib to demos
* [SPOI-2152] - Stabillity of mobile demo
* [SPOI-2194] - Gateway start script prints out repetitive message
* [SPOI-2205] - Make generate license tool work with web tool to generate 1TB license in the new flow
* [SPOI-2207] - Deduper showed high latency and crashed in staging environment.
* [SPOI-2221] - Analyze FileSystem.get calls and if necessary replace them with FileSystem.newInstance
* [SPOI-2278] - Relative hdfs path should be created under application directory
* [SPOI-2283] - Do not make assumption about FSStorageAgent being the StorageAgent or the default configuration for it being the configuration the user set
* [SPOI-2284] - User 'dtadmin' should be added to the group having access to hadoop services and hdfs
* [SPOI-2285] - uninstall.sh does not uninstall the platform
* [SPOI-2288] - NullPointerException in buffer server
* [SPOI-2289] - FSStorageAgent store throws java.nio.channels.ClosedChannelException 
* [SPOI-2295] - Monitoring and fixing the bugs in Customer demos
* [SPOI-2297] - Mobile Demo going to unstable state due to out of order tuple sequence error
* [SPOI-2298] - Events returned from REST API has funky keys
* [SPOI-2302] - Normalize WebSocket & REST format for Stram Events
* [SPOI-2314] - Fix application names
* [SPOI-2315] - node1 application launch-xxx macros not working after upgrade
* [SPOI-2342] - DTCLI ignoring annotated Application Names
* [SPOI-2344] - dtcli fails to load dt-env.sh
* [SPOI-2349] - Update default license to 4 months
* [SPOI-2357] - Unable to launch application using launch alias, if the application names shown in the dtcli list are picked from dt-site.xml.
* [SPOI-2358] - Installer bin extrac does not preserve permissions
* [SPOI-2359] - Gateway fails to restart due to missing JAVA_HOME
* [SPOI-2361] - After global install local .dt directory may be missing when executing dtcli
* [SPOI-2364] - Catastrophic Error- tuples out of sequence in Generic Node
* [SPOI-2365] - Hadoop Shell throws exception for dt.attr.APPLICATION_PATH
* [SPOI-2371] - DTCLI updating the dt-site.xml
* [SPOI-2373] - Sandbox dt-site.xml is missing configurations related to Map reduce applications.
* [SPOI-2374] - The apps in sandbox use 1GB as the container size and not 512MB as specified under misc/sandbox/conf/dt/dt-site.xml
* [SPOI-2375] - configuration from dt-site.xml in user's directory is not picked by dtcli
* [SPOI-2376] - Gateway classpath references invalid directory
* [SPOI-2380] - get-physical-operator-properties wrong help text
* [SPOI-2389] - DataTorrent discovers override dt-site.xml in CLASSPATH
* [SPOI-2390] - DTGateway is killed after terminal is closed
* [SPOI-2391] - dtdemos service does not stop on sandbox
* [SPOI-2395] - Missing FraudDetection/AdsDeminsions/MachineData demos from sandbox.
* [SPOI-2396] - gateway not started after stopping and starting hadoop/datatorrent services in sandbox.
* [SPOI-2398] - Extra directory created by gateway in user home
* [SPOI-2400] - An operator exits normally when there is OutOfMemory error 
* [SPOI-2401] - The AppMaster finishes after retrying 6 times to deploy input operator
* [SPOI-2412] - App restart HDFS file permission issue on CDH cluster
* [SPOI-2417] - DTGateway dt-site.xml backup location
* [SPOI-2419] - Ensure principal name propagates to containers in non-secure mode
* [SPOI-2435] - Latest changes to latency calculation break tests.


### Improvement
* [SPOI-1376] - Have app specific configuration to stram-site.xml in sandbox
* [SPOI-1855] - Ability to continue/shutdown application
* [SPOI-1986] - In Logical View do not include the unifier stats
* [SPOI-2001] - Update Release Process document (GDrive)
* [SPOI-2222] - Constraint format in license file to be in JSON
* [SPOI-2287] - Allow specifying a complete list of dependencies while deploying the application
* [SPOI-2335] - Make BaseOperator Java Serializable
* [SPOI-2367] - Create service wrapper for demos server
* [SPOI-2385] - Improve the performance of HDFSStorage for POC
* [SPOI-2404] - Reset the Application Failure Count upon successful recovery
* [SPOI-2405] - Add more params to /ws/v1/applications/{appid}/events call
* [SPOI-2407] - Need ability to supply the class name representing the property

### New Feature
* [SPOI-91] - Design and implement a socket adapter operator
* [SPOI-2007] - Automation to certify High Availability
* [SPOI-2012] - Run the app-memory-usage with lower container sizes starting from 128M to 512M when the grid is restarted.
* [SPOI-2249] - Simple user authentication / authorization support in the UI
* [SPOI-2355] - Add REST call to make existing license file the current license
* [SPOI-2386] - REST call to retrieve the datatorrent conf directory
* [SPOI-2399] - Starter Web Application

### Story
* [SPOI-2215] - Password protect the dashboard

### Task
* [SPOI-746] - DT Phome home customer side work
* [SPOI-1642] - Certify support for node failure
* [SPOI-2045] - Discuss license cleanup/improvements
* [SPOI-2099] - Show mandatory fields with '*' in the installer
* [SPOI-2101] - Say "Terms of Service" on the text
* [SPOI-2103] - Show error message on the side
* [SPOI-2117] - An error during uninstall
* [SPOI-2118] - 1 yr license mail not getting mailed
* [SPOI-2145] - Set up separate access to jars for big customers 
* [SPOI-2178] - Filters HashMap from HDFSLoader
* [SPOI-2190] - Create web page (navigator and table view) for 5 dimensions and 2 computations
* [SPOI-2201] - Create a upgrade license page
* [SPOI-2202] - Upgrade Machine Data to latest code
* [SPOI-2211] - Getting too many deprecated warnings in demos
* [SPOI-2213] - Be able to diagnose Stram decisions
* [SPOI-2214] - Ability to access Stram decisions for failed/finished/killed app
* [SPOI-2216] - Upgrade Twitter Demo to latest Code
* [SPOI-2217] - Upgrade Fraud Detection Demo to latest Code
* [SPOI-2218] - Upgrade Ads Dimension Demo to latest Code
* [SPOI-2219] - Upgrade Mobile Locator Demo to latest Code
* [SPOI-2224] - Fraud demo issues 
* [SPOI-2225] - Issues with Machine Data Demo
* [SPOI-2226] - Issues with Ads demo
* [SPOI-2233] - Remove max num container parameter that is included by default
* [SPOI-2234] - Give warning when operators are automatically inlined
* [SPOI-2237] - CPU column on logical view
* [SPOI-2243] - Use hammerdb to generate load against Oracle
* [SPOI-2256] - Document certification suite used to certify datatorrent platform
* [SPOI-2286] - Implement Goldengate java handler to capture db change and send to kafka
* [SPOI-2290] - Hide configuration and launch app for GA
* [SPOI-2292] - Add to README: not recommended to launch more than one gateway
* [SPOI-2293] - Manage license file on HDFS
* [SPOI-2303] - Make DFS error keys more fine grained 
* [SPOI-2309] - Use connection to RM to guess the cluster accessible IP address for GATEWAY_CONNECT_ADDRESS
* [SPOI-2310] - Allow different filesystem from fs.defaultFS for dt.dfsRootDirectory
* [SPOI-2338] - The "#" in the boxes should not change
* [SPOI-2351] - Bundle the default passwd file (with admin/admin) in the installer
* [SPOI-2362] - Create service wrappers for Apache Hadoop on Sandbox
* [SPOI-2363] - Update dtdemo sandbox script to work with Hadoop/DTGateway service wrappers
* [SPOI-2394] - Install wizard shows up again after gateway restart
* [SPOI-2416] - Separate malhar and malhar-ui-console
* [SPOI-2418] - Create an ability for the DTFlumeSink to backoff if it suspects that the DAG is not processing the data in healthy fashion.
* [SPOI-2421] - Update end-user documentation


### Sub-task
* [MLHR-726] - Time Series Forecasting Operator using Holt's Linear Trend Model
* [MLHR-933] - Time Series Forecasting using Holt-Winters' Seasonal Method
* [MLHR-965] - create non transactional output operator
* [MLHR-966] - create transactional output operator
* [MLHR-967] - create a data store writer implementation to use in real time etl app
* [MLHR-1036] - Create incremental model for Holt's Linear Trend Forecasting Algorithm
* [MLHR-1040] - Develop incremental model creation for Holt-Winters' Multiplicative Method Time-Series Forecasting


### Bug
* [MLHR-778] - Logical Operators list has no palette
* [MLHR-857] - Machinedata demo stop working with new Redis operator
* [MLHR-963] - create output operator to add historical data to supplied datastore
* [MLHR-964] - create interface for data stores that can be used by output operator to persist historical data
* [MLHR-968] - Remove test related code from AbstractTransactionableStoreOutputOperator
* [MLHR-969] - Create a manageable version of our demo docs to be included with our installation
* [MLHR-978] - create resource leak for the hdfs input/output operators
* [MLHR-979] - AdsDimension: Redis operator shows high latency
* [MLHR-986] - Page Not Found errors from the web-site
* [MLHR-1000] - Invalid IP address selected by default during upgrade
* [MLHR-1005] - CPU column on logical view
* [MLHR-1008] - twitter application failed with exception
* [MLHR-1015] - State is missing from physical operator overview widget
* [MLHR-1019] - Make gateway ip and port inputs on same line in installer
* [MLHR-1020] - License screen does not reflect new license upload
* [MLHR-1021] - Unifiers should not have link to nonexistent logical operator
* [MLHR-1022] - Update installer license text to reflect correct trial period
* [MLHR-1028] - Cannot kill application in state ACCEPTED
* [MLHR-1030] - Sorting on logical operators list fails until you sort on name
* [MLHR-1031] - UI Showing wrong total Memory usage
* [MLHR-1049] - Streams not showing up in dag overview
* [MLHR-1050] - Remove the "Development" mode
* [MLHR-1055] - Unnecessary gateway restart requested during installation navigation
* [MLHR-1057] - Overview in dag widget not accurate to visible area
* [MLHR-1058] - Change install wizard from widget in a page to just a page
* [MLHR-1066] - Install Wizard tab order and auto-focus
* [MLHR-1067] - Install Wizard invalid DFS directory check
* [MLHR-1072] - Socket input operator test fail
* [MLHR-1074] - Remove stram events page/widget from 0.9.5


### Improvement
* [MLHR-721] - Migrate database cache lookup to the new db framework
* [MLHR-985] - AdsDimension: Plug-in Dimension Unifier 
* [MLHR-1010] - Remove info icon from installer text
* [MLHR-1011] - Change "property" to "item" in install step tables
* [MLHR-1012] - Review and edit installer text
* [MLHR-1013] - Installer: Rework Hadoop and System screens
* [MLHR-1035] - Remove darker grey background from console
* [MLHR-1046] - Operators/Containers not being subscribed to on App Page
* [MLHR-1062] - Install Wizard examples of Hadoop and DFS path
* [MLHR-1069] - License summary section in Install Wizard

### New Feature
* [MLHR-684] - Invalidate dashboard state from previous versions
* [MLHR-881] - ETL Web App - Packaging
* [MLHR-882] - ETL Web App - Dashboard
* [MLHR-885] - ETL Web App - Sample Data Generation
* [MLHR-997] - ETL Web App - Historical Data from MongoDB
* [MLHR-1014] - Remove config properties edit page, replace with config home
* [MLHR-1052] - Bar Chart Widget
* [MLHR-1053] - Widget Library - Demo Application

### Story
* [MLHR-703] - Logstream UI
* [MLHR-709] - Widgets Library as Independent Project

### Task
* [MLHR-661] - Migrate JDBC adapters to use the new database adapter interface
* [MLHR-866] - Annotate all stateless operators in Malhar as such
* [MLHR-868] - Demo Guide for Map-Reduce Operator - LogsCountApplication
* [MLHR-869] - Demo guide for Map-Reduce Operator - NewWordCountApplication.
* [MLHR-870] - Demo guide for Map-Reduce Operator - InvertedIndexApplication.
* [MLHR-922] - Machine data demo is using deprecated attributes. Gives warnings on launch
* [MLHR-951] - Remove deprecated warnings from demos
* [MLHR-954] - Need to debug older demos
* [MLHR-961] - Develop a Goldengate input adapter
* [MLHR-970] - Re-create the application that we build for iAd Poc in Malhar
* [MLHR-1006] - In Logical View do not include the unifier stats
* [MLHR-1007] - Simple user authentication/authorization support in UI
* [MLHR-1018] - Need a Kafka-HBase app
* [MLHR-1023] - Update installer text on welcome screen
* [MLHR-1024] - Create issues summary page under configuration
* [MLHR-1025] - Add progress status indicator for installer wizard
* [MLHR-1026] - Reorder install wizard screens
* [MLHR-1027] - Remove external upgrade link from licensing screen
* [MLHR-1041] - ETL : Consolidate input operator properties in json format
* [MLHR-1044] - ETL: Add input operator to ETL Application in ETL branch
* [MLHR-1071] - Create stateless deduper - aka deduper which forgets its state upon failure or repartitioning





Version 0.9.4
------------------------------------------------------------------------------------------------------------------------

### Bug
* [SPOI-455] - Cleanup maven repository workaround in install.sh
* [SPOI-1636] - Update all node1 demo to 0.9.3 release
* [SPOI-1774] - Thread local performance drop from 65M to 40 M tuplesProcessed/sec
* [SPOI-1775] - MROperator demo applications fail when launched from Sandbox
* [SPOI-1847] - Intermittent - WebSocket Publishing ignores endWindow
* [SPOI-1864] - POC partitioned operators not getting correct initial state
* [SPOI-1866] - Datatorrent applications not starting on CDH5 Vagrant cluster
* [SPOI-1867] - Investigate InstallAnywhere use for DataTorrent installation
* [SPOI-1882] - When not able to contact license agent, the application should not die
* [SPOI-1883] - Stram crashes with Unknown-Container issue
* [SPOI-1885] - Determine minimum amount of memory needed to run twitter app
* [SPOI-1886] - Determine minimum amount of memory needed to run mobile app
* [SPOI-1888] - Install license in the new console configuration
* [SPOI-1889] - Licensing needs to support eval and free
* [SPOI-1902] - Dynamic MxN partitioning does not handle scale down to single M instance 
* [SPOI-1903] - MiniClusterTests fails because ~/.dt/dt-site.xml dependency
* [SPOI-1906] - history does not get flushed to the history file until the next command prompt
* [SPOI-1917] - Licensing error
* [SPOI-1922] - Loading license does not work
* [SPOI-1923] - Close button does not work in several pop-up windows
* [SPOI-1936] - No uninstall script available with the installer. 
* [SPOI-1953] - Installation video on our website should be refreshed to reflect the latest version(s)
* [SPOI-1960] - application incorrectly marked as succeeded
* [SPOI-1968] - 404 for logical plan url
* [SPOI-1970] - Negative requested container count logged by Stram
* [SPOI-1976] - Fix AdsDimensions in certification 
* [SPOI-1992] - the latency in the application overview freezes after a container gets killed.
* [SPOI-1999] - Evaluate Yarn cluster issue
* [SPOI-2002] - Gateway fails to load properties
* [SPOI-2037] - Redirect to welcome page on first run / install
* [SPOI-2039] - DTGateway logs to .dt/logs in service mode
* [SPOI-2040] - Apache logs application under contrib folder fails to run
* [SPOI-2047] - dtgateway service not starting when machine boots
* [SPOI-2049] - Better error message on invalid hadoop directory
* [SPOI-2051] - RPM install reports install script failure
* [SPOI-2052] - DTGateway restart fails when running with -service
* [SPOI-2055] - dtgateway service reports OK on startup failure
* [SPOI-2056] - LicensingAgentProtocolHelper.getLicensingAgentProtocol gets stuck when YARN is not running
* [SPOI-2057] - DTCLI is not working after intallation
* [SPOI-2058] - launch-demos macro not available after installing the platform from self extracting intaller
* [SPOI-2059] - Show understandable error message if the root hdfs directory could't be created
* [SPOI-2060] - UI Shows Nan B in Allocated Memory
* [SPOI-2062] - Gateway needs to check hadoop version
* [SPOI-2064] - dtgateway-ctl stop doesn't work
* [SPOI-2065] - Readme File is not udpated
* [SPOI-2066] - installer not recognizing -l option
* [SPOI-2070] - Installer: echo_success command doesn't work with Ubuntu
* [SPOI-2073] - Invalid Ip Address in Installer UI
* [SPOI-2074] - install script needs to check hadoop version
* [SPOI-2075] - lauch-local-demos
* [SPOI-2076] - Licensing agent RPC gives NPE
* [SPOI-2077] - Installer: we need a separate page for hadoop installation directory 
* [SPOI-2078] - Change the certification and benchmarking script and code to use the new location of benchmarking apps
* [SPOI-2083] - install script, when run by rpm, complains about invalid group dtadmin
* [SPOI-2088] - Map Reduce demo applications still show the classnames when listed using launch-demos
* [SPOI-2089] - demo applications displayed after running the launch-demos command should be in alphabetical order
* [SPOI-2090] - Error while requesting evaluation license from Datatorrent.com
* [SPOI-2094] - Installer throws failed message while stopping gateway 
* [SPOI-2097] - launch-demos macro not available after installing the platform from self extracting intaller
* [SPOI-2098] - App names still have full classpath
* [SPOI-2120] - Installer - Restart Modal is not closed after Restart Failed (Happened Once)
* [SPOI-2132] - Ensure HDFS does not blow up with millions of files per sec
* [SPOI-2133] - Delete old files to ensure NN does not crash
* [SPOI-2134] - Send POC1 to customer
* [SPOI-2143] - Spelling error and reference to $HOME/.datatorrent
* [SPOI-2146] - Move Kafka benchmark apps to contrib folder
* [SPOI-2148] - Installer - Disable Closing Modals on Click
* [SPOI-2149] - Address the confusion around gateway address.
* [SPOI-2151] - User is not able to change the defaultFS during installation
* [SPOI-2153] - Cryptic error message when launching app on node0
* [SPOI-2157] - Getting logical plan returns error when one of the getters is bad
* [SPOI-2159] - gateway is polling resourcemanager for appinfo w/o subscriber
* [SPOI-2163] - Change directory before DTGateway launch
* [SPOI-2165] - Installer - add reload ability to System screen
* [SPOI-2170] - DTGateway classpath is duplicated after restart
* [SPOI-2171] - Remove reload button from System configuration screen
* [SPOI-2172] - Installer may display invalid port after starting DTGateway
* [SPOI-2173] - Installer base location change not working
* [SPOI-2192] - CLI command for getting list of operator classes from a jar
* [SPOI-2193] - CLI command for getting properties of a operator class from a jar
* [SPOI-2206] - dag view does not get rendered property in Firefox
* [SPOI-2227] - (Re)start license agent when license file is uploaded
* [SPOI-2229] - container local operators not redeployed
* [SPOI-2238] - Installer complains about sudo running as root
* [SPOI-2241] - DAG Firefox 28 Support


### Improvement
* [SPOI-1311] - Review platform documentation
* [SPOI-1567] - Certify against commercial Hadoop distributions
* [SPOI-1769] - Trying to kill a non dt app can return a better message
* [SPOI-1844] - Ship project-template with a log4j.properties file with debugging level set to INFO
* [SPOI-1852] - WebSocket client recovery logging
* [SPOI-1853] - Create WebSocket clients in containers on demand
* [SPOI-1854] - Option to retrieve only running and recently-ended apps
* [SPOI-1856] - Need something that is like LicensingAgentClient but not specific for stram.
* [SPOI-1857] - Gateway to warn about available licensed memory being low
* [SPOI-1858] - CLI to directly connect to license agent to get live license info
* [SPOI-1859] - Gateway to directly connect to license agent to get live license info
* [SPOI-1861] - Gateway command to restart itself
* [SPOI-1869] - Add UI build script to dist build file
* [SPOI-1874] - the first operator that stalls for more than specific period, take it out so as to unclog the processing
* [SPOI-1899] - Add appmaster container to container list
* [SPOI-1904] - Updates needed to the README file
* [SPOI-1911] - Run certification as part of nighty build
* [SPOI-1915] - Using $DT_HOME in README 
* [SPOI-1961] - Show the activation date of the license with list-license-agent command 
* [SPOI-1965] - The file demos.jar should be installed by default by the Installer
* [SPOI-1978] - Manual eval request (by e-mail) - template  
* [SPOI-1980] - DT Version in license request and generated license
* [SPOI-1981] - Approve / update license verification e-mail
* [SPOI-1997] - Certify against commercial Hadoop distributions
* [SPOI-2026] - Add support to LogicalPlan for testing dag serialization
* [SPOI-2150] - Update Readme file for the local install
* [SPOI-2155] - Installer - Validate Fields on blur event
* [SPOI-2156] - Installer - Navigation Code Cleanup
* [SPOI-2158] - Installer - CSS Classes
* [SPOI-2160] - Installer font size
* [SPOI-2166] - Configuration screen navigation panel
* [SPOI-2174] - Notify user with installation location and version
* [SPOI-2175] - Notify user about local DTGateway management during installation
* [SPOI-2188] - Installer - Register Instructions

### New Feature
* [SPOI-328] - Add annotation to declare the operator stateless
* [SPOI-393] - High Availability for STRAM
* [SPOI-868] - Setting operator properties as different types
* [SPOI-1182] - Add Key-based filter functionality to malhar library for Min, Max, SimpleMovingAverage, StandardDeviation like operators
* [SPOI-1654] - Logstream - aggregate top hits and bytes for URL, geo DMA, IP, URL/status code, url
* [SPOI-1747] - create a filter operator to output multiple records based on filter
* [SPOI-1756] - configuration for input adaptor
* [SPOI-1757] - configuration for filter operator
* [SPOI-1758] - configuration for dimension operator
* [SPOI-1759] - configuration for aggreagation operator
* [SPOI-1760] - configuration for web socket output
* [SPOI-1849] - add dt HDFS directory in configuration 
* [SPOI-1907] - Installer: HDFS directory creation attempt via Gateway (as part of config updates) 
* [SPOI-1909] - Port re-selection by Gateway if 9090, 9091, 9092, etc are taken
* [SPOI-1913] - Automate verifing the app memory for the demos
* [SPOI-1928] - gateway needs to be able to start with standalone hadoop jar (without hadoop installation)
* [SPOI-1929] - /ws/v1/about to include java version and hadoop location
* [SPOI-1930] - New installation script
* [SPOI-1966] - dtcli should be enabled to list app names (if available) as opposed to app class path
* [SPOI-1974] - Add throughput,  totalTuplesProcessed and elapsed time to performance benchmarking
* [SPOI-1975] - Display throughput, tuplesProcessed per sec and latency in a tabular format.
* [SPOI-1987] - Copy License to Front-End Distribution
* [SPOI-2003] - Verify and add all the demos except Machine data to app memory usage automation
* [SPOI-2011] - Make a separate jar file for performance benchmarking demos
* [SPOI-2013] - Support for doc link as an attribute for the application
* [SPOI-2018] - Have a launch-performance command in dtcli
* [SPOI-2021] - Rename all the apps under contrib to have meaningful names
* [SPOI-2023] - Make a launch-contrib command available in stram cli
* [SPOI-2027] - Packaging benchmarking demos
* [SPOI-2042] - redirect user to welcome screen if dt.configStatus is not "complete"
* [SPOI-2044] - set property dt.configStatus to "complete" when the user has completed the config wizard
* [SPOI-2122] - Installer - Offline Email Template
* [SPOI-2147] - Provide separate dt benchmarking package scripts to throughput and hdfs operators benchmarking
* [SPOI-2195] - Gateway REST API to return operator classes in a jar given superclass (or not)
* [SPOI-2196] - Gateway REST API to return properties of an operator in a jar 
* [SPOI-2200] - Installer - License Flow

### Story
* [SPOI-1608] - Platform Benchmarking (Platform1 and Platform2)

### Task
* [SPOI-722] - Document ads demo (add comments to codebase)
* [SPOI-1403] - HDFS Operator Benchmark
* [SPOI-1411] - Deprecate old Malhar webdemos once logstream is available
* [SPOI-1513] - datatorrent.com webapp development - app testing
* [SPOI-1610] - Develop benchmarking app for AdsDimension App (exactly once semantics) - Platform1
* [SPOI-1612] - Benchmarking Ads Dimension demo app on Morado cluster (exactly once semantics) - Platform1
* [SPOI-1618] - Benchmarking Machine Data app with Platform1
* [SPOI-1694] - Document DT SandBox preparation
* [SPOI-1730] - Default License in git needs to be replaced by the license cut by the real key 
* [SPOI-1732] - Create the real public/private key for licenses and store the private key in a safe place.
* [SPOI-1745] - Document Demo Application Setup
* [SPOI-1788] - CLI commands for licensing
* [SPOI-1794] - Create license info as a string 
* [SPOI-1796] - Soft enforcement for normal paid app. 200% bump?
* [SPOI-1848] - Gateway to support changing and getting config parameters
* [SPOI-1851] - Document virtual cluster setup
* [SPOI-1862] - Working on creating Wire Frames for the Installation of DT Platform
* [SPOI-1863] - Make installer work w/o Maven
* [SPOI-1865] - Allow user to configure application classpath
* [SPOI-1868] - Support Book Keeping in the HDFSStorage
* [SPOI-1870] - Validate dtcli generate-license-request
* [SPOI-1872] - Modify generatelicense process
* [SPOI-1873] - License process via console
* [SPOI-1876] - Application Developer Guide Improvements
* [SPOI-1877] - Download and build JDK Standrd Doclet Source as part of DT 
* [SPOI-1878] - DT Console Web UI Testing on Chrome
* [SPOI-1879] - DT Console Web UI Testing for Demo Apps on Chrome
* [SPOI-1884] - Operater developer guide review 
* [SPOI-1891] - Add allatori documentation
* [SPOI-1892] - Add automatic build of front components to distribution
* [SPOI-1893] - Quick Start Guide
* [SPOI-1914] - cli get-app-info to include info from hadoop
* [SPOI-1926] - Call license web service and return license file
* [SPOI-1927] - Returns license request blob for UI to assemble mailto link
* [SPOI-1939] - Twitter Top Counter Demo Applications Guide
* [SPOI-1940] - RPM packaging for installer
* [SPOI-1941] - Include demo UI into installer
* [SPOI-1942] - Remove Allatori code expiration for GA
* [SPOI-1943] - include more info in the license request 
* [SPOI-1945] - Add REST call to gateway to post license file
* [SPOI-1946] - virtual cluster configuration changes
* [SPOI-1947] - Create license@datatorrent.com
* [SPOI-1949] - Java application (with main method) that returns information given a license request blob
* [SPOI-1956] - License generation key pair expiration / private key protection
* [SPOI-1963] - Evaluate Doclava Doclet from Google
* [SPOI-1982] - E-mail verification success web page 
* [SPOI-1988] - Review Quick Start Guide
* [SPOI-1989] - AdsDimension - Demo Applications Guide
* [SPOI-1990] - Twitter Rolling Top Words Counter - Demo Applications Guide
* [SPOI-2004] - Installer testing for GA
* [SPOI-2006] - Grant Google Analytics Access To Following People
* [SPOI-2010] - Configure the apps to use minimum memory as verified by app-memory-usage-automation.
* [SPOI-2015] - Get Machine data into contrib.jar
* [SPOI-2016] - Fraud Detection in contrib.jar
* [SPOI-2017] - Quick Start Guide version 2
* [SPOI-2019] - List NxN performance apps (different event size vs different stream locality
* [SPOI-2025] - Getting Start Guide - Launch this copy.
* [SPOI-2032] - Certify Cloudera CDH 5.0
* [SPOI-2048] - Uninstall script
* [SPOI-2050] - Start gateway as service flag
* [SPOI-2069] - Test Installer
* [SPOI-2091] - Update installation license agreement
* [SPOI-2093] - Verify demo UI is bundled with installer
* [SPOI-2100] - For terms of service box, change "continue" to "accept and continue"
* [SPOI-2106] - Change the message on 1 yr registration
* [SPOI-2107] - Change the message on 1 yr registration
* [SPOI-2108] - Put timeglass and "loading" or spinning.... while Hadoop system properties are being loaded
* [SPOI-2109] - Gateway down creates bad error message
* [SPOI-2110] - Remove errors popping on the right hand of console
* [SPOI-2111] - If gateway outage is discovered add a message to get them back
* [SPOI-2112] - Change the message on Hadoop screen
* [SPOI-2114] - Error if HDFS does not exist
* [SPOI-2115] - Create a list of issues summary screen
* [SPOI-2116] - Show more instructions on the completed screen
* [SPOI-2131] - Ingestion POC
* [SPOI-2136] - Do cartesian products for key, val pair
* [SPOI-2142] - Allow customization of cartesian product 
* [SPOI-2161] - prereq message on welcome screen
* [SPOI-2162] - DFS error message
* [SPOI-2164] - DFS location validation
* [SPOI-2167] - Evaluate errors in Cloudera certification
* [SPOI-2223] - Test if all the applications with reduced container memory sizes run in sandbox 0.9.4.
* [SPOI-2230] - Uninstaller for RPM
* [SPOI-2231] - Provide Environment with Running Demos
* [SPOI-2240] - Set Up DataTorrent Demos on Dev Environment


### Sub-task
* [SPOI-1682] - Too many mbassy threads!!!
* [SPOI-1718] - Update HA Documentation
* [SPOI-1729] - Restore operator recovery checkpoints in AM recovery 
* [SPOI-1786] - Users should be able to generate license at datatorrent.com
* [SPOI-1931] - Installer - determine OS type and version
* [SPOI-1932] - installer with sudo/root user creation, service installs
* [SPOI-1933] - service wrappers for DTGateway
* [SPOI-1934] - HDFS directory creation during install
* [SPOI-1935] - Search for hadoop binaries standard paths
* [SPOI-1958] - Create HDFS Word input operator
* [SPOI-1962] - Add test to jekins nightly build
* [SPOI-1971] - Verify launch script for other apps from demo 
* [SPOI-1972] - When some app fail, the main monitor should still keep looking at the other apps
* [SPOI-2028] - Provide shell script 'benchmark-throughput' to produce a single summary table 
* [SPOI-2030] - Provide a list of individual demos used for benchmarking through dtcli benchmarking, so that the user can launch the demos individually.
* [SPOI-2031] - Package benchmarking suite into the installer and sandbox
* [SPOI-2046] - Update licenses location in installation script
* [SPOI-2053] - Certify CDH5.0 as part of Cloudera certification for inclusion in their process
* [SPOI-2054] - Certify installer on HW
* [SPOI-2079] - Run certification on bin install
* [SPOI-2085] - Change the certification resource xml files to contain the certification type.




### Bug
* [MLHR-729] - Columns in table wrap in Firefox
* [MLHR-730] - Dev server does not escape double-quotes in error message
* [MLHR-732] - Links Outline in Firefox
* [MLHR-754] - JarList and DepJarList headers point to nonexistent text items
* [MLHR-767] - "FINISHING" has no icon in status
* [MLHR-785] - NaN in file size column of jar list
* [MLHR-809] - Inconsistent landing page across browsers
* [MLHR-814] - Selecting operators in the logical operators widget does not activate any actions
* [MLHR-816] - Names of partitions in the partitions widget should not be shown as links
* [MLHR-817] - Clickin on 'outputPort' leads to PageNotFound error
* [MLHR-824] - Don't show license agent detail when license agent is not running
* [MLHR-826] - Dep Jars fail to load in specify dep jars modal
* [MLHR-830] - Optimize RandomWordInput operator used in perfromance benhcmarking to use local final variables to improve performance. 
* [MLHR-835] - Fix hard-coded file path in com.datatorrent.demos.wordcount.WordCountInputOperator
* [MLHR-836] - Need AbstractHDFSOutputAdapter
* [MLHR-863] - Add license headers to AbstractHdfsOutputOperator
* [MLHR-879] - Installer - Issues Management
* [MLHR-887] - Input operator that tails a growing log file in a directory
* [MLHR-899] - Give default name for all demo applications
* [MLHR-908] - Mark installation complete with dt.configStatus property
* [MLHR-911] - UI Shows Nan B in Allocated Memory
* [MLHR-912] - Installer - System Section - Show Field Specific Errors
* [MLHR-913] - Installer - System Section - Server-Side Error Messages
* [MLHR-918] - Yahoo finance with Alerts : Modify to accept multiple ticker symbols and remove hard-coded values.
* [MLHR-920] - Give desciptive names to benchmarking apps
* [MLHR-924] - Tail Operator should take care of the truncation of file
* [MLHR-930] - UI container list should not show time for last heartbeat for if the value is "-1"
* [MLHR-938] - gateway address property change
* [MLHR-939] - Put GatewayRestart into "actions" hash in settings.js
* [MLHR-940] - Delete the space in the name
* [MLHR-943] - Change the method name from isConnected to Connected in the db api
* [MLHR-991] - DAG Stream Locality


### Improvement
* [MLHR-731] - Compile LESS on the fly in dev environment
* [MLHR-735] - Remove unused bundling make commands, update README
* [MLHR-745] - Add icon to left widget manager drawer
* [MLHR-746] - Use "cores" not % cpu for cluster metric total cpu usage
* [MLHR-747] - Remove "#" for "number of container", et al labels
* [MLHR-748] - Only load all applications from RM on demand
* [MLHR-749] - Improve notification history pane
* [MLHR-750] - Normalize labels for everything in console
* [MLHR-751] - Add lock where close dashboard icon would be for default dashboard
* [MLHR-753] - Remove avg app age in cluster metrics
* [MLHR-755] - Change "max alloc mem" to "peak alloc mem" in cluster metrics
* [MLHR-756] - Add memory levels to tooltip of license mem gauge in top right
* [MLHR-768] - Remove beefy from npm shrinkwrap
* [MLHR-770] - Clean up BaseUtil, BaseModel, BaseCollection, add tests
* [MLHR-781] - shorten link to log file in container page
* [MLHR-798] - Add "config.adsdimensions.redis.dbindex" configuration in webdemo
* [MLHR-873] - Add equals and hashcode to JdbcOperatorBase
* [MLHR-931] - ETL: Create a converter api and provide an implementation for Json Object to flat map conversion
* [MLHR-935] - Have "silentErrors" option for models and collections
* [MLHR-937] - ETL: Create a unifier for DimensionComputation operator
* [MLHR-947] - Improve overall look and feel of install wizard
* [MLHR-948] - Remove mock issues from SummaryView in installer wizard
* [MLHR-993] - Demo UI - Default Applications Names for Application Discovery

### New Feature
* [MLHR-688] - Discard Real-Time Updates When Page is not Active
* [MLHR-757] - Dashboard - Save Widget Width to Local Storage
* [MLHR-759] - Dashboard - Widget Definitions Collection
* [MLHR-763] - Line Chart Widget - hAxis options
* [MLHR-764] - Dashboard App - Meteor Data Source
* [MLHR-765] - Shutdown Container Interface
* [MLHR-773] - Configuration wizard page
* [MLHR-788] - Web Demos - Redis and MongoDB Config
* [MLHR-789] - Web Demos - Fraud Demo MongoDB Database Name
* [MLHR-790] - Web Demos - Single Configuration File
* [MLHR-791] - Web Demos - Start Script
* [MLHR-792] - Web Demos - Single Page App
* [MLHR-793] - Web Demos - JS/CSS Bundle
* [MLHR-794] - Web Demos - WebSocket Pub/Sub
* [MLHR-795] - Web Demos - Resources Clean Up on Scope Destroy
* [MLHR-796] - Web Demos - Distribution Files
* [MLHR-797] - Web Demos - Running Instructions
* [MLHR-804] - Config Page (Manage Properties)
* [MLHR-805] - Web Demos - Distribution Package Instructions
* [MLHR-806] - Installer - License Requests (REST API Calls)
* [MLHR-807] - Installer - License Text
* [MLHR-818] - Installer - License Section
* [MLHR-819] - Installer - System Properties Section
* [MLHR-820] - Console - Node.js Dev Mode
* [MLHR-821] - Web Demos - Distribution Package Launch Script
* [MLHR-831] - Installer - License Flow
* [MLHR-834] - Installer - License - Registration
* [MLHR-858] - Installer - Gateway Restart
* [MLHR-861] - Installer - System Properties - IP List
* [MLHR-864] - Installer - Handling Hadoop Not Found
* [MLHR-903] - Installer - WebSocket DataSource Disconnect
* [MLHR-909] - Installer - Restart Confirmation
* [MLHR-914] - Installer - Error Messages
* [MLHR-919] - License Bar
* [MLHR-923] - Installer - Properties Update "Loading" Indicator
* [MLHR-925] - Installer Update
* [MLHR-934] - Allow overrides to $.().modal(options) for Modals

### Story
* [MLHR-705] - Node.js Pub/Sub Service
* [MLHR-708] - Evaluate Node.js Pub/Sub Services
* [MLHR-710] - Pie Chart Data Model
* [MLHR-712] - Dashboard App - Historical Data Support
* [MLHR-714] - Dashboard App - MongoDB Integration
* [MLHR-715] - Create Dashboard from Running App - Widgets Auto Discovery
* [MLHR-736] - Console Firefox Support
* [MLHR-737] - Console Safari Support
* [MLHR-801] - Installer/Config UI
* [MLHR-802] - Web Demos - Distribution Package
* [MLHR-803] - Installer (Wizard) Page

### Task
* [MLHR-349] - Add build script to Malhar/front
* [MLHR-402] - Logstream - aggregate top hits and bytes for URL, geo DMA, IP, URL/status code, url
* [MLHR-651] - Use compatible version of jersey/jackson/jetty in Malhar
* [MLHR-659] - Migrate MongoDB adapters to use the new database adapter interface
* [MLHR-741] - Web Apps (Demos) Firefox Support
* [MLHR-744] - Web Apps (Demos) Safari Support
* [MLHR-760] - Dashboard App - Meteor Integration
* [MLHR-761] - Dashboard App - Derby.js Integration
* [MLHR-762] - create install script for ui
* [MLHR-839] - Review guide on MachineData app
* [MLHR-842] - Demo guide for Pi Application
* [MLHR-843] - Demo guide for Twitter Top URL Counter demo application
* [MLHR-851] - Demo guide for Fraud detection demo application
* [MLHR-853] - Demo guide for Mobile demo application
* [MLHR-854] - Demo Guide for Word-Count Application
* [MLHR-855] - Demo guide for Pi Calculator application
* [MLHR-856] - Demo guide for Twitter Rolling Top Words Application
* [MLHR-859] - upgrade kryo to 2.23
* [MLHR-871] - Demo guide for Twitter Top URL Counter - Launch This Copy.
* [MLHR-872] - Demo Guide for Word-Count Application - Launch this copy.
* [MLHR-875] - Demo guide for Yahoo finance application
* [MLHR-876] - Demo guide for Yahoo finance alerting application
* [MLHR-877] - Demo guide for Yahoo finance application with Derby SQL
* [MLHR-892] - ETL logstream application - study the log stream application
* [MLHR-893] - ETL- Use the generic dimension operator that was created for a POC in Log stream 
* [MLHR-900] - ETL- Operators used by logstream application need to be generic and moved to library
* [MLHR-904] - Fix the nightly and trigger builds broken due to removal of api.codec and api.util
* [MLHR-905] - Dedup: Make deduper and bucket manager part of malhar library
* [MLHR-910] - Demo guide for Twitter Rolling Top Words Application - Launch This Copy
* [MLHR-915] - CLONE - Demo guide for Pi Application - Launch this copy
* [MLHR-916] - CLONE - Demo guide for Pi Calculator application - Launch this copy
* [MLHR-917] - CLONE - Demo guide for Mobile demo application - Launch this copy
* [MLHR-936] - Create new Redis Store using Lettuce redis client
* [MLHR-949] - Add confirmation to DTGateway restart button in System Properties
* [MLHR-962] - ETL : Create a sifter operator 
* [MLHR-980] - CLONE - Demo guide for Yahoo finance alerting application - launch this copy
* [MLHR-981] - CLONE - Demo guide for Yahoo finance application - launch this copy
* [MLHR-982] - CLONE - Demo guide for Yahoo finance application with Derby SQL - launch this copy

### Sub-task
* [MLHR-678] - Time Series Forecasting with Simple Linear Regression
* [MLHR-718] - Time Series Forecasting using Simple/Single Exponential Smoothing
* [MLHR-726] - Time Series Forecasting Operator using Holt's Linear Trend Model
* [MLHR-727] - Develop application for a telecom related use case for time series forecasting with Simple Linear Regression and CMA smoothing
* [MLHR-932] - Create Centered Moving Average Smoothing Operator




Version 0.9.3
------------------------------------------------------------------------------------------------------------------------

### New Feature
* [SPOI-261] - Design a general purpose read from stream and write to cassandra
* [SPOI-400] - Each streaming application should license check
* [SPOI-1622] - Input operator - XML parser
* [SPOI-1647] - LogStream UI 
* [SPOI-1770] - Gateway should expose list of available topics
* [SPOI-1778] - Open readme on sandbox startup
* [SPOI-1804] - Start license app on launch app if not running
* [SPOI-1805] - command to show license file info in cli
* [SPOI-1812] - Create REST call for specific license agent, given a license id
* [SPOI-1823] - Gateway REST API - Get Running Applications List
* [SPOI-1829] - Semantic URLs for Web Apps

### Improvement
* [SPOI-1202] - Provide a way to check whether an operator is partitioned
* [SPOI-1783] - Add allocatedMB to main application list
* [SPOI-1789] - Change frequency of heartbeats to license app
* [SPOI-1795] - License file to clearly state hard enforcement or soft enforcement
* [SPOI-1816] - support simple variable substitution in the cli
* [SPOI-1835] - support gateway status command

### Story
* [SPOI-1320] - Support MQTT protocol
* [SPOI-1542] - Input operator - Directory Scan

### Bug
* [SPOI-1696] - Make de-duper dynamically partitionable
* [SPOI-1704] - Stram enforcement to lock physical plan changes when license memory limit is reached
* [SPOI-1706] - Design a enforcement format for the license policy
* [SPOI-1711] - Encryption/obfuscation of communication between stram and license agent
* [SPOI-1779] - Update sandbox documentation terminology
* [SPOI-1802] - Provide total license memory via stram web services
* [SPOI-1807] - Unknown outage on Machine data demo
* [SPOI-1809] - Suppress expected error message in dtgateway-ctl  
* [SPOI-1810] - sample-stram-site.xml generates warnings
* [SPOI-1813] - Add SNAPSHOT repository to install pom
* [SPOI-1815] - Make stram memory reporting to license manager asynchronous 
* [SPOI-1818] - Chance "className" in license file to id
* [SPOI-1820] - dtcli script doesn't exit when maven command fails
* [SPOI-1826] - Update documentation title
* [SPOI-1827] - Install script errors
* [SPOI-1831] - CLI warning about trouble with license manager
* [SPOI-1833] - Use encrypted byte arrays for RPC wire protocol for licensing
* [SPOI-1840] - Change default license memory limit to 25GB
* [SPOI-1841] - Make stram memory enforcement tolerances property settings for the enforcer
* [SPOI-1842] - Investigate the possibility of engine obfuscation jar not containing any references to license package path
* [SPOI-1880] - GET nonexistent container returns 500 error

### Task
* [SPOI-1375] - All sandbox apps must work in 8G VM. Need to test each
* [SPOI-1467] - DB lookup for Cassandra
* [SPOI-1507] - datatorrent.com webapp development - pilot test of Angular and WP integration
* [SPOI-1509] - datatorrent.com webapp development - db design
* [SPOI-1511] - datatorrent.com webapp development - app design
* [SPOI-1512] - datatorrent.com webapp development - app dev
* [SPOI-1515] - datatorrent.com webapp deveopment - integrate standalone app with cms
* [SPOI-1516] - datatorrent.com webapp development - add GA info during registration
* [SPOI-1517] - datatorrent.com webapp development - background jobs
* [SPOI-1617] - Benchmarking Performance app with Platform2
* [SPOI-1641] - Benchmarking Ads Dimension App - Platform2
* [SPOI-1715] - Show remainingLicensedMB and allocatedMB in UI for each application
* [SPOI-1763] - Provide support for Accumulo NoSQL db
* [SPOI-1780] - Sandbox - activate license automatically
* [SPOI-1781] - Sandbox - increase memory to 8GB
* [SPOI-1782] - License App should use much less memory (256MB or less?)
* [SPOI-1787] - Add license instructions to README
* [SPOI-1790] - Ensure update to license app on any resource change by StrAM
* [SPOI-1791] - Hard enforcement for free license (6GB), and eval license
* [SPOI-1793] - Hide sub-license and make license object behave as “what is license data right now?”
* [SPOI-1798] - Date format change in license file
* [SPOI-1799] - Change name "Sublicense" to "Section" or "LicenseSection"
* [SPOI-1800] - Webservice specs for Gateway for license info
* [SPOI-1825] - Update end user documentation
* [SPOI-1832] - Support CDH default log4j setup

### Sub-task
* [SPOI-1451] - Show critical path
* [SPOI-1721] - Augment the Partitionable interface to inform of all the partitions which actually were deployed
* [SPOI-1733] - Container heartbeat RPC failover


### New Feature
* [MLHR-5] - UI component for license information
* [MLHR-6] - Google Line Chart Widget
* [MLHR-7] - Gauge Widget
* [MLHR-8] - Top N Widget
* [MLHR-9] - Compile Widget from HTML Template
* [MLHR-10] - Make widgets resizable and renameable in ui-builder
* [MLHR-11] - Dashboard Component Grunt Tasks
* [MLHR-653] - Dynamically Connect Widgets to WebSocket Topics
* [MLHR-655] - Create serializing mechanism for instantiated widgets and dashboard(s)
* [MLHR-656] - Add/Compile Widgets from templateUrl
* [MLHR-664] - Support MQTT protocol
* [MLHR-668] - Set up widget configure dialog
* [MLHR-669] - Visual Data Demo App
* [MLHR-671] - Add allocatedMB column in main application list
* [MLHR-673] - Dashboard App - Notification Service
* [MLHR-674] - Explicit Saving/Loading of Dash configurations in ui builder
* [MLHR-687] - Dashboard App - Filter WebSocket Topics
* [MLHR-689] - Dashboard App - Widget Options Modal
* [MLHR-690] - Dashboard App - Widgets Schema
* [MLHR-691] - WebSocket Topics Debugger Widget
* [MLHR-692] - JSON Widget
* [MLHR-693] - Progressbar Widget
* [MLHR-695] - Pie Chart Widget
* [MLHR-696] - Dashboard App - Development/Production Scripts
* [MLHR-697] - Dashboard App - Node.js Configuration
* [MLHR-698] - Dashboard App - WebSocket/REST API Configuration

### Improvement
* [MLHR-686] - Deglobalize the visibly component

### Bug
* [MLHR-4] - Use new livechart module for OpChart Widget
* [MLHR-13] - Console status column display
* [MLHR-648] - Update Issues section in README files 
* [MLHR-650] - Changing metrics on logical dag fails
* [MLHR-654] - Some widgets' height changes when changing width
* [MLHR-667] - Add UI version to console
* [MLHR-670] - Memory leak in console
* [MLHR-677] - Widgets Data Models
* [MLHR-680] - Update license information dialog for new REST call info
* [MLHR-725] - WindowId Formatter
* [MLHR-739] - Stream Locality Toggle fails for DAG view

### Story
* [MLHR-1] - Reusable Dashboard Component with AngularJS
* [MLHR-2] - Dashboard Widgets
* [MLHR-3] - Dashboard App

### Task
* [MLHR-321] - Directory Scan operator
* [MLHR-452] - Create a De-duplication operator
* [MLHR-603] - Supports upload of dependency jars
* [MLHR-638] - Test streaming application for dynamic partition
* [MLHR-645] - More fields in drop down in logicalDAG widget
* [MLHR-646] - Document issue tracking location in README
* [MLHR-652] - Parallel Simple Linear Regression
* [MLHR-657] - Migrate memcache adapters to use the new database adapter interface
* [MLHR-662] - Migrate Redis adapters to use the new database adapter interface
* [MLHR-663] - Design new DB adapters interface
* [MLHR-666] - DB lookup for Cassandra



Version 0.9.2
------------------------------------------------------------------------------------------------------------------------

### Bug
* [SPOI-1327] - AtLeastOnceTest.testInlineOperatorsRecovery intermittent failure
* [SPOI-1342] - DTCli should check license and relay the information with each application launched
* [SPOI-1383] - Last window id and recovery window id do not update on 0.9
* [SPOI-1439] - Gateway should be secured
* [SPOI-1445] - Add version detection for Gateway
* [SPOI-1456] - Free Memory in container widget changes too rapidly
* [SPOI-1540] - Specification of license handlers and enforcers in the license file.
* [SPOI-1632] - jar upload fails
* [SPOI-1634] - Uptime at 1Billion events/s (Machine data)
* [SPOI-1635] - Update node1 with latest machine data demo
* [SPOI-1676] - Incremental Obfuscation of dt-flume directory
* [SPOI-1677] - Supports uploading of dependency jars
* [SPOI-1678] - When loading jars, make sure they are in their separate space so they don't conflict with gateway, cli and other jars
* [SPOI-1679] - When uploading jar and when dependencies are not met, allow the upload with a message about dependencies
* [SPOI-1680] - gateway throws errors when retrieving web service info from stram
* [SPOI-1687] - Support launching jar and showing logical plan from HDFS 
* [SPOI-1688] - Map Reduce Monitor Does Not Publish WebSocket Data
* [SPOI-1697] - Update demo configuration on node2
* [SPOI-1703] - Update auto provisioning with DataTorrent 0.9.1 and GCE GA
* [SPOI-1707] - License agent should handle license expiry
* [SPOI-1708] - Stram should store license expiry
* [SPOI-1709] - Show license object information in gateway
* [SPOI-1710] - License cutting utility
* [SPOI-1712] - Gateway to gracefully handle stram being a newer version than itself
* [SPOI-1714] - Dynamic partition stop working if you start from only 1  partition
* [SPOI-1727] - ApplicationInfoAutoPublisher unit test error
* [SPOI-1728] - StramEvent exception prevents package name obfuscation
* [SPOI-1739] - recordingStartTime of operator stats is showing -1 from time to time
* [SPOI-1743] - Tuple recording on port is not showing up in web services
* [SPOI-1744] - Recording says ended even if the recording is still going on


### Improvement
* [SPOI-1098] - event recorder logging improvements
* [SPOI-1370] - Make the partition logic available to the end-users
* [SPOI-1448] - DAG Visualization - Stream Types
* [SPOI-1603] - BufferServerStatsCollection - dont check against bufferserverpublisher and subscriber
* [SPOI-1613] - Update the User Interface guide to reflect latest version (0.9.1)

### New Feature
* [SPOI-165] - Parent jira for authentication
* [SPOI-170] - Stream should authenticate before allowing an operator to connect
* [SPOI-258] - Develop Flume Sink and corresponding DT input adapter
* [SPOI-327] - Parent jira for Security
* [SPOI-401] - Licensing alert mechanisms
* [SPOI-411] - Ability to modify (add, upgrade, downgrade) license while the app is running
* [SPOI-436] - Provide Web Service for obtaining license information (Usage limits, etc)
* [SPOI-729] - Include license data in DT phone home
* [SPOI-872] - Logical View of Running Application
* [SPOI-975] - Support DataLocal Functionality
* [SPOI-1406] - Add log file path and/or URL to each container info map
* [SPOI-1621] - Input operator - CDR parser using CSV 
* [SPOI-1699] - Add locality (and maybe id?) to physical streams in REST calls

### Task
* [SPOI-1689] - Map Reduce Monitor Web App
* [SPOI-739] - Hadoop 2.2 certification
* [SPOI-763] - Competition study
* [SPOI-1140] - Annotate dag visualization with stream throughout and other data
* [SPOI-1246] - Support versioning for Gateway to STRAM communications 
* [SPOI-1253] - Create DataTorrent Application which provides licensing server functionality
* [SPOI-1389] - ContainerList view should show the log file name (stderr, stdout) in the info widget
* [SPOI-1405] - Design macros for node0 and node1
* [SPOI-1609] - Competitive analysis - DT (Platform1 and Platform2)
* [SPOI-1611] - Benchmarking Ads Dimension on Morado cluster (at-least-once semantics) - Platform1
* [SPOI-1616] - Benchmarking Performance app with Platform1
* [SPOI-1670] - Ensure that Dedup operator is fault tolerant
* [SPOI-1673] - use public/private key encryption for dt phone home
* [SPOI-1675] - Map Reduce Jobs
* [SPOI-1686] - Launch separate process when loading classes from application jars
* [SPOI-1722] - Create a utility to create default license
* [SPOI-1724] - Create a command line utility to generate customer license
* [SPOI-1736] - CLI warning on License Violation
* [SPOI-1742] - Update end-user documentation


### Sub-task
* [SPOI-919] - Certify secure mode with Hadoop 2.2.0
* [SPOI-966] - Create a licensing agent application
* [SPOI-1413] - Flume sink part 
* [SPOI-1414] - DT Input Adapter for Flume
* [SPOI-1475] - Augment Kafka operator to dynamically adapt to load and broker/partition changes
* [SPOI-1538] - Develop Ads Dimension on Morado cluster (at-least-once semantics) Platform1
* [SPOI-1713] - Secure communication between gateway and stram
* [SPOI-1720] - Ensure that the Partionable interface and StatsListener interface callbacks are made from the same thread
* [SPOI-1723] - The default license generation should be integrated with build
* [SPOI-1731] - Sync execution layer deployment state after recovery

### GitHub - DataTorrent/Malhar
* [616] - fix #615 Update Web Apps Instructions
* [615] - Update Web Apps Instructions
* [614] - corrected typo
* [613] - Fixes #599. Upload and specify dependency jars
* [612] - fixes #597
* [611] - fixes #610
* [610] - Telecom tests failing
* [609] - Github 597
* [608] - #fix 607 Machine Data Demo Day Format
* [607] - Machine Data Demo Day Format
* [606] - fixes #457 added xml parse operator to parse and pick values from xml nodes and att...
* [605] - added the history for hadoop 1.x
* [603] - Map Reduce Monitor - Elapsed Time
* [602] - Map Reduce Monitor - Elapsed Time
* [601] - Map Reduce Monitor - Bootstrap JS, Server Errors Notification, Header Alignment
* [599] - Provide UI for uploading and specifying dependency jars
* [598] - Map Reduce Monitor - Server Errors Notification
* [597] - Map Reduce Monitor App - CPU/Memory History
* [595] - Map Reduce Monitor (History Charts, Animations, Readme, AngularJS Upgrade)
* [594] - Map Reduce Monitor - Production Files (dist)
* [593] - Map Reduce Monitor - AngularUI Bootstrap Progressbar issue with ngAnimate
* [592] - Map Reduce Monitor Update (Readme, App List, History Charts)
* [591] - Map Reduce Monitor - Map/Reduce History Charts
* [590] - Fixes #401, adds zoom to physical DAG
* [589] - Map Reduce Monitor - App List Columns
* [586] - Map Reduce Monitor - App Id AngularJS Filter
* [585] - Fixes #569, Cosmetic changes
* [584] - Map Reduce Monitor - Show Active Job First
* [581] - Map Reduce Monitor Update (Loading Indicator, Animations, Delayed Promise)
* [580] - Map Reduce Monitor - AngularJS Animations
* [579] - Map Reduce Monitor - Upgrade to AngularJS 1.2.6
* [578] - Map Reduce Monitor - App List Loading Indicator
* [577] - fixes #553, fixes #575
* [576] - Map Reduce Monitor - AngularJS Delayed $q Promise
* [575] - Map Reduce Monitor App - Send Job Stats immediately on Subscribe Request
* [573] - Map Reduce Monitor Update (App List Grid, Progress Bars, Job Removal)
* [572] - fixes #570
* [571] - Map Reduce Monitor - Remove Job on WebSocket Message
* [570] - clipPath issue when multiple charts on the same page
* [569] - Various cosmetic updates for console
* [568] - fixes #542, tooltip no longer obstructed by graph lines
* [567] - Bird's Eye View for Physical DAG view
* [566] - fixes #544, windowIds can now handle initial value of -1 or 0
* [565] - Map Reduce Monitor - Job Selection
* [564] - fixes #357, added logical operator page
* [563] - Map Reduce Monitor - App List ng-grid
* [561] - Map Reduce Monitor - App List Table Filter
* [560] - Fixed exception with KryoSerializableStreamCodec #559
* [558] - CDR simulator #524
* [557] - Github 525
* [556] - set the name of the io threads created by ning asynchttpclient
* [554] - Squashed commit of the following:
* [553] - Map Reduce Monitor App - Store Map/Reduce Progress History
* [551] - fixes #550
* [550] - Map Reduce Monitor App - App Should Broadcast Special Message on Unsubscription
* [549] - Map Reduce Monitor - Stop Updates after Job Unsubscribe
* [548] - Map Reduce Monitor - Found Job Notification
* [547] - Fix Github #545
* [544] - Console does not handle initial windowId
* [542] - Tooltip for line graphs show up behind graphs after turning series on and off
* [541] - fixes #535
* [539] - Map Reduce Monitor - Merge Progress Bars with Progress Table
* [538] - Map Reduce Monitor - Combine Map/Reduce Counters
* [536] - Map Reduce Monitor - App List Running Jobs Progress Bar
* [535] - Console breaks when switching to other page
* [534] - Fixes #510, Unsubscribe Logical Operators when not used by any widget
* [533] - Fixes #521, Refactored WindowId usage
* [532] - Map Reduce Monitor - Counters
* [530] - Map Reduce Monitor - App List Sort
* [526] - Map Reduce Monitor - Counters
* [525] - CDR processing DAG prototype
* [523] - Github 512
* [521] - Normalize all WindowId objects by overriding "set" method of appropriate models
* [519] - Map Reduce Monitor - Header Alignment on Resize
* [518] - Map Reduce Web App
* [517] - Map Reduce Monitor - License Headers
* [516] - Map Reduce Monitor - Map Reduce Jobs List
* [515] - Map Reduce Monitor - AngularJS Modules Definition
* [514] - Map Reduce Monitor - Readme (Deployment and Running Instructions)
* [513] - Map Reduce Monitor - Job Query Loading Indicator
* [512] - Support Normalization Operator
* [511] - Map Reduce Monitor - AngularJS Settings Provider
* [510] - Unsubscribe logicalOperators on InstancePage when not in use by widget
* [509] - Fixes #505. Also removes one more instance of free memory metric for containers
* [507] - Map Reduce Monitor - Single Config (Server and Client)
* [505] - Add processed and emitted metrics to container overview widget
* [504] - fixes #356, container log url now available in container info widget
* [503] - Map Reduce Monitor - Active Job Highlight
* [502] - Map Reduce Monitor - AngularJS Parent Scope Event Propagation
* [501] - Fixes #364, removed free memory from container metrics
* [500] - Map Reduce Monitor - Mock Server
* [499] - Adding support for R. Basic operations - min, max and std deviation support added. Also adding support to run R scripts.
* [498] - Rsupport pull
* [496] - Map Reduce Monitor - Progress Line Chart
* [495] - Map Reduce Monitor - Running MAPREDUCE Applications Discovery
* [494] - fixes #420, can now set explicit height for widgets
* [493] - fix #488 added delay before reconnection
* [492] - CPU/RAM Metrics for Map Reduce Jobs
* [491] - fix #488 added delay before reconnection
* [489] - Map Reduce Monitor - Job Controller
* [488] - WebSocketOutputOperator should wait a specified number of seconds before reconnection
* [487] - Using uniform naming convention for applications. Fixed incorrect application names. Fixes #486.
* [486] - Application names are not uniform
* [485] - CPU/RAM Metrics for Map Reduce Jobs (Map Reduce Monitor App)
* [484] - Map Reduce Monitor - AngularJS UI-Router Nested Views
* [483] - Enhance the AbstractSlidingWindow #480, Add a SortedSlidingWindow operator #423
* [482] - fixes #411. bundling on server.js, monkeypatching fs to avoid EMFILE
* [479] - fix #443 reconnection when the connection is dropped
* [478] - fix #443 Handles reconnection when the connection is dropped
* [477] - Improvements to LogicalDagWidget. Fixes #399, #473, #475, #476
* [476] - Logical DAG Widget: Limit scroll scale extent
* [475] - Logical DAG Widget: add ability to reset initial dag view
* [474] - Map Reduce Monitor - AngularJS UI-Router
* [473] - Logical DAG Widget: only zoom when alt/option is held down
* [472] - Map Reduce Monitor App - App Does not Publish Completed Maps
* [471] - Map Redice Monitor - Reduce Progress Grid
* [470] - Map Redice Monitor - Map Progress Grid
* [469] - Map Redice Monitor - AngularJS Percentage Filter
* [468] - Map Reduce Monitor - Monitored Jobs Grid
* [467] - Add a general CSV parser operator to parse string, byte[] input to Map #451
* [466] - Map Redice Monitor - AngularJS Util Service
* [465] - Map Reduce Monitor - Unsubscribe Action
* [464] - Map Reduce Monitor - Client-Side Settings
* [463] - Map Reduce Monitor - WebSocket Unsubscribe
* [461] - Map Reduce Monitor -  Multiple Jobs Monitoring
* [460] - Map Reduce Monitor - Progress Bar Animation
* [459] - Map Reduce Monitor - Upgrade to AngularJS 1.2.4
* [458] - added xml parser operator and its test, fixes #457
* [456] - Github 444
* [454] - Map Reduce Monitor - AngularUI Bootstrap
* [453] - Map Reduce Monitor - Production Build with Grunt
* [452] - Map Reduce Monitor - jshint
* [451] - CSV input operator (CDR processing)
* [450] - Map Reduce Monitor - Progress Bars 
* [449] - Map Reduce Monitor App - WebSocket Query
* [448] - Map Reduce Monitor - Error Notifications with pnotify 
* [444] - Map Redice Monitor App - Publish Map/Reduce Updates as Array
* [443] - Map Reduce Monitor App WebSocket Issue
* [442] - Map Reduce Monitor - Node.js Proxy for Hadoop ResourceManager
* [441] - Map Reduce Monitor - REST Service
* [439] - Map Reduce Monitor - Server Configuration
* [438] - Map Reduce Monitor - Settings
* [436] - Map Reduce Monitor - Job Progress Grid
* [435] - Map Reduce Monitor - WebSocket Service with AngularJS provider
* [434] - Map Reduce Monitor - Unit Tests
* [433] - Map Reduce Monitor - AngularJS Directives (widgets)
* [432] - Map Reduce Monitor - Page Layout with Bootstrap
* [431] - Map Reduce Monitor - Node.js Server
* [430] - Map Reduce Monitor - Yeoman Generated App
* [428] - Normalization operator (CDR processing)
* [427] - Filter operator (CDR Processing)
* [426] - Enrichment operator (CDR processing)
* [425] - Aggregator operator (CDR processing)
* [422] - Github 421
* [421] - Create RedisOperator taking String,String for performance
* [420] - Allow widgets to have adjustable height
* [419] - DAG Styling, DAG Firefox Issue
* [418] - Logical DAG - Firefox Bottom Margin Issue
* [417] - Logical DAG Styling
* [416] - Fix jquery build error
* [415] - Organized scripts and server
* [414] - fix #408, fix #413 Logical DAG - Show Stream Locality on Demand
* [413] - Logical DAG - Right Aligned Legned and Show Locality Link
* [412] - Improve Front Dev Environment
* [411] - Improved dev environment for front
* [410] - Map Reduce Monitor Web App
* [409] - fix #393 Front Node.js Proxy
* [408] - Logical DAG - Show Stream Locality on Demand
* [407] - fixes #373
* [401] - Physical DAG - Smart Zoom
* [399] - Physical DAG - Bird's-Eye View
* [393] - Front Node.js Proxy
* [375] - fixes #367, improves reload time during dev on front
* [374] - fixes #367, improves reload time during dev on front
* [372] - Logical DAG Legend Styling
* [371] - Logical DAG Legend
* [370] - Fix issue316 issue317 pull
* [369] - Logical DAG - Legend
* [368] - Squashed commit of the following:
* [367] - Precompile templates for better dev process
* [366] - Documenting demos pull
* [365] - Normalized all "processed" and "emitted" labels
* [364] - Remove free memory from container metrics in UI
* [362] - Dependency to dagre-d3 fork
* [361] - Logical DAG - Stream Locality
* [360] - Update physical operators collection to fetch from physical plan
* [359] - Add source and sinks to physical operator list 
* [358] - Normalize processed/s emitted/s labels across data tables and dag view
* [357] - Create Logical Operator Page
* [356] - ContainerList view should show the log file name (stderr, stdout) in the info widget
* [355] - fixes #349, recently-launched app does not request operator list
* [354] - Make partitionable kafka input operator adjust partitions ifself for kafka partition change(del/add)
* [353] - Upgrade kafka to 0.8 release
* [352] - fixes #322
* [351] - Non-partitioned operators
* [350] - Key/Value lookup Storage Manager changes
* [349] - Application launch error in console
* [348] - Fixes #339, switches cluster metrics to websocket topic
* [347] - fix #346 Physical DAG - Remove Container IDs
* [346] - Physical DAG - Remove Container IDs
* [345] - Added sensible default display for avg app age field in cluster metrics widget #341
* [344] - Added build cmd to travis script, fixes #343
* [343] - Build step for front not in travis script
* [342] - Fix for #328
* [341] - Cluster overview display items (initial launch)
* [339] - Cluster stats should come from WebSocket topic
* [337] - Add Write failed: Broken pipe
