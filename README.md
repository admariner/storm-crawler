[![storm-crawler](http://stormcrawler.net/img/Logo-small.jpg)](http://stormcrawler.net/)
=============

[![license](https://img.shields.io/github/license/apache/incubator-stormcrawler.svg?maxAge=2592000?style=plastic)](http://www.apache.org/licenses/LICENSE-2.0)
![Build Status](https://github.com/apache/incubator-stormcrawler/actions/workflows/maven.yml/badge.svg)
[![javadoc](https://javadoc.io/badge2/apache/incubator-stormcrawler-core/javadoc.svg)](https://javadoc.io/doc/org.apache.stormcrawler/storm-crawler-core/)
[![Coverage Status](https://coveralls.io/repos/github/apache/incubator-stormcrawler/badge.svg?branch=master)](https://coveralls.io/github/apache/incubator-stormcrawler?branch=master)

StormCrawler is an open source collection of resources for building low-latency, scalable web crawlers on [Apache Storm](http://storm.apache.org/). It is provided under [Apache License](http://www.apache.org/licenses/LICENSE-2.0) and is written mostly in Java.

## Quickstart

NOTE: These instructions assume that you have [Apache Maven](https://maven.apache.org/install.html) installed. You will need to install [Apache Storm](http://storm.apache.org/) to run the crawler.

StormCrawler requires Java 11 or above.

The version of Apache Storm to install must match the one defined in the pom.xml file of your topology. The major version of StormCrawler mirrors the one from Apache Storm, i.e whereas StormCrawler 1.x used Storm 1.2.3, the current version now requires Storm 2.6.1. DigitalPebble's [Ansible-Storm](https://github.com/DigitalPebble/ansible-storm) repository contains resources to install Apache Storm using Ansible. Alternatively, this [stormCrawler-docker](https://github.com/DigitalPebble/stormcrawler-docker) project should help you run Apache Storm on Docker.

Once Storm is installed, the easiest way to get started is to generate a brand new StormCrawler project using \: 

`mvn archetype:generate -DarchetypeGroupId=com.digitalpebble.stormcrawler -DarchetypeArtifactId=storm-crawler-archetype -DarchetypeVersion=2.11`

You'll be asked to enter a groupId (e.g. com.mycompany.crawler), an artefactId (e.g. stormcrawler), a version, a package name and details about the user agent to use.

This will not only create a fully formed project containing a POM with the dependency above but also the default resource files, a default CrawlTopology class and a configuration file. Enter the directory you just created (should be the same as the artefactId you specified earlier) and follow the instructions on the README file.

Alternatively if you can't or don't want to use the Maven archetype above, you can simply copy the files from [archetype-resources](https://github.com/apache/incubator-stormcrawler/tree/master/archetype/src/main/resources/archetype-resources).

Have a look at the code of the [CrawlTopology class](https://github.com/apache/incubator-stormcrawler/blob/master/archetype/src/main/resources/archetype-resources/src/main/java/CrawlTopology.java), the [crawler-conf.yaml](https://github.com/apache/incubator-stormcrawler/blob/master/archetype/src/main/resources/archetype-resources/crawler-conf.yaml) file as well as the files in [src/main/resources/](https://github.com/apache/incubator-stormcrawler/tree/master/archetype/src/main/resources/archetype-resources/src/main/resources), they are all that is needed to run a crawl topology : all the other components come from the core module.

## Getting help

The [WIKI](https://github.com/apache/incubator-stormcrawler/wiki) is a good place to start your investigations but if you are stuck please use the tag [stormcrawler](http://stackoverflow.com/questions/tagged/stormcrawler) on StackOverflow or ask a question in the [discussions](https://github.com/apache/incubator-stormcrawler/discussions) section. Alternatively, you can join our [Discord channel](https://discord.com/invite/C62MHusNnG).

[DigitalPebble Ltd](http://digitalpebble.com) provide commercial support and consulting for StormCrawler.

## Note for developers 

Please format your code before submitting a PR with 

```
mvn git-code-format:format-code -Dgcf.globPattern=**/*
```

Each commit must include a DCO which looks like this

```
Signed-off-by: Jane Smith <jane.smith@email.com>
```

You may type this line on your own when writing your commit messages. However, if your `user.name` and `user.email` are set in your git config, you can use `-s` or `--signoff` to add the `Signed-off-by` line to the end of the commit message.


## Thanks

![alt tag](https://www.yourkit.com/images/yklogo.png)

YourKit supports open source projects with its full-featured Java Profiler.
YourKit, LLC is the creator of <a href="https://www.yourkit.com/java/profiler/index.jsp">YourKit Java Profiler</a>
and <a href="https://www.yourkit.com/.net/profiler/index.jsp">YourKit .NET Profiler</a>,
innovative and intelligent tools for profiling Java and .NET applications.
