# mulesoft-parent-pom
>Parent POM for deployment in CloudHub 1 and 2

## Table of contents
1. [Using the parent POM](#usinge-the-parent-pom)
2. [Deployment in Anypoint](#deployment-in-anypoint-exchange)
  * [Prerequisites](#prerequisites)
  * [Deployment](#deployment)
3. [List of plugins and dependencies](#list-of-plugins-and-dependencies)
4. [Recommended content](#recommended-content)

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
* Java Development Kit (JDK) 8. Must be version 8!
* Apache Maven, version 3.8 or later.
* Anypoint account credentials

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
Mandatory properties in POM 
| Artifact      | Documentation / List of versions |
| ----------- | ----------- |
| mule-maven-plugin | https://mvnrepository.com/artifact/org.mule.tools.maven/mule-maven-plugin?repo=mulesoft-public <br>
https://docs.mulesoft.com/release-notes/mule-maven-plugin/mule-maven-plugin-release-notes       |
| api.tags      | Anypoint Visualizer. Tags for the service separated by commas, example: customer, finance |


## Recommended content
* [How to work with a parent pom](https://help.mulesoft.com/s/article/How-to-work-with-a-parent-pom)
* [How to deploy mule extension with pom hierarchy to exchange](https://help.mulesoft.com/s/article/How-to-deploy-mule-extension-with-pom-hierarchy-to-exchange)

---
[Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)