Google Cloud Client Library for Java
==========================

Java idiomatic client for [Google Cloud Platform][cloud-platform] services.

[![Build Status](https://travis-ci.org/GoogleCloudPlatform/google-cloud-java.svg?branch=master)](https://travis-ci.org/GoogleCloudPlatform/google-cloud-java)
[![Coverage Status](https://coveralls.io/repos/GoogleCloudPlatform/google-cloud-java/badge.svg?branch=master)](https://coveralls.io/r/GoogleCloudPlatform/google-cloud-java?branch=master)
[![Maven](https://img.shields.io/maven-central/v/com.google.cloud/google-cloud.svg)](http://search.maven.org/#search%7Cga%7C1%7Cg%3A%22com.google.cloud%22%20a%3A%22google-cloud%22)
[![Codacy Badge](https://api.codacy.com/project/badge/grade/9da006ad7c3a4fe1abd142e77c003917)](https://www.codacy.com/app/mziccard/google-cloud-java)
[![Dependency Status](https://www.versioneye.com/user/projects/58fe4c8d6ac171426c414772/badge.svg?style=flat)](https://www.versioneye.com/user/projects/58fe4c8d6ac171426c414772)

-  [Homepage](https://googlecloudplatform.github.io/google-cloud-java/)
-  [API Documentation](https://googlecloudplatform.github.io/google-cloud-java/apidocs)

This client supports the following Google Cloud Platform services at a [GA](#versioning) quality level:
-  [Stackdriver Logging](#stackdriver-logging-ga) (GA)
-  [Cloud Datastore](#google-cloud-datastore-ga) (GA)
-  [Cloud Storage](#google-cloud-storage-ga) (GA)

This client supports the following Google Cloud Platform services at a [Beta](#versioning) quality level:

-  [BigQuery](#google-cloud-bigquery-beta) (Beta)
-  [Cloud Pub/Sub](#google-cloud-pubsub-beta) (Beta)
-  [Cloud Spanner](#cloud-spanner-beta) (Beta)
-  [Cloud Translation](#google-translation-beta) (Beta)
-  [Cloud Natural Language](#google-cloud-language-beta) (Beta)
-  [Cloud Vision](#google-cloud-vision-beta) (Beta)

This client supports the following Google Cloud Platform services at an [Alpha](#versioning) quality level:

-  [Cloud Compute](#google-cloud-compute-alpha) (Alpha)
-  [Cloud DNS](#google-cloud-dns-alpha) (Alpha)
-  [Stackdriver Error Reporting](#stackdriver-error-reporting-alpha) (Alpha)
-  [Stackdriver Monitoring](#stackdriver-monitoring-alpha) (Alpha)
-  [Cloud Resource Manager](#google-cloud-resource-manager-alpha) (Alpha)
-  [Cloud Speech](#google-cloud-speech-alpha) (Alpha)
-  [Cloud Trace](#google-cloud-trace-alpha) (Alpha)
-  [Cloud Video Intelligence](#google-cloud-video-intelligence-alpha) (Alpha)

> Note: This client is a work-in-progress, and may occasionally
> make backwards-incompatible changes.

## Where did `gcloud-java` go?

`gcloud-java` lives on under a new name, `google-cloud`.
Your code will behave the same, simply change your dependency (see [Quickstart](./README.md#quickstart)).

Quickstart
----------

If you are using Maven, add this to your pom.xml file
```xml
<dependency>
  <groupId>com.google.cloud</groupId>
  <artifactId>google-cloud</artifactId>
  <version>0.20.1-alpha</version>
</dependency>
```
If you are using Gradle, add this to your dependencies
```Groovy
compile 'com.google.cloud:google-cloud:0.20.1-alpha'
```
If you are using SBT, add this to your dependencies
```Scala
libraryDependencies += "com.google.cloud" % "google-cloud" % "0.20.1-alpha"
```

For running on Google App Engine, see [more instructions here](./APPENGINE.md).

Example Applications
--------------------

- [`BigQueryExample`](./google-cloud-examples/src/main/java/com/google/cloud/examples/bigquery/BigQueryExample.java) - A simple command line interface providing some of Cloud BigQuery's functionality
  - Read more about using this application on the [`BigQueryExample` docs page](https://googlecloudplatform.github.io/google-cloud-java/apidocs/?com/google/cloud/examples/bigquery/BigQueryExample.html).
- [`ComputeExample`](./google-cloud-examples/src/main/java/com/google/cloud/examples/compute/ComputeExample.java) - A simple command line interface providing some of Cloud Compute's functionality
  - Read more about using this application on the [`google-cloud-examples` docs page](https://googlecloudplatform.github.io/google-cloud-java/apidocs/?com/google/cloud/examples/compute/ComputeExample.html).
- [`Bookshelf`](https://github.com/GoogleCloudPlatform/getting-started-java/tree/master/bookshelf) - An App Engine app that manages a virtual bookshelf.
  - This app uses `google-cloud` to interface with Cloud Datastore and Cloud Storage. It also uses Cloud SQL, another Google Cloud Platform service.
- [`DatastoreExample`](./google-cloud-examples/src/main/java/com/google/cloud/examples/datastore/DatastoreExample.java) - A simple command line interface for Cloud Datastore
  - Read more about using this application on the [`DatastoreExample` docs page](https://googlecloudplatform.github.io/google-cloud-java/apidocs/?com/google/cloud/examples/datastore/DatastoreExample.html).
- [`DnsExample`](./google-cloud-examples/src/main/java/com/google/cloud/examples/dns/DnsExample.java) - A simple command line interface for Cloud DNS
  - Read more about using this application on the [`DnsExample` docs page](https://googlecloudplatform.github.io/google-cloud-java/apidocs/?com/google/cloud/examples/dns/DnsExample.html).
- [`Flexible Environment/Datastore example`](https://github.com/GoogleCloudPlatform/java-docs-samples/tree/master/flexible/datastore) - A simple app that uses Cloud Datastore to list the last 10 IP addresses that visited your site.
  - Read about how to run the application [here](https://github.com/GoogleCloudPlatform/java-docs-samples/blob/master/managed_vms/README.md).
- [`Flexible Environment/Storage example`](https://github.com/GoogleCloudPlatform/java-docs-samples/tree/master/flexible/cloudstorage) - An app that uploads files to a public Cloud Storage bucket on the App Engine Flexible Environment runtime.
- [`GuestBook`](https://github.com/GoogleCloudPlatform/java-docs-samples/tree/master/appengine/guestbook-cloud-datastore) - An App Engine Standard guestbook that uses Cloud Datastore.
- [`LoggingExample`](./google-cloud-examples/src/main/java/com/google/cloud/examples/logging/LoggingExample.java) - A simple command line interface providing some of Stackdriver Logging's functionality
  - Read more about using this application on the [`LoggingExample` docs page](https://googlecloudplatform.github.io/google-cloud-java/apidocs/?com/google/cloud/examples/logging/LoggingExample.html).
- [`ResourceManagerExample`](./google-cloud-examples/src/main/java/com/google/cloud/examples/resourcemanager/ResourceManagerExample.java) - A simple command line interface providing some of Cloud Resource Manager's functionality
  - Read more about using this application on the [`ResourceManagerExample` docs page](https://googlecloudplatform.github.io/google-cloud-java/apidocs/?com/google/cloud/examples/resourcemanager/ResourceManagerExample.html).
- [`SparkDemo`](https://github.com/GoogleCloudPlatform/java-docs-samples/blob/master/flexible/sparkjava) - An example of using `google-cloud-datastore` from within the SparkJava and App Engine Flexible Environment frameworks.
  - Read about how it works on the example's [README page](https://github.com/GoogleCloudPlatform/java-docs-samples/tree/master/managed_vms/sparkjava#how-does-it-work).
- [`StorageExample`](./google-cloud-examples/src/main/java/com/google/cloud/examples/storage/StorageExample.java) - A simple command line interface providing some of Cloud Storage's functionality
  - Read more about using this application on the [`StorageExample` docs page](https://googlecloudplatform.github.io/google-cloud-java/apidocs/?com/google/cloud/examples/storage/StorageExample.html).
- [`TaskList`](https://github.com/GoogleCloudPlatform/java-docs-samples/blob/master/datastore/src/main/java/com/google/datastore/snippets/TaskList.java) - A command line application that uses Cloud Datastore to manage a to-do list.
  - Read about how to run the application on its [README page](https://github.com/GoogleCloudPlatform/java-docs-samples/tree/master/datastore).
- [`TranslateExample`](./google-cloud-examples/src/main/java/com/google/cloud/examples/translate/TranslateExample.java) - A simple command line interface providing some of Google Translation's functionality
  - Read more about using this application on the [`TranslateExample` docs page](https://googlecloudplatform.github.io/google-cloud-java/apidocs/?com/google/cloud/examples/translate/TranslateExample.html).

Specifying a Project ID
-----------------------

Most `google-cloud` libraries require a project ID.  There are multiple ways to specify this project ID.

1. When using `google-cloud` libraries from within Compute/App Engine, there's no need to specify a project ID.  It is automatically inferred from the production environment.
2. When using `google-cloud` elsewhere, you can do one of the following:
  * Supply the project ID when building the service options.  For example, to use Datastore from a project with ID "PROJECT_ID", you can write:

  ```java
  Datastore datastore = DatastoreOptions.newBuilder().setProjectId("PROJECT_ID").build().getService();
  ```
  * Specify the environment variable `GOOGLE_CLOUD_PROJECT` to be your desired project ID.
  * Set the project ID using the [Google Cloud SDK](https://cloud.google.com/sdk/?hl=en).  To use the SDK, [download the SDK](https://cloud.google.com/sdk/?hl=en) if you haven't already, and set the project ID from the command line.  For example:

  ```
  gcloud config set project PROJECT_ID
  ```

`google-cloud` determines the project ID from the following sources in the listed order, stopping once it finds a value:

1. The project ID supplied when building the service options
2. Project ID specified by the environment variable `GOOGLE_CLOUD_PROJECT`
3. The App Engine project ID
4. The project ID specified in the JSON credentials file pointed by the `GOOGLE_APPLICATION_CREDENTIALS` environment variable
5. The Google Cloud SDK project ID
6. The Compute Engine project ID

Authentication
--------------

`google-cloud-java` uses
[https://github.com/google/google-auth-library-java](https://github.com/google/google-auth-library-java)
to authenticate requests. `google-auth-library-java` supports a wide range of authentication types;
see the project's [README](https://github.com/google/google-auth-library-java/blob/master/README.md)
and [javadoc](http://google.github.io/google-auth-library-java/releases/0.6.0/apidocs/) for more
details.

To access Google Cloud services, you first need to ensure that the necessary Google Cloud APIs are
enabled for your project. To do this, follow the instructions on the
[authentication document](https://github.com/GoogleCloudPlatform/gcloud-common/blob/master/authentication/readme.md#authentication)
shared by all the Google Cloud language libraries.

Next, choose a method for authenticating API requests from within your project:

1. When using `google-cloud` libraries from within Compute/App Engine, no additional authentication
steps are necessary. For example:
```java
Storage storage = StorageOptions.getDefaultInstance().getService();
```
2. When using `google-cloud` libraries elsewhere, there are several options:
  * [Generate a JSON service account key](https://cloud.google.com/storage/docs/authentication?hl=en#service_accounts).
  After downloading that key, you must do one of the following:
    * Define the environment variable GOOGLE_APPLICATION_CREDENTIALS to be the location of the key.
    For example:
    ```bash
    export GOOGLE_APPLICATION_CREDENTIALS=/path/to/my/key.json
    ```
    * Supply the JSON credentials file when building the service options. For example, this Storage
    object has the necessary permissions to interact with your Google Cloud Storage data:
    ```java
    Storage storage = StorageOptions.newBuilder()
        .setCredentials(ServiceAccountCredentials.fromStream(new FileInputStream("/path/to/my/key.json")))
        .build()
        .getService();
    ```
  * If running locally for development/testing, you can use the
  [Google Cloud SDK](https://cloud.google.com/sdk/). Create Application Default Credentials with
  `gcloud auth application-default login`, and then `google-cloud` will automatically detect such
  credentials.
  * If you already have an OAuth2 access token, you can use it to authenticate (notice that in this
  case, the access token will not be automatically refreshed):
  ```java
  Storage storage = StorageOptions.newBuilder()
      .setCredentials(new GoogleCredentials(new AccessToken(accessToken, expirationTime)))
      .build()
      .getService();
  ```

If no credentials are provided, `google-cloud` will attempt to detect them from the environment
using `GoogleCredentials.getApplicationDefault()` which will search for Default Application
Credentials in the following locations (in order):

1. The credentials file pointed to by the `GOOGLE_APPLICATION_CREDENTIALS` environment variable
2. Credentials provided by the Google Cloud SDK `gcloud auth application-default login` command
3. Google App Engine built-in credentials
4. Google Cloud Shell built-in credentials
5. Google Compute Engine built-in credentials

Stackdriver Logging (GA)
----------------------
- [API Documentation][logging-api]
- [Official Documentation][stackdriver-logging-docs]

*Follow the [activation instructions][stackdriver-logging-activation] to use the Stackdriver Logging
API with your project.*

#### Preview

Here are two code snippets showing simple usage examples from within Compute Engine/App Engine
Flexible. Note that you must [supply credentials](#authentication) and a project ID if running this
snippet elsewhere.

The first snippet shows how to write and list log entries. Complete source code can be found on
[WriteAndListLogEntries.java](./google-cloud-examples/src/main/java/com/google/cloud/examples/logging/snippets/WriteAndListLogEntries.java).

```java
import com.google.cloud.MonitoredResource;
import com.google.cloud.Page;
import com.google.cloud.logging.LogEntry;
import com.google.cloud.logging.Logging;
import com.google.cloud.logging.Logging.EntryListOption;
import com.google.cloud.logging.LoggingOptions;
import com.google.cloud.logging.Payload.StringPayload;

import java.util.Collections;
import java.util.Iterator;

LoggingOptions options = LoggingOptions.getDefaultInstance();
try(Logging logging = options.getService()) {

  LogEntry firstEntry = LogEntry.newBuilder(StringPayload.of("message"))
      .setLogName("test-log")
      .setResource(MonitoredResource.newBuilder("global")
          .addLabel("project_id", options.getProjectId())
          .build())
      .build();
  logging.write(Collections.singleton(firstEntry));

  Page<LogEntry> entries = logging.listLogEntries(
      EntryListOption.filter("logName=projects/" + options.getProjectId() + "/logs/test-log"));
  Iterator<LogEntry> entryIterator = entries.iterateAll();
  while (entryIterator.hasNext()) {
    System.out.println(entryIterator.next());
  }
}
```

The second snippet shows how to use a `java.util.logging.Logger` to write log entries to Stackdriver
Logging. The snippet installs a Stackdriver Logging handler using
`LoggingHandler.addHandler(Logger, LoggingHandler)`. Notice that this could also be done through the
`logging.properties` file, adding the following line:
```
com.google.cloud.examples.logging.snippets.AddLoggingHandler.handlers=com.google.cloud.logging.LoggingHandler
```
The complete code can be found on
[AddLoggingHandler.java](./google-cloud-examples/src/main/java/com/google/cloud/examples/logging/snippets/AddLoggingHandler.java).

```java
import com.google.cloud.logging.LoggingHandler;

import java.util.logging.Logger;

Logger logger = Logger.getLogger(AddLoggingHandler.class.getName());
LoggingHandler.addHandler(logger, new LoggingHandler());
logger.warning("test warning");
```

Google Cloud Datastore (GA)
----------------------

- [API Documentation][datastore-api]
- [Official Documentation][cloud-datastore-docs]

*Follow the [activation instructions][cloud-datastore-activation] to use the Google Cloud Datastore API with your project.*

#### Preview

Here are two code snippets showing simple usage examples from within Compute/App Engine. Note that you must [supply credentials](#authentication) and a project ID if running this snippet elsewhere.

The first snippet shows how to create a Datastore entity. Complete source code can be found at
[CreateEntity.java](./google-cloud-examples/src/main/java/com/google/cloud/examples/datastore/snippets/CreateEntity.java).

```java
import com.google.cloud.datastore.Datastore;
import com.google.cloud.datastore.DatastoreOptions;
import com.google.cloud.datastore.DateTime;
import com.google.cloud.datastore.Entity;
import com.google.cloud.datastore.Key;
import com.google.cloud.datastore.KeyFactory;

Datastore datastore = DatastoreOptions.getDefaultInstance().getService();
KeyFactory keyFactory = datastore.newKeyFactory().setKind("keyKind");
Key key = keyFactory.newKey("keyName");
Entity entity = Entity.newBuilder(key)
    .set("name", "John Doe")
    .set("age", 30)
    .set("access_time", DateTime.now())
    .build();
datastore.put(entity);
```
The second snippet shows how to update a Datastore entity if it exists. Complete source code can be
found at
[UpdateEntity.java](./google-cloud-examples/src/main/java/com/google/cloud/examples/datastore/snippets/UpdateEntity.java).
```java
import com.google.cloud.datastore.Datastore;
import com.google.cloud.datastore.DatastoreOptions;
import com.google.cloud.datastore.DateTime;
import com.google.cloud.datastore.Entity;
import com.google.cloud.datastore.Key;
import com.google.cloud.datastore.KeyFactory;

Datastore datastore = DatastoreOptions.getDefaultInstance().getService();
KeyFactory keyFactory = datastore.newKeyFactory().setKind("keyKind");
Key key = keyFactory.newKey("keyName");
Entity entity = datastore.get(key);
if (entity != null) {
  System.out.println("Updating access_time for " + entity.getString("name"));
  entity = Entity.newBuilder(entity)
      .set("access_time", DateTime.now())
      .build();
  datastore.update(entity);
}
```

Google Cloud Storage (GA)
----------------------

- [API Documentation][storage-api]
- [Official Documentation][cloud-storage-docs]

*Follow the [activation instructions][cloud-storage-activation] to use the Google Cloud Storage API with your project.*

#### Preview

Here are two code snippets showing simple usage examples from within Compute/App Engine.  Note that you must [supply credentials](#authentication) and a project ID if running this snippet elsewhere.

The first snippet shows how to create a Storage blob. Complete source code can be found at
[CreateBlob.java](./google-cloud-examples/src/main/java/com/google/cloud/examples/storage/snippets/CreateBlob.java).

```java
import static java.nio.charset.StandardCharsets.UTF_8;

import com.google.cloud.storage.Blob;
import com.google.cloud.storage.BlobId;
import com.google.cloud.storage.BlobInfo;
import com.google.cloud.storage.Storage;
import com.google.cloud.storage.StorageOptions;

Storage storage = StorageOptions.getDefaultInstance().getService();
BlobId blobId = BlobId.of("bucket", "blob_name");
BlobInfo blobInfo = BlobInfo.newBuilder(blobId).setContentType("text/plain").build();
Blob blob = storage.create(blobInfo, "Hello, Cloud Storage!".getBytes(UTF_8));
```
The second snippet shows how to update a Storage blob if it exists. Complete source code can be
found at
[UpdateBlob.java](./google-cloud-examples/src/main/java/com/google/cloud/examples/storage/snippets/UpdateBlob.java).
```java
import static java.nio.charset.StandardCharsets.UTF_8;

import com.google.cloud.storage.Blob;
import com.google.cloud.storage.BlobId;
import com.google.cloud.storage.Storage;
import com.google.cloud.storage.StorageOptions;

import java.nio.ByteBuffer;
import java.nio.channels.WritableByteChannel;

Storage storage = StorageOptions.getDefaultInstance().getService();
BlobId blobId = BlobId.of("bucket", "blob_name");
Blob blob = storage.get(blobId);
if (blob != null) {
  byte[] prevContent = blob.getContent();
  System.out.println(new String(prevContent, UTF_8));
  WritableByteChannel channel = blob.writer();
  channel.write(ByteBuffer.wrap("Updated content".getBytes(UTF_8)));
  channel.close();
}
```

Google Cloud BigQuery (Beta)
----------------------

- [API Documentation][bigquery-api]
- [Official Documentation][cloud-bigquery-docs]

#### Preview

Here is a code snippet showing a simple usage example from within Compute/App Engine. Note that you
must [supply credentials](#authentication) and a project ID if running this snippet elsewhere.
Complete source code can be found at
[CreateTableAndLoadData.java](./google-cloud-examples/src/main/java/com/google/cloud/examples/bigquery/snippets/CreateTableAndLoadData.java).

```java
import com.google.cloud.bigquery.BigQuery;
import com.google.cloud.bigquery.BigQueryOptions;
import com.google.cloud.bigquery.Field;
import com.google.cloud.bigquery.FormatOptions;
import com.google.cloud.bigquery.Job;
import com.google.cloud.bigquery.Schema;
import com.google.cloud.bigquery.StandardTableDefinition;
import com.google.cloud.bigquery.Table;
import com.google.cloud.bigquery.TableId;
import com.google.cloud.bigquery.TableInfo;

BigQuery bigquery = BigQueryOptions.getDefaultInstance().getService();
TableId tableId = TableId.of("dataset", "table");
Table table = bigquery.getTable(tableId);
if (table == null) {
  System.out.println("Creating table " + tableId);
  Field integerField = Field.of("fieldName", Field.Type.integer());
  Schema schema = Schema.of(integerField);
  table = bigquery.create(TableInfo.of(tableId, StandardTableDefinition.of(schema)));
}
System.out.println("Loading data into table " + tableId);
Job loadJob = table.load(FormatOptions.csv(), "gs://bucket/path");
loadJob = loadJob.waitFor();
if (loadJob.getStatus().getError() != null) {
  System.out.println("Job completed with errors");
} else {
  System.out.println("Job succeeded");
}
```

Google Cloud Pub/Sub (Beta)
----------------------
- [API Documentation][pubsub-api]
- [Official Documentation][cloud-pubsub-docs]

#### Preview

Here is a code snippet showing a simple usage example from within Compute Engine/App Engine
Flexible. Note that you must [supply credentials](#authentication) and a project ID if running this
snippet elsewhere. Complete source code can be found at
[CreateTopicAndPublishMessages.java](./google-cloud-examples/src/main/java/com/google/cloud/examples/pubsub/snippets/CreateTopicAndPublishMessages.java).

```java
import com.google.api.gax.core.ApiFuture;
import com.google.cloud.pubsub.v1.Publisher;
import com.google.cloud.pubsub.v1.TopicAdminClient;
import com.google.protobuf.ByteString;
import com.google.pubsub.v1.PubsubMessage;
import com.google.pubsub.v1.TopicName;

TopicName topic = TopicName.create("test-project", "test-topic");
try (TopicAdminClient topicAdminClient = TopicAdminClient.create()) {
  topicAdminClient.createTopic(topic);
}

Publisher publisher = null;
try {
  publisher = Publisher.newBuilder(topic).build();
  ByteString data = ByteString.copyFromUtf8("my message");
  PubsubMessage pubsubMessage = PubsubMessage.newBuilder().setData(data).build();
  ApiFuture<String> messageId = publisher.publish(pubsubMessage);
  System.out.println("published with message ID: " + messageId.get());
} finally {
  if (publisher != null) {
    publisher.shutdown();
  }
}
```

Cloud Spanner (Beta)
--------------------

- [API Documentation][cloud-spanner-api]
- [Official Documentation][cloud-spanner-docs]

#### Preview

Here is a code snippet showing a simple usage example from within Compute/App Engine Flex. Note that you
must [supply credentials](#authentication) and a project ID if running this snippet elsewhere.

```java
import com.google.cloud.spanner.DatabaseClient;
import com.google.cloud.spanner.DatabaseId;
import com.google.cloud.spanner.ResultSet;
import com.google.cloud.spanner.Spanner;
import com.google.cloud.spanner.SpannerOptions;
import com.google.cloud.spanner.Statement;

// Instantiates a client
SpannerOptions options = SpannerOptions.newBuilder().build();
Spanner spanner = options.getService();
String instance = "my-instance";
String database = "my-database";
try {
    // Creates a database client
    DatabaseClient dbClient = spanner.getDatabaseClient(
      DatabaseId.of(options.getProjectId(), instance, database));
    // Queries the database
    ResultSet resultSet = dbClient.singleUse().executeQuery(Statement.of("SELECT 1"));
    // Prints the results
    while (resultSet.next()) {
      System.out.printf("%d\n", resultSet.getLong(0));
    }
} finally {
    // Closes the client which will free up the resources used
    spanner.closeAsync().get();
}
```

Google Cloud Language (Beta)
----------------------
- [API Documentation][language-api]
- [Official Documentation][cloud-language-docs]

### Preview

Here is a code snippet showing a simple usage example of LanguageServiceClient. The example assumes that either default application
credentials or a valid API key are available. (See [Authentication section](#authentication) for more information)
```java
 try (LanguageServiceClient languageServiceClient = LanguageServiceClient.create()) {
   Document document = Document.newBuilder().build();
   AnalyzeSentimentResponse response = languageServiceClient.analyzeSentiment(document);
 }
```

Google Cloud Vision (Beta)
----------------

- [API Documentation][vision-api]
- [Official Documentation][cloud-vision-docs]

### Preview

Here is a code snippet showing a simple usage example of ImageAnnotatorClient.
The example assumes that either default application credentials or a valid API key
are available. (See [Authentication section](#authentication) for more information)
```java
 try (ImageAnnotatorClient imageAnnotatorClient = ImageAnnotatorClient.create()) {
   List<AnnotateImageRequest> requests = new ArrayList<>();
   BatchAnnotateImagesResponse response = imageAnnotatorClient.batchAnnotateImages(requests);
 }
```

Google Cloud Compute (Alpha)
----------------------

- [API Documentation][compute-api]
- [Official Documentation][cloud-compute-docs]

#### Preview

Here are two code snippets showing simple usage examples from within Compute/App Engine. Note that
you must [supply credentials](#authentication) and a project ID if running this snippet elsewhere.

The first snippet shows how to create a snapshot from an existing disk. Complete source code can be
found at
[CreateSnapshot.java](./google-cloud-examples/src/main/java/com/google/cloud/examples/compute/snippets/CreateSnapshot.java).

```java
import com.google.cloud.compute.Compute;
import com.google.cloud.compute.ComputeOptions;
import com.google.cloud.compute.Disk;
import com.google.cloud.compute.DiskId;
import com.google.cloud.compute.Snapshot;

Compute compute = ComputeOptions.getDefaultInstance().getService();
DiskId diskId = DiskId.of("us-central1-a", "disk-name");
Disk disk = compute.getDisk(diskId, Compute.DiskOption.fields());
if (disk != null) {
  String snapshotName = "disk-name-snapshot";
  Operation operation = disk.createSnapshot(snapshotName);
  operation = operation.waitFor();
  if (operation.getErrors() == null) {
    // use snapshot
    Snapshot snapshot = compute.getSnapshot(snapshotName);
  }
}
```
The second snippet shows how to create a virtual machine instance. Complete source code can be found
at
[CreateInstance.java](./google-cloud-examples/src/main/java/com/google/cloud/examples/compute/snippets/CreateInstance.java).
```java
import com.google.cloud.compute.AttachedDisk;
import com.google.cloud.compute.Compute;
import com.google.cloud.compute.ComputeOptions;
import com.google.cloud.compute.ImageId;
import com.google.cloud.compute.Instance;
import com.google.cloud.compute.InstanceId;
import com.google.cloud.compute.InstanceInfo;
import com.google.cloud.compute.MachineTypeId;
import com.google.cloud.compute.NetworkId;

Compute compute = ComputeOptions.getDefaultInstance().getService();
ImageId imageId = ImageId.of("debian-cloud", "debian-8-jessie-v20160329");
NetworkId networkId = NetworkId.of("default");
AttachedDisk attachedDisk = AttachedDisk.of(AttachedDisk.CreateDiskConfiguration.of(imageId));
NetworkInterface networkInterface = NetworkInterface.of(networkId);
InstanceId instanceId = InstanceId.of("us-central1-a", "instance-name");
MachineTypeId machineTypeId = MachineTypeId.of("us-central1-a", "n1-standard-1");
Operation operation =
    compute.create(InstanceInfo.of(instanceId, machineTypeId, attachedDisk, networkInterface));
operation = operation.waitFor();
if (operation.getErrors() == null) {
  // use instance
  Instance instance = compute.getInstance(instanceId);
}
```

Google Cloud DNS (Alpha)
----------------------
- [API Documentation][dns-api]
- [Official Documentation][cloud-dns-docs]

*Follow the [activation instructions][cloud-dns-activation] to use the Google Cloud DNS API with your project.*

#### Preview

Here are two code snippets showing simple usage examples from within Compute/App Engine. Note that you must [supply credentials](#authentication) and a project ID if running this snippet elsewhere.

The first snippet shows how to create a zone resource. Complete source code can be found on
[CreateZone.java](./google-cloud-examples/src/main/java/com/google/cloud/examples/dns/snippets/CreateZone.java).

```java
import com.google.cloud.dns.Dns;
import com.google.cloud.dns.DnsOptions;
import com.google.cloud.dns.Zone;
import com.google.cloud.dns.ZoneInfo;

Dns dns = DnsOptions.getDefaultInstance().getService();
String zoneName = "my-unique-zone";
String domainName = "someexampledomain.com.";
String description = "This is a google-cloud-dns sample zone.";
ZoneInfo zoneInfo = ZoneInfo.of(zoneName, domainName, description);
Zone zone = dns.create(zoneInfo);
```

The second snippet shows how to create records inside a zone. The complete code can be found on [CreateOrUpdateRecordSets.java](./google-cloud-examples/src/main/java/com/google/cloud/examples/dns/snippets/CreateOrUpdateRecordSets.java).

```java
import com.google.cloud.dns.ChangeRequestInfo;
import com.google.cloud.dns.Dns;
import com.google.cloud.dns.DnsOptions;
import com.google.cloud.dns.RecordSet;
import com.google.cloud.dns.Zone;

import java.util.Iterator;
import java.util.concurrent.TimeUnit;

Dns dns = DnsOptions.getDefaultInstance().getService();
String zoneName = "my-unique-zone";
Zone zone = dns.getZone(zoneName);
String ip = "12.13.14.15";
RecordSet toCreate = RecordSet.newBuilder("www.someexampledomain.com.", RecordSet.Type.A)
    .setTtl(24, TimeUnit.HOURS)
    .addRecord(ip)
    .build();
ChangeRequestInfo.Builder changeBuilder = ChangeRequestInfo.newBuilder().add(toCreate);

// Verify that the record does not exist yet.
// If it does exist, we will overwrite it with our prepared record.
Iterator<RecordSet> recordSetIterator = zone.listRecordSets().iterateAll();
while (recordSetIterator.hasNext()) {
  RecordSet current = recordSetIterator.next();
  if (toCreate.getName().equals(current.getName()) &&
      toCreate.getType().equals(current.getType())) {
    changeBuilder.delete(current);
  }
}

ChangeRequestInfo changeRequest = changeBuilder.build();
zone.applyChangeRequest(changeRequest);
```

Stackdriver Error Reporting (Alpha)
----------------------
- [API Documentation][errorreporting-api]
- [Official Documentation][cloud-errorreporting-docs]

### Preview

Here is a code snippet showing a simple usage example of ErrorGroupServiceClient.
Note that you must [supply credentials](#authentication) and a project ID if running this snippet elsewhere.
```java
 try (ErrorGroupServiceClient errorGroupServiceClient = ErrorGroupServiceClient.create()) {
   GroupName groupName = GroupName.create("[PROJECT]", "[GROUP]");
   ErrorGroup response = errorGroupServiceClient.getGroup(groupName);
 }
```

Stackdriver Monitoring (Alpha)
----------------------
- [API Documentation][monitoring-api]
- [Official Documentation][cloud-monitoring-docs]

### Preview

Here is a code snippet showing a simple usage example of MetricServiceClient.
Note that you must [supply credentials](#authentication) and a project ID if running this snippet elsewhere.
```java
 try (MetricServiceClient metricServiceClient = MetricServiceClient.create()) {
   MonitoredResourceDescriptorName name =
       MonitoredResourceDescriptorName.create("[PROJECT]", "[MONITORED_RESOURCE_DESCRIPTOR]");
   MonitoredResourceDescriptor response = metricServiceClient.getMonitoredResourceDescriptor(name);
 }
```

Google Cloud Resource Manager (Alpha)
----------------------

- [API Documentation][resourcemanager-api]
- [Official Documentation][cloud-resourcemanager-docs]

#### Preview

Here is a code snippet showing a simple usage example. Note that you must supply Google SDK credentials for this service, not other forms of authentication listed in the [Authentication section](#authentication).
Complete source code can be found at
[UpdateAndListProjects.java](./google-cloud-examples/src/main/java/com/google/cloud/examples/resourcemanager/snippets/UpdateAndListProjects.java).
```java
import com.google.cloud.resourcemanager.Project;
import com.google.cloud.resourcemanager.ResourceManager;
import com.google.cloud.resourcemanager.ResourceManagerOptions;

import java.util.Iterator;

ResourceManager resourceManager = ResourceManagerOptions.getDefaultInstance().getService();
Project project = resourceManager.get("some-project-id"); // Use an existing project's ID
if (project != null) {
  Project newProject = project.toBuilder()
      .addLabel("launch-status", "in-development")
      .build()
      .replace();
  System.out.println("Updated the labels of project " + newProject.getProjectId()
      + " to be " + newProject.getLabels());
}
Iterator<Project> projectIterator = resourceManager.list().iterateAll();
System.out.println("Projects I can view:");
while (projectIterator.hasNext()) {
  System.out.println(projectIterator.next().getProjectId());
}
```

Google Translation (Beta)
----------------

- [API Documentation][translate-api]
- [Official Documentation][translate-docs]

#### Preview

Here's a snippet showing a simple usage example. The example shows how to detect the language of
some text and how to translate some text. The example assumes that either default application
credentials or a valid API key are available. An API key stored in the `GOOGLE_API_KEY` environment
variable will be automatically detected. Complete source code can be found at
[DetectLanguageAndTranslate.java](./google-cloud-examples/src/main/java/com/google/cloud/examples/translate/snippets/DetectLanguageAndTranslate.java).

```java
import com.google.cloud.translate.Detection;
import com.google.cloud.translate.Translate;
import com.google.cloud.translate.Translate.TranslateOption;
import com.google.cloud.translate.TranslateOptions;
import com.google.cloud.translate.Translation;

Translate translate = TranslateOptions.getDefaultInstance().getService();

Detection detection = translate.detect("Hola");
String detectedLanguage = detection.getLanguage();

Translation translation = translate.translate(
    "World",
    TranslateOption.sourceLanguage("en"),
    TranslateOption.targetLanguage(detectedLanguage));

System.out.printf("Hola %s%n", translation.getTranslatedText());
```

Google Cloud Speech (Alpha)
----------------

- [API Documentation][speech-api]
- [Official Documentation][cloud-speech-docs]

### Preview

Here is a code snippet showing a simple usage example of SpeechClient. The example assumes that either default application
credentials or a valid API key are available. (See [Authentication section](#authentication) for more information)
Note that you must provide a uri to a FLAC audio file to run this.

```java
 try (SpeechClient speechClient = SpeechClient.create()) {
   RecognitionConfig.AudioEncoding encoding = RecognitionConfig.AudioEncoding.FLAC;
   int sampleRateHertz = 44100;
   String languageCode = "en-US";
   RecognitionConfig config = RecognitionConfig.newBuilder()
     .setEncoding(encoding)
     .setSampleRateHertz(sampleRateHertz)
     .setLanguageCode(languageCode)
     .build();
   String uri = "gs://bucket_name/file_name.flac";
   RecognitionAudio audio = RecognitionAudio.newBuilder()
     .setUri(uri)
     .build();
   RecognizeResponse response = speechClient.recognize(config, audio);
 }
```

Google Cloud Trace (Alpha)
----------------

- [API Documentation][trace-api]
- [Official Documentation][cloud-trace-docs]

### Preview

Here is a code snippet showing a simple usage example of TraceServiceClient. The example assumes that either default application
credentials or a valid API key are available.
Note that you must [supply credentials](#authentication) and a project ID if running this snippet elsewhere.
```java
 try (TraceServiceClient traceServiceClient = TraceServiceClient.create()) {
   String projectId = "";
   Traces traces = Traces.newBuilder().build();
   traceServiceClient.patchTraces(projectId, traces);
 }
```

Google Cloud Video Intelligence (Alpha)
----------------

- [Official Documentation][cloud-video-intelligence-docs]

### Preview

Here is a code snippet showing a simple usage example of TraceServiceClient. The example assumes that either default application
credentials or a valid API key are available.
Note that you must [supply credentials](#authentication) and a project ID if running this snippet elsewhere.
```java
try (VideoIntelligenceServiceClient videoIntelligenceServiceClient =
    VideoIntelligenceServiceClient.create()) {
  String inputUri = "";
   List<Feature> features = new ArrayList<>();
   VideoContext videoContext = VideoContext.newBuilder().build();
   String outputUri = "";
   String locationId = "";
   AnnotateVideoResponse response =
       videoIntelligenceServiceClient.annotateVideoAsync(
           inputUri, features, videoContext, outputUri, locationId).get();
 }
```

Troubleshooting
---------------

To get help, follow the instructions in the [shared Troubleshooting document](https://github.com/GoogleCloudPlatform/gcloud-common/blob/master/troubleshooting/readme.md#troubleshooting).

Using a proxy
-----
Clients in this repository use either HTTP or gRPC for the transport layer.
The README of each client documents the transport layer the client uses.

For HTTP clients, a proxy can be configured by using `http.proxyHost` and
related system properties as documented by
[Java Networking and Proxies](https://docs.oracle.com/javase/8/docs/technotes/guides/net/proxies.html).

For gRPC clients, a proxy can be configured by using the
`GRPC_PROXY_EXP` environment variable as documented by
the gRPC [release notes](https://github.com/grpc/grpc-java/releases/tag/v1.0.3).
Please note that gRPC proxy support is currently experimental.

Java Versions
-------------

Java 7 or above is required for using this client.

Supported Platforms
-------------------

This client is supported on Mac OS X, Windows and Linux (excluding Android and Alpine).
Google Cloud Platform environments currently supported include GCE, GKE and GAE Flex.
GAE Standard is not currently supported.

Spring Boot users : Native Tomcat is not currently supported. Please use [embedded Jetty](https://docs.spring.io/spring-boot/docs/current/reference/html/howto-embedded-servlet-containers.html#howto-use-jetty-instead-of-tomcat)
to get your application working with this client.

Testing
-------

This library provides tools to help write tests for code that uses google-cloud services.

See [TESTING] to read more about using our testing helpers.

Versioning
----------

This library follows [Semantic Versioning](http://semver.org/), but with some
additional qualifications:

1. Components marked with `@BetaApi` are considered to be "0.x" features inside
   a "1.x" library. This means they can change between minor and patch releases
   in incompatible ways. These features should not be used by any library "B"
   that itself has consumers, unless the components of library B that use
   `@BetaApi` features are also marked with `@BetaApi`. Features marked as
   `@BetaApi` are on a path to eventually become "1.x" features with the marker
   removed.

   **Special exception for google-cloud-java**: google-cloud-java is
   allowed to depend on `@BetaApi` features in gax-java without declaring the consuming
   code `@BetaApi`, because gax-java and google-cloud-java move in step
   with each other. For this reason, gax-java should not be used
   independently of google-cloud-java.

1. Components marked with `@InternalApi` are technically public, but are only
   public for technical reasons, because of the limitations of Java's access
   modifiers. For the purposes of semver, they should be considered private.

Please note it is currently under active development. Any release versioned 0.x.y is
subject to backwards incompatible changes at any time.

**GA**: Libraries defined at a GA quality level are expected to be stable and all updates in the
libraries are guaranteed to be backwards-compatible. Any backwards-incompatible changes will lead
to the major version increment (1.x.y -> 2.0.0).

**Beta**: Libraries defined at a Beta quality level are expected to be mostly stable and
we're working towards their release candidate. We will address issues and requests with
a higher priority.

**Alpha**: Libraries defined at an Alpha quality level are still a work-in-progress and
are more likely to get backwards-incompatible updates.

Contributing
------------

Contributions to this library are always welcome and highly encouraged.

See `google-cloud`'s [CONTRIBUTING] documentation and the [shared documentation](https://github.com/GoogleCloudPlatform/gcloud-common/blob/master/contributing/readme.md#how-to-contribute-to-gcloud) for more information on how to get started.

Please note that this project is released with a Contributor Code of Conduct. By participating in this project you agree to abide by its terms. See [Code of Conduct][code-of-conduct] for more information.

License
-------

Apache 2.0 - See [LICENSE] for more information.


[CONTRIBUTING]:https://github.com/GoogleCloudPlatform/google-cloud-java/blob/master/CONTRIBUTING.md
[code-of-conduct]:https://github.com/GoogleCloudPlatform/google-cloud-java/blob/master/CODE_OF_CONDUCT.md#contributor-code-of-conduct
[LICENSE]: https://github.com/GoogleCloudPlatform/google-cloud-java/blob/master/LICENSE
[TESTING]: https://github.com/GoogleCloudPlatform/google-cloud-java/blob/master/TESTING.md
[cloud-platform]: https://cloud.google.com/
[cloud-datastore]: https://cloud.google.com/datastore/docs
[cloud-datastore-docs]: https://cloud.google.com/datastore/docs
[cloud-datastore-activation]: https://cloud.google.com/datastore/docs/activate
[datastore-api]: https://googlecloudplatform.github.io/google-cloud-java/apidocs/index.html?com/google/cloud/datastore/package-summary.html

[dns-api]: https://googlecloudplatform.github.io/google-cloud-java/apidocs/index.html?com/google/cloud/dns/package-summary.html
[cloud-dns-docs]: https://cloud.google.com/dns/docs
[cloud-dns-activation]: https://console.cloud.google.com/start/api?id=dns

[errorreporting-api]: https://googlecloudplatform.github.io/google-cloud-java/apidocs/index.html?com/google/cloud/errorreporting/spi/v1beta1/package-summary.html
[cloud-errorreporting-docs]: https://cloud.google.com/error-reporting/docs

[language-api]: https://googlecloudplatform.github.io/google-cloud-java/apidocs/index.html?com/google/cloud/language/spi/v1/package-summary.html
[cloud-language-docs]: https://cloud.google.com/language/docs

[monitoring-api]: https://googlecloudplatform.github.io/google-cloud-java/apidocs/index.html?com/google/cloud/monitoring/spi/v3/package-summary.html
[cloud-monitoring-docs]: https://cloud.google.com/monitoring/docs

[speech-api]: http://googlecloudplatform.github.io/google-cloud-java/0.15.0/apidocs/?com/google/cloud/speech/spi/v1/package-summary.html
[cloud-speech-docs]: https://cloud.google.com/speech/docs

[trace-api]: http://googlecloudplatform.github.io/google-cloud-java/0.15.0/apidocs/?com/google/cloud/trace/spi/v1/package-summary.html
[cloud-trace-docs]: https://cloud.google.com/trace/docs

[vision-api]: http://googlecloudplatform.github.io/google-cloud-java/0.15.0/apidocs/?com/google/cloud/vision/spi/v1/package-summary.html
[cloud-vision-docs]: https://cloud.google.com/vision/docs

[cloud-video-intelligence-docs]: https://cloud.google.com/video-intelligence/docs

[logging-api]: https://googlecloudplatform.github.io/google-cloud-java/apidocs/index.html?com/google/cloud/logging/package-summary.html
[stackdriver-logging-docs]: https://cloud.google.com/logging/docs
[stackdriver-logging-activation]: https://console.cloud.google.com/start/api?id=logging

[pubsub-api]: https://googlecloudplatform.github.io/google-cloud-java/apidocs/index.html?com/google/cloud/pubsub/v1/package-summary.html
[cloud-pubsub]: https://cloud.google.com/pubsub/
[cloud-pubsub-docs]: https://cloud.google.com/pubsub/docs

[cloud-storage]: https://cloud.google.com/storage/
[cloud-storage-docs]: https://cloud.google.com/storage/docs/overview
[cloud-storage-create-bucket]: https://cloud.google.com/storage/docs/cloud-console#_creatingbuckets
[cloud-storage-activation]: https://cloud.google.com/storage/docs/signup
[storage-api]: https://googlecloudplatform.github.io/google-cloud-java/apidocs/index.html?com/google/cloud/storage/package-summary.html

[resourcemanager-api]:https://googlecloudplatform.github.io/google-cloud-java/apidocs/index.html?com/google/cloud/resourcemanager/package-summary.html
[cloud-resourcemanager-docs]:https://cloud.google.com/resource-manager/

[cloud-bigquery]: https://cloud.google.com/bigquery/
[cloud-bigquery-docs]: https://cloud.google.com/bigquery/docs/overview
[bigquery-api]: https://googlecloudplatform.github.io/google-cloud-java/apidocs/index.html?com/google/cloud/bigquery/package-summary.html

[cloud-compute]: https://cloud.google.com/compute/
[cloud-compute-docs]: https://cloud.google.com/compute/docs/overview
[compute-api]: https://googlecloudplatform.github.io/google-cloud-java/apidocs/index.html?com/google/cloud/compute/package-summary.html

[translate-docs]: https://cloud.google.com/translate/docs/
[translate-api]: https://googlecloudplatform.github.io/google-cloud-java/apidocs/index.html?com/google/cloud/translate/package-summary.html

[cloud-spanner]: https://cloud.google.com/spanner/
[cloud-spanner-docs]: https://cloud.google.com/spanner/docs/
[cloud-spanner-api]: https://googlecloudplatform.github.io/google-cloud-java/apidocs/index.html?com/google/cloud/spanner/package-summary.html
