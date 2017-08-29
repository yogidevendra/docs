# HDFS to S3 Sync Application

## Summary

This application demonstrates continuous big data sync from a source HDFS to destination S3. It read files from source HDFS and upload it into Amazon S3 using multipart upload feature.

## Quick links

-  <a
    href="../0.10.0/common/import-launch"  class="docs" id="docs" ga-track="docs"
    target="_blank">How to import and launch an app-template</a>

-  <a
    href="../0.10.0/common/customize"  class="docs" id="docs" ga-track="docs"
    target="_blank">How to customize an app-template</a>

-  <a
    href="https://github.com/DataTorrent/moodI/tree/master/app-templates/hdfs-to-s3-sync"  class="docs" id="docs" ga-track="docs"
    target="_blank">README for the application</a>
- <a
   href="https://github.com/DataTorrent/moodI/tree/master/app-templates/hdfs-to-s3-sync"  class="github" id="github" ga-track="github" target="_blank">Source code</a>

- Please send feedback or feature requests to :
    <a href="mailto:feedback@datatorrent.com"  class="feedback" id="feedback" ga-track="feedback">feedback@datatorrent.com</a>

- Join our user discussion group at :
    <a href="mailto:dt-users@googlegroups.com"  class="maillist" id="maillist" ga-track="maillist">dt-users@googlegroups.com</a>

## Required Properties
End user must specify the values for these properties.

|Property|Type|Example|Notes|
|---|---|-----|--|
|Aws Credentials Access Key Id|String|ACCESS_XXX_KEY_XX_ID| AWS credentials access key id for S3|
|Aws Credentials Secret Access Key|String|8your+own0+AWS0 secret1230+8key8goes0here| AWS Secret access key for accessing S3 output.|
|Input Directory Or File Path On HDFS|String|<ul><li>/user/appuser/input /directory1</li><li>/user/appuser /input/file2.log</li><li>hdfs://node1.corp1 .com/user/user1 /input</li></ul>|HDFS path for input file or directory
|Output Directory Path On S3Storage|String|hdfs_to_s3| Output directory for AWS S3|
|S3Storage Bucket Name|String|com.example.app.s3| Bucket name for AWS S3 output|

## Advanced Properties (optional)
|Property|Default|Type|Notes|
|--------|-------|----|-----|
|Maximum Readers For Dynamic Partitioning| 16| int| Maximum no of partitions for Block Reader operator. |
|Minimum Readers For Dynamic Partitioning| 2| int| Minimum no of partitions for Block Reader operator. |
|Number Of Blocks Per Window| 1|int|File splitter will emit these many blocks per window for downstream operators. |
