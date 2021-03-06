# Amazon WorkDocs Java code examples

This README discusses how to run and test the Java code examples for Amazon WorkDocs.

## Running the Amazon WorkDocs Java files

**IMPORTANT**

The Java code examples perform AWS operations for the account and AWS Region for which you've specified credentials, and you may incur AWS service charges by running them. See the [AWS Pricing page](https://aws.amazon.com/pricing/) for details about the charges you can expect for a given service and operation.

Some of these examples perform *destructive* operations on AWS resources. **Be very careful** when running an operation that deletes or modifies AWS resources in your account. It's best to create separate test-only resources when experimenting with these examples.

To run the examples, you'll need the AWS SDK for Java libraries in your **CLASSPATH**.

	export CLASSPATH=target/sdk-examples-1.0.jar:/path/to/aws-java-sdk/<jar-file-name>.jar

Here **/path/to/aws-java-sdk/<jar-file-name>.jar** is the path to where you extracted or built the AWS SDK for Java JAR file.

For systems with bash support, once you set the **CLASSPATH**, you can run a particular example as follows.

	  java com.example.workdocs.ListUserDocs


## Testing the Amazon WorkDocs Java files

You can test the Java code examples for Amazon WorkDocs by running a test file named **WorkdocsServiceIntegrationTest**. This file uses JUnit 5 to run the JUnit tests and is located in the **src/test/java** folder. For more information, see [https://junit.org/junit5/](https://junit.org/junit5/).

You can execute the JUnit tests from a Java IDE, such as IntelliJ, or from the command line by using Maven. As each test is executed, you can view messages that inform you if the various tests succeed or fail. For example, the following message informs you that Test 3 passed.

	Test 3 passed

**WARNING**: _Running these JUnit tests manipulates real Amazon resources and may incur charges on your account._

 ### Properties file
Before running the Amazon WorkDocs JUnit tests, you must define values in the **config.properties** file located in the **resources** folder. This file contains values that are required to execute the JUnit tests.

Define the following values to successfully run the JUnit tests:

- **orgId** - Your organization ID value.   
- **userEmail** ??? The user email that you configured.
- **workdocsName** - The name of the document to download.
- **saveDocFullName** - The path where a document is saved after it's downloaded.
- **docName** - The name of the document after it's uploaded.
- **docPath** - The path of the document to upload.

### Command line
To execute the JUnit tests from the command line, you can use the following command.

		mvn test

You will see output from the JUnit tests, as shown here.

	[INFO] -------------------------------------------------------
	[INFO]  T E S T S
	[INFO] -------------------------------------------------------
	[INFO] Running WorkdocsServiceIntegrationTest
	Test 1 passed
	Test 2 passed
	...
	Done!
	[INFO] Results:
	[INFO]
	[INFO] Tests run: 5, Failures: 0, Errors: 0, Skipped: 0
	[INFO]
	INFO] --------------------------------------------
	[INFO] BUILD SUCCESS
	[INFO]--------------------------------------------
	[INFO] Total time:  12.003 s
	[INFO] Finished at: 2020-02-10T14:25:08-05:00
	[INFO] --------------------------------------------

### Unsuccessful tests

If you don't define the correct values in the properties file, your JUnit tests are not successful. You will see an error message such as the following. You need to double-check the values that you set in the properties file and run the tests again.

	[INFO]
	[INFO] --------------------------------------
	[INFO] BUILD FAILURE
	[INFO] --------------------------------------
	[INFO] Total time:  19.038 s
	[INFO] Finished at: 2020-02-10T14:41:51-05:00
	[INFO] ---------------------------------------
	[ERROR] Failed to execute goal org.apache.maven.plugins:maven-surefire-plugin:2.22.1:test (default-test) on project S3J2Project:  There are test failures.
	[ERROR];
