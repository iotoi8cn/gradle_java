<a href = "https://openjdk.java.net/">
<img width = "90%" height = "auto" src = "https://img.shields.io/badge/Java-Programming%20Language%20with%20Gradle-black?style=flat&logo=java" alt = "The Java Programming Language">
</a>


[![Ubuntu-(20.04LTS)](https://img.shields.io/badge/Ubuntu-%2020.04LTS-brightgreen)](https://ubuntu.com/)
[![GitHub release (latest by date)](https://img.shields.io/github/v/release/shyiko/jabba?label=jabba&logo=jabba)](https://github.com/shyiko/jabba)
[![Java zulu-openjdk:11](https://img.shields.io/badge/Java-zulu%20openjdk:11-brightgreen?style=flat&logo=java)](https://www.azul.com/downloads/zulu-community/?package=jdk)
[![GitHub release (latest by date)](https://img.shields.io/badge/Gradle-v6.6.1-black?style=flat&logo=gradle)](https://gradle.org/)
[![CircleCI](https://circleci.com/gh/cnruby/gradle_java/tree/basic_106.svg?style=svg)](https://app.circleci.com/pipelines/github/cnruby/gradle_java?branch=basic_106)




<h1>Lesson 106: Hello Package!</h1>

- Develop a Java application with Third Package

---



- [Keywords](#keywords)
- [Prerequisites](#prerequisites)
- [Create a Java Application with Gradle](#create-a-java-application-with-gradle)
- [Add the third Package to the build file `build.gradle`](#add-the-third-package-to-the-build-file-buildgradle)
  - [change the Gradle build file `build.gradle`](#change-the-gradle-build-file-buildgradle)
  - [build the file `build.gradle`](#build-the-file-buildgradle)
- [Develop the Java application with the Third Package `Gson`](#develop-the-java-application-with-the-third-package-gson)
  - [change the Java Code](#change-the-java-code)
  - [run the Java application on project](#run-the-java-application-on-project)
- [Package the Java application](#package-the-java-application)
  - [build the project](#build-the-project)
  - [run the Java application on different OS System](#run-the-java-application-on-different-os-system)
- [Download and Use This compelete Project](#download-and-use-this-compelete-project)
- [Result on the CI Website `CircleCI.com`](#result-on-the-ci-website-circlecicom)
- [Main References](#main-references)
- [References](#references)



## Keywords
- Third Package Library
- Ubuntu Java Gradle tutorial example `Continuous Integration` CI `Continuous Deployment` CD CircleCI



## Prerequisites
- [install JDK on Ubuntu 20.04](https://github.com/cnruby/gradle_java/blob/basic_101/README.md)
- [install Gradle on Ubuntu 20.04](https://github.com/cnruby/gradle_java/blob/basic_102/README.md)
- [CircleCI Account](https://circleci.com/vcs-authorize/)



## Create a Java Application with Gradle

```bash
git clone https://github.com/cnruby/gradle_java.git 106_gradle_java
git switch basic_106
cd 106_gradle_java
```



## Add the third Package to the build file `build.gradle`

### change the Gradle build file `build.gradle`

```bash
vi ./build.gradle
```

```bash
# FILE (./build.gradle)
...
dependencies {
  implementation 'org.json:json:20201115'
...
```

### build the file `build.gradle`

```bash
./gradlew
```



## Develop the Java application with the Third Package `Gson`

### change the Java Code

```bash
vi src/main/java/basic_106/App.java
```

```bash
# FILE (src/main/java/basic_106/App.java)
...
        System.out.println(new App().getGreeting());

        LongStream obj = new Random().longs(5,0,10);
        String json = new Gson().toJson(obj.toArray());

        System.out.println("json = " + json);
...
```

### run the Java application on project

```bash
./gradlew run
```

Result:

```bash
> Task :run
Hello world.
json = [3,5,7,6,7]

BUILD SUCCESSFUL in 467ms
2 actionable tasks: 2 executed
```



## Package the Java application
 
### build the project 
```bash
./gradlew clean build
```

### run the Java application on different OS System

```bash
unzip build/distributions/_gradle_java.zip 
./_gradle_java/bin/basic_106
```

Result:

```bash
Hello world.
json = [2,3,9,8,6]
```



## Download and Use This compelete Project

```bash
# Download
git clone -b basic_106 https://github.com/cnruby/gradle_java.git basic_106
```

```bash
# Use
cd basic_106
./gradlew run
```



## Result on the CI Website `CircleCI.com`
- [CircleCI Account](https://circleci.com/vcs-authorize/)



## Main References

## References
- https://github.com/johnrengelman/shadow
- 