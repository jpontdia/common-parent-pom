# common-parent-pom
![Powered by](https://img.shields.io/badge/Powered%20by-Mulesoft-535597.svg)
  ![Build](https://github.com/jpontdia/common-parent-pom/actions/workflows/build.yml/badge.svg)
  ![Build job](https://gist.githubusercontent.com/jpontdia/2f22ca2ddf1ba473d6e2cff61cc2fba9/raw/common-parent-pom-wf.svg)
<br>

Parent POM for Mulesoft applications

  > This project follows the standards defined in the Development Process Document in Anypoint Exchange. The details to compile and package the asset are in the Build Environment section. 

## Table of contents
1. [Description](#description)
1. [Using the parent POM](#usinge-the-parent-pom)
1. [Runtime upgrade](#runtime-upgrade)
1. [List of plugins and dependencies](#list-of-plugins-and-dependencies)
1. [Installation in your organization](#Installation)
1. [Recommended content](#recommended-content)

<br>  

## Description

In Maven, a parent POM is a concept that allows you to define a common configuration and set of dependencies for multiple related projects within an organization or a software development team. It promotes code reuse and consistency across projects.

The parent POM acts as a blueprint or a template for child projects. It defines common configuration elements such as project version, organization details, build settings, and repositories. It also includes dependency management sections where you can define the shared dependencies required by all child projects. This allows you to centrally manage the versions and configurations of shared libraries and frameworks.

When you create a new Maven project, you can specify a parent POM from which the new project inherits its configuration. The child project can then override or extend the configuration inherited from the parent POM as needed. By inheriting from a parent POM, the child projects automatically adopt the common settings defined in the parent, reducing duplication and making it easier to maintain consistency across the project ecosystem.

In addition to configuration inheritance, the parent POM can also define common build plugins, profiles, and other build-related configurations that are shared among multiple projects.

To summarize, a Maven parent POM provides a way to define and share common configuration, dependencies, and build settings across multiple projects, enabling consistency, code reuse, and centralized management of project-related settings.

<br>  

## Using the parent POM
To use the parent POM in any of the child projects, specify the `parent`
section in the child `pom.xml` as follows:

```xml
	<parent>
		<groupId>078efef1-d139-48ed-92f5-f8d4a0592374</groupId>
		<artifactId>common-parent-pom</artifactId>
		<version>1.0.0</version>
		<relativePath/>
	</parent>
``` 

Update the element `version` to match the latest release available.

<br> 

## Runtime upgrade

In the next links, We have the latest release for the Mulesoft Runtime that we must update in our pom file to run the test cases against the latest version:

- https://docs.mulesoft.com/release-notes/mule-runtime/mule-4.4.0-release-notes
- https://repository-master.mulesoft.org/nexus/content/repositories/ci-releases/com/mulesoft/mule/distributions/mule-ee-distribution-standalone/

Update the runtime in the next section of the pom file, example:

```xml
		<app.runtime>4.4.0-20231110</app.runtime>
```

Release Notes for 4.5.0 (not yet implemented in this asset) https://docs.mulesoft.com/release-notes/mule-runtime/mule-4.5.0-release-notes

<br>

## List of plugins and dependencies
Next are the plugins and dependencies included in the parent POM and the link to check new versions.

**Plugins**

| Artifact      | Documentation / Versions available |
| ----------- | ----------- |
| mule-maven-plugin | https://mvnrepository.com/artifact/org.mule.tools.maven/mule-maven-plugin?repo=mulesoft-public | 
| | https://docs.mulesoft.com/release-notes/mule-maven-plugin/mule-maven-plugin-release-notes | 
| | https://help.mulesoft.com/s/article/Issues-with-Maven-3-9-0-when-deploying | 
| maven-enforcer-plugin | https://mvnrepository.com/artifact/org.apache.maven.plugins/maven-enforcer-plugin | 
| maven-resources-plugin | https://mvnrepository.com/artifact/org.apache.maven.plugins/maven-resources-plugin | 
| maven-clean-plugin | https://mvnrepository.com/artifact/org.apache.maven.plugins/maven-clean-plugin | 
| exchange-mule-maven-plugin | https://mvnrepository.com/artifact/org.mule.tools.maven/exchange-mule-maven-plugin?repo=mulesoft-releases | 

**Connectors**

| Artifact      | Documentation / Versions available |
| ----------- | ----------- |
| mule-http-connector | https://mvnrepository.com/artifact/org.mule.connectors/mule-http-connector?repo=mulesoft-releases | 
| mule-apikit-module | https://mvnrepository.com/artifact/org.mule.modules/mule-apikit-module?repo=mulesoft-releases | 
| mule-tracing-module | https://mvnrepository.com/artifact/org.mule.modules/mule-tracing-module?repo=mulesoft-releases | 
| munit-maven-plugin | https://mvnrepository.com/artifact/com.mulesoft.munit.tools/munit-maven-plugin?repo=mulesoft-releases | 
| | https://docs.mulesoft.com/release-notes/mule-maven-plugin/mule-maven-plugin-release-notes |
| munit-tools | https://mvnrepository.com/artifact/com.mulesoft.munit/munit-tools?repo=mulesoft-releases | 
| munit-runner | https://mvnrepository.com/artifact/com.mulesoft.munit/munit-runner |
| mule-validation-module | https://mvnrepository.com/artifact/org.mule.modules/mule-validation-module?repo=mulesoft-public |
| assertions | https://mvnrepository.com/artifact/org.mule.weave/assertions?repo=mulesoft-releases |

**Connectors for Mulesoft Metrics Toolkit Application**

| Artifact      | Documentation / Versions available |
| ------------- | ----------- |
| mule-objectstore-connector | https://mvnrepository.com/artifact/org.mule.connectors/mule-objectstore-connector?repo=mulesoft-releases | 
| mule-secure-configuration-property-module | https://mvnrepository.com/artifact/com.mulesoft.modules/mule-secure-configuration-property-module | 
| mule-custom-metrics-extension | https://docs.mulesoft.com/custom-metrics-connector/2.2/custom-metrics-connector-reference | 
|  | https://mvnrepository.com/artifact/org.mule.connectors/mule-custom-metrics-extension | 
| mule-sfdc-analytics-connector | https://www.mulesoft.com/exchange/com.mulesoft.connectors/mule-sfdc-analytics-connector/ | 
|  | https://docs.mulesoft.com/salesforce-analytics-cloud-connector/3.12 | 
| mule-mongodb-connector | https://www.mulesoft.com/exchange/com.mulesoft.connectors/mule-mongodb-connector/ | 
|  | https://mvnrepository.com/artifact/com.mulesoft.connectors/mule-mongodb-connector | 
| mongodb-driver-legacy | https://mvnrepository.com/artifact/org.mongodb/mongodb-driver-legacy | 
| mule-file-connector | https://mvnrepository.com/artifact/org.mule.connectors/mule-file-connector | 

**Databases**

| Artifact      | Documentation / Versions available |
| ----------- | ----------- |
| derby | https://mvnrepository.com/artifact/org.apache.derby/derby/10.14.2.0 | 
| | It is dependent on Mule JDK compatibility. This is the last version compatible with jdk8 |
| commons-dbcp2 | https://mvnrepository.com/artifact/org.apache.commons/commons-dbcp2 | 
| mssql-jdbc | https://mvnrepository.com/artifact/com.microsoft.sqlserver/mssql-jdbc | 
| mssql-jdbc_auth | https://mvnrepository.com/artifact/com.microsoft.sqlserver/mssql-jdbc_auth |
| mule-db-connector | https://mvnrepository.com/artifact/org.mule.connectors/mule-db-connector?repo=mulesoft-releases | 
| mule4-snowflake-connector | https://anypoint.mulesoft.com/exchange/com.mulesoft.connectors/mule4-snowflake-connector | 
| snowflake-jdbc | https://mvnrepository.com/artifact/net.snowflake/snowflake-jdbc | 
| | https://docs.snowflake.com/en/developer-guide/jdbc/jdbc | 

**Log Management**

| Artifact      | Documentation / Versions available |
| ----------- | ----------- |
| log4j-core | https://mvnrepository.com/artifact/org.apache.logging.log4j/log4j-core | 
| log4j-api | https://mvnrepository.com/artifact/org.apache.logging.log4j/log4j-api | 
| logzio-log4j2-appender | https://mvnrepository.com/artifact/io.logz.log4j2/logzio-log4j2-appender | 
| logzio-sender | https://mvnrepository.com/artifact/io.logz.sender/logzio-sender | 

**Optional artifacts**

| Artifact      | Documentation / Versions available |
| ----------- | ----------- |
| mule-ftp-connector | https://mvnrepository.com/artifact/org.mule.connectors/mule-ftp-connector | 
| mule-sftp-connector | https://mvnrepository.com/artifact/org.mule.connectors/mule-sftp-connector | 
| mule-salesforce-connector | https://anypoint.mulesoft.com/exchange/com.mulesoft.connectors/mule-salesforce-connector | 
| | gov version - <br> https://maven.gov.anypoint.mulesoft.com/api/v2/maven/com/mulesoft/connectors/mule-salesforce-connector/maven-metadata.xml |
| | https://docs.mulesoft.com/salesforce-connector/10.18 |
| mule-email-connector| https://mvnrepository.com/artifact/org.mule.connectors/mule-email-connector?repo=mulesoft-releases | 

**Spring Framework artifacts**

All next dependencies have a dependency on the Mulesoft Runtime version, so they shoud not be updated to the latest available version.

Mule Spring connector: [link](https://www.mulesoft.com/exchange/org.mule.modules/mule-spring-module)
Spring Module Release Notes: [link])(https://docs.mulesoft.com/release-notes/connector/spring-module-release-notes)

| Artifact      | Documentation / Versions available |
| ----------- | ----------- |
| spring-beans | https://mvnrepository.com/artifact/org.springframework/spring-beans | 
| spring-core | https://mvnrepository.com/artifact/org.springframework/spring-core | 
| spring-context | https://mvnrepository.com/artifact/org.springframework/spring-context | 
| spring-security-config | https://mvnrepository.com/artifact/org.springframework.security/spring-security-config | 
| spring-security-core | https://mvnrepository.com/artifact/org.springframework.security/spring-security-core | 
| spring-security-crypto | https://mvnrepository.com/artifact/org.springframework.security/spring-security-crypto | 
| spring-jdbc | https://mvnrepository.com/artifact/org.springframework/spring-jdbc | 

## Installation

Follow the next steps to install this asset in your organization.

### pom.xml changes:

**Update the groupId with your organization ID**

Example:
```xml
    <groupId>078eefffa-d139-48ed-92f5-f8d4a0592374</groupId>
    <artifactId>common-parent-pom</artifactId>
    <version>1.0.1</version>
    <packaging>pom</packaging>
``` 
**Update the distributionManagement section**

1) Update the Mulesoft cloud
2) Set the name of the repository ID, the default name is anypoint-exchange-v3

```xml
	<distributionManagement>
		<repository>
			<!-- Commercial version: Cloudhub -->

			<id>anypoint-exchange-v3</id>
			<name>Assets for your anypoint organization</name>
			<url>https://maven.anypoint.mulesoft.com/api/v3/organizations/${project.groupId}/maven</url>

			<!-- MuleSoft EU Cloud
			<url>https://maven.eu1.anypoint.mulesoft.com/api/v3/organizations/${project.groupId}/maven</url>
			-->

			<!-- MuleSoft Government Cloud
			<url>https://maven.gov.anypoint.mulesoft.com/api/v2/organizations/${project.groupId}/maven</url>
			-->

			<layout>default</layout>
		</repository>
	</distributionManagement>
``` 

### settings.xml changes:

1) The repository id from the pom.xml distributionManagement must be declared in this file

Example:

```xml
   <profiles>
      <profile>
         <id>mulesoft</id>
         <repositories>
            <repository>
               <id>anypoint-exchange-v3</id>
               <name>Assets for your anypoint organization</name>
               <url>https://maven.anypoint.mulesoft.com/api/v3/maven/</url>
            </repository>
            ...
            ...
		<repositories>
      <profile>
   <profiles>

``` 

Provide the credentials to authenticate to the Anypoint Platform, the following example uses a connected app.

```xml
   <servers>
      <server>
        <id>anypoint-exchange-v3</id>
        <username>~~~Client~~~</username>
        <password>6bbbbbbbf5624373b94775e9b17XXXXX~?~8302aaaaa92B436EB64829567eBXXXX</password>      </server>
      <server>
         <id>mulesoft-enterprise-repository</id>
         <username>MYUSER</username>
         <password>MYPASSWORD</password>
      </server>
   </servers>
``` 

A complete example of the settings file is provided in the repository, and the file name is settings-example.xml

**Connected App**

The connected app must have the role Exchange Contributor or the role Exchange Administrator.


## Recommended content
* [How to work with a parent pom](https://help.mulesoft.com/s/article/How-to-work-with-a-parent-pom)
* [How to deploy mule extension with pom hierarchy to exchange](https://help.mulesoft.com/s/article/How-to-deploy-mule-extension-with-pom-hierarchy-to-exchange)

---
[Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)