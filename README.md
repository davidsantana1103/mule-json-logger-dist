# Mule JSON Logger Distribution

This repository is a utility to build and publish the [anypointcloud/json-logger](https://github.com/anypointcloud/json-logger) library to a personal GitHub Packages Maven registry.

## How to use

1.  Go to the **Actions** tab in this repository.
2.  Select the **Build and Publish JSON Logger** workflow.
3.  Click **Run workflow**.
4.  Specify the `version_tag` (e.g., `v3.1.0`) and the required `jdk_version`.
5.  Once the workflow completes, the package will be available in your GitHub Packages.

## Adding the dependency to your Mule API

Add the following to your `pom.xml`:

### 1. Repository
```xml
<repositories>
    <repository>
        <id>github</id>
        <url>https://maven.pkg.github.com/davidsantana1103/mule-json-logger-dist</url>
    </repository>
</repositories>
```

### 2. Dependency
```xml
<dependency>
    <groupId>cloud.anypoint</groupId>
    <artifactId>json-logger</artifactId>
    <version>3.1.0</version>
    <classifier>mule-plugin</classifier>
</dependency>
```

### 3. Server Configuration (settings.xml)
Ensure your `~/.m2/settings.xml` has credentials for GitHub:
```xml
<servers>
    <server>
        <id>github</id>
        <username>davidsantana1103</username>
        <password>YOUR_GITHUB_TOKEN</password>
    </server>
</servers>
```
