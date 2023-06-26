# parent-pom
![Powered by](https://img.shields.io/badge/Powered%20by-Mulesoft-blue.svg)
  ![Build and deploy](https://github.com/jpontdia/mulesoft-parent-pom/actions/workflows/build.yml/badge.svg)
<br>
Parent POM for Mulesoft applications

## Table of contents
1. [Using the parent POM](#usinge-the-parent-pom)
1. [Deployment in Anypoint](#deployment-in-anypoint-exchange)
    - [Prerequisites](#prerequisites)
    - [Deployment](#deployment)
3. [List of plugins and dependencies](#list-of-plugins-and-dependencies)
1. [Recommended content](#recommended-content)

<br>  

## Using the parent POM
To use the parent POM in any of the child projects, specify the `parent`
section in the child `pom.xml` as follows:
```xml
	<parent>
		<groupId>078efef1-d139-48ed-92f5-f8d4a0592374</groupId>
		<artifactId>parent-pom</artifactId>
		<version>1.0.1</version>
		<relativePath/>
	</parent>
``` 

Update the element `version` to match the latest release available.

## Deployment in Anypoint Exchange

### Prerequisites
To compile and build the project:

 - Java Development Kit (JDK) 8
 - Apache Maven, version 3.8 or later.
 - Anypoint account credentials

<br>

### Deployment
Configure settings.xml in your machine with the correct credentials for Anypoint Platform.
The configuration file used for this parent POM and all the services that implement this artifact is: [settings.xml](
https://github.com/jpontdia/mule-micorp-pom/blob/main/settings.xml)

```xml
	<servers>
		<server>
			<id>anypoint-exchange-v3</id>
			<username>MY-USER</username>
			<password>MY-PASSWORD</password>
		</server>
	</servers>
```

The "id" element must be the same between settings.xml and the repository defined in pom.xml.
Deploy the pom changes to the maven repository for your Anypoint platform, from the command line type:

```xml
mvn deploy
```

<br>

## List of plugins and dependencies
Next are the plugins and dependencies included in the parent POM and the link to check new versions.

**Plugins**

| Artifact      | Documentation / Versions available |
| ----------- | ----------- |
| maven-deploy-plugin      | [https://mvnrepository.com/artifact/org.apache.maven.plugins/maven-deploy-plugin](https://mvnrepository.com/artifact/org.apache.maven.plugins/maven-deploy-plugin)       
| mule-maven-plugin | https://mvnrepository.com/artifact/org.mule.tools.maven/mule-maven-plugin?repo=mulesoft-public | 
| | https://docs.mulesoft.com/release-notes/mule-maven-plugin/mule-maven-plugin-release-notes | 
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


**Optional artifacts**

| Artifact      | Documentation / Versions available |
| ----------- | ----------- |
| derby | https://mvnrepository.com/artifact/org.apache.derby/derby/10.14.2.0 | 
| | It is dependent on Mule JDK compatibility. This is the last version compatible with jdk8 |
| commons-dbcp2 | https://mvnrepository.com/artifact/org.apache.commons/commons-dbcp2 | 
| log4j-core | https://mvnrepository.com/artifact/org.apache.logging.log4j/log4j-core | 
| log4j-api | https://mvnrepository.com/artifact/org.apache.logging.log4j/log4j-api | 
| logzio-log4j2-appender | https://mvnrepository.com/artifact/io.logz.log4j2/logzio-log4j2-appender | 
| logzio-sender | https://mvnrepository.com/artifact/io.logz.sender/logzio-sender | 
| mule-db-connector | https://mvnrepository.com/artifact/org.mule.connectors/mule-db-connector?repo=mulesoft-releases | 
| mule-ftp-connector | https://mvnrepository.com/artifact/org.mule.connectors/mule-ftp-connector | 
| mule-sftp-connector | https://mvnrepository.com/artifact/org.mule.connectors/mule-sftp-connector | 
| mule-salesforce-connector | https://anypoint.mulesoft.com/exchange/com.mulesoft.connectors/mule-salesforce-connector | 
| | https://docs.mulesoft.com/salesforce-connector/10.18 |

**Spring Framework artifacts**
All next dependencies have a dependency on the Mulesoft Runtime version
| Artifact      | Documentation / Versions available |
| ----------- | ----------- |
| spring-beans | https://mvnrepository.com/artifact/org.springframework/spring-beans | 
| spring-core | https://mvnrepository.com/artifact/org.springframework/spring-core | 
| spring-context | https://mvnrepository.com/artifact/org.springframework/spring-context | 
| spring-security-config | https://mvnrepository.com/artifact/org.springframework.security/spring-security-config | 
| spring-security-core | https://mvnrepository.com/artifact/org.springframework.security/spring-security-core | 
| spring-security-crypto | https://mvnrepository.com/artifact/org.springframework.security/spring-security-crypto | 
| spring-jdbc | https://mvnrepository.com/artifact/org.springframework/spring-jdbc | 



## Recommended content
* [How to work with a parent pom](https://help.mulesoft.com/s/article/How-to-work-with-a-parent-pom)
* [How to deploy mule extension with pom hierarchy to exchange](https://help.mulesoft.com/s/article/How-to-deploy-mule-extension-with-pom-hierarchy-to-exchange)

---
[Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)