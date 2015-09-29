DataTorrent RTS Sandbox
================================================================================

Welcome to the DataTorrent Sandbox, an introduction to DataTorrent RTS, the industry’s only unified stream and batch processing platform.  For additional information about DataTorrent products, please visit https://www.datatorrent.com/

Sandbox Overview
--------------------------------------------------------------------------------

The DataTorrent Sandbox automatically launches Hadoop HDFS and YARN services on startup.  Depending on the host machine capabilities, these may take from several seconds to several minutes to start up.  Until Hadoop services are active and ready, it is normal to see error messages about availability of HDFS and YARN in the Issues section of the DataTorrent console.  Ensure there are no errors remaining in the console by allowing sufficient time for Hadoop services startup prior to launching DataTorrent applications.

**Note**: By default, this sandbox is designed to run with 6 GB of RAM.  Limited resources may cause delays during Hadoop services and DataTorrent applications startup.

When accessing DataTorrent <a href="http://localhost:9090/#/docs/" target="_blank">console</a> in the sandbox for the first time, you will be required to log in.  Use username **dtadmin** and password **dtadmin**.  Same credentials are also valid for sandbox system access.

![](images/sandbox/login.png)

Once authenticated, you can continue to [DataTorrent Docs](index.md) to explore demo applications, discover features of the RTS platform, or learn how to write your own DataTorrent applications.
