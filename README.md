# spring-boot-ci

This parent POM extends `spring-boot-starter-parent` and generates static code analysis reports for Maven site and 
Continuous Integration Servers ([Jenkins](https://jenkins-ci.org/), etc). 

It also includes a profile that allows you to push:-
* project artifacts to [Sonatype OSSRH (OSS Repository Hosting)](https://oss.sonatype.org).
* Maven generated site to project [GitHub](https://github.com/) page.

## How to Use

Add the following configuration to your project's pom.xml:-

```xml
<project ...>
    <parent>
        <groupId>com.github.choonchernlim</groupId>
        <artifactId>spring-boot-ci</artifactId>
        <version>0.1.0</version>
    </parent>
    ...
</project>
```

###  Jenkins Integration

```xml
mvn clean test site
```

### Deploy to Sonatype OSSRH

```xml
mvn clean deploy -Possrh-deploy
```

###  Deploy Site to GitHub

```xml
mvn clean test site -Possrh-deploy
```

## Important Notes

* If the JaCoCo web report is not rendering properly in the GitHub page, please read this post for solution: [JaCoCo Web Report Not Rendering Properly in GitHub Pages](http://myshittycode.com/2015/07/22/jacoco-web-report-not-rendering-properly-in-github-pages/)                                    

## Build Plugins 

* [Versions Maven plugin](http://www.mojohaus.org/versions-maven-plugin/) - Handles dependencies and plugins date.
* [Surefire Maven Plugin](http://maven.apache.org/surefire/maven-surefire-plugin/) - Runs unit tests.
* [Maven Failsafe Plugin](http://maven.apache.org/surefire/maven-failsafe-plugin/) - Runs integration tests.
* [Maven Site Plugin](http://maven.apache.org/plugins/maven-site-plugin/) - Generates site.
* [JaCoCo Maven Plugin](http://www.eclemma.org/jacoco/) - Code coverage report for JVM languages.

## Reporting Plugins 

* [Maven Project Info Reports Plugin](https://maven.apache.org/plugins/maven-project-info-reports-plugin/) - Generates reports information about the project.
* [Maven Surefire Reports Plugin](http://maven.apache.org/surefire/maven-surefire-report-plugin/) - Parses generated test results from both unit tests and integration tests.
* [JaCoCo Maven Plugin](http://www.eclemma.org/jacoco/) - Code coverage report for JVM languages.
* [Maven Javadoc Plugin](https://maven.apache.org/plugins/maven-javadoc-plugin/) - Generates Javadoc.
* [Maven JXR Plugin](http://maven.apache.org/plugins/maven-jxr-plugin/) - Generates a cross-reference of the project's sources.
* [JDepend Maven Plugin](http://www.mojohaus.org/jdepend-maven-plugin/) - Generates design quality metrics for each Java package.
* [Maven PMD Plugin](http://maven.apache.org/plugins/maven-pmd-plugin/) - Generates PMD and CPD reports.
* [FindBugs Maven Plugin](http://www.mojohaus.org/findbugs-maven-plugin/) - Inspects Java bytecode for occurrences of bug patterns.
* [TagList Maven Plugin](http://www.mojohaus.org/taglist-maven-plugin/) - Generates a report on various tags found in the code.

## Profile: "ossrh-deploy" 

* [Nexus Staging Maven Plugin](https://github.com/sonatype/nexus-maven-plugins/tree/master/staging/maven-plugin) - Deploys artifacts to Sonatype OSSRH.
* [Maven Source Plugin](https://maven.apache.org/plugins/maven-source-plugin/) - Generates source code.
* [GitHub Site Plugin](https://github.com/github/maven-plugins) - Generates Maven site in project GitHub page.
* [Maven Javadoc Plugin](https://maven.apache.org/plugins/maven-javadoc-plugin/) - Generates Javadoc.
* [Maven GPG Plugin](http://maven.apache.org/plugins/maven-gpg-plugin/) - Signs all of the project's attached artifacts with GnuPG..

