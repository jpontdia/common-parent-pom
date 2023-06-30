# mulesoft-parent-pom
![Powered by](https://img.shields.io/badge/Powered%20by-Mulesoft-blue.svg)
  ![Build and deploy](https://github.com/jpontdia/mulesoft-parent-pom/actions/workflows/build.yml/badge.svg)
<br>

Parent POM for Mulesoft applications

## Table of contents
1. [Description](#description)
1. [Using the parent POM](#usinge-the-parent-pom)
1. [Deployment in Anypoint](#deployment-in-anypoint-exchange)
    - [Prerequisites](#prerequisites)
    - [Deployment](#deployment)
3. [List of plugins and dependencies](#list-of-plugins-and-dependencies)
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
		<artifactId>parent-pom</artifactId>
		<version>1.0.35</version>
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
Configure settings.xml in your machine with the correct credentials for Anypoint Platform. The next file uses a connected app to deploy the asset in Anypoint Exchange, more information in: [How to set up your settings.xml and pom.xml using Connected Apps CI/CD without needing to manually retrieve a token](
https://help.mulesoft.com/s/article/How-to-set-up-your-settings-xml-and-pom-xml-using-Connected-Apps-CI-CD-without-needing-to-manually-retrieve-a-token)

```xml
<?xml version='1.0' encoding='UTF-8'?>
<settings xmlns='http://maven.apache.org/SETTINGS/1.0.0' xmlns:xsi='http://www.w3.org/2001/XMLSchema-instance' xsi:schemaLocation='http://maven.apache.org/SETTINGS/1.0.0 http://maven.apache.org/xsd/settings-1.0.0.xsd'>
   <activeProfiles>
      <activeProfile>mulesoft</activeProfile>
   </activeProfiles>
   <profiles>
      <profile>
         <id>mulesoft</id>
         <repositories>
            <repository>
               <id>anypoint-exchange-v3</id>
               <name>Assets for your anypoint organization</name>
               <url>https://maven.anypoint.mulesoft.com/api/v3/maven/</url>
            </repository>
            <repository>
               <snapshots>
                  <enabled>false</enabled>
               </snapshots>
               <id>central</id>
               <name>maven-central</name>
               <url>https://repo1.maven.org/maven2/</url>
            </repository>
            <repository>
               <id>mulesoft-releases</id>
               <name>mulesoft-releases</name>
               <url>https://repository-master.mulesoft.org/releases/</url>
            </repository>
            <repository>
               <id>mulesoft-snapshots</id>
               <name>MuleSoft Snapshot Repository</name>
               <url>https://repository-master.mulesoft.org/snapshots/</url>
            </repository>
            <repository>
               <id>mulesoft-enterprise-repository</id>
               <name>MuleSoft Enterprise Repository</name>
               <url>https://repository.mulesoft.org/nexus-ee/content/repositories/releases-ee/</url>
            </repository>
            <repository>
               <id>mulesoft-nexus-public</id>
               <name>Mulesoft Nexus Public Repository</name>
               <url>https://repository.mulesoft.org/nexus/content/repositories/public</url>
            </repository>
         </repositories>
         <pluginRepositories>
            <pluginRepository>
               <id>mulesoft-plugins</id>
               <name>Mulesoft plugins-release</name>
               <url>https://repository.mulesoft.org/nexus/content/repositories/public/</url>
            </pluginRepository>
            <pluginRepository>
               <id>central-plugins</id>
               <name>plugins-release</name>
               <url>https://repo1.maven.org/maven2</url>
            </pluginRepository>
            <pluginRepository>
               <id>mulesoft-snapshots</id>
               <name>MuleSoft Snapshot Repository</name>
               <url>https://repository-master.mulesoft.org/snapshots/</url>
            </pluginRepository>
            <pluginRepository>
               <id>mulesoft-plugins-release</id>
               <name>Mulesoft plugins-release</name>
               <url>https://repository.mulesoft.org/releases/</url>
               <snapshots>
                  <enabled>false</enabled>
                  <updatePolicy>always</updatePolicy>
                  <checksumPolicy>fail</checksumPolicy>
               </snapshots>
            </pluginRepository>
         </pluginRepositories>
      </profile>
   </profiles>
   <servers>
      <server>
         <id>anypoint-exchange-v3</id>
         <username>~~~Client~~~</username>
         <password>$cicd_connectedapp_clientid~?~$cicd_connectedapp_secret</password>
      </server>
      <server>
         <id>mulesoft-enterprise-repository</id>
         <username>$mulesoft_nexus_ee_user</username>
         <password>$mulesoft_nexus_ee_password</password>
      </server>
   </servers>
   <mirrors />
   <pluginGroups />
   <proxies />
</settings>
```

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

All next dependencies have a dependency on the Mulesoft Runtime version, so they shoud not be updated to the latest available version

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