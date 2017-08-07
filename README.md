# spring-boot-ci

This parent POM:-
 
* Consolidates static code analysis report configuration in one place and declutters app's `pom.xml`.
* Generates reports for Continuous Integration servers ([Jenkins](https://jenkins-ci.org/), etc) and Maven site. 
* Enables Spring Boot by inheriting from the `spring-boot-starter-parent` to leverage the full power of Spring Boot.
    * While an app may enable Spring Boot without inheriting from the `spring-boot-starter-parent`, it can only leverage Spring Boot's dependency management but not the plugin management. Furthermore, it requires the app to re-configure several plugins used by Spring Boot to continue working properly.
* Enables Groovy compiler.
* Includes a Maven profile to deploy:-
    * Project artifacts to [Sonatype OSSRH (OSS Repository Hosting)](https://oss.sonatype.org).
    * Maven generated site to project [GitHub](https://github.com/) page.

## Parent POM Dependency

```xml
<project ...>
    <parent>
        <groupId>com.github.choonchernlim</groupId>
        <artifactId>spring-boot-ci</artifactId>
        <version>0.2.3</version>
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
mvn clean deploy -P ossrh,ossrh-deploy
```

###  Deploy Site to GitHub

```xml
mvn clean test site -P ossrh,ossrh-deploy
```

## Build Plugins 

* [Maven Compiler Plugin](https://maven.apache.org/plugins/maven-compiler-plugin/) - Enables Groovy compiler.
* [Groovy Eclipse Maven Plugin](https://github.com/groovy/groovy-eclipse/wiki/Groovy-Eclipse-Maven-plugin) - Handles possible missing `src/main/java` and `src/test/java` when using Groovy.
* [Spring Boot Maven Plugin](http://docs.spring.io/spring-boot/docs/current/maven-plugin/) - Enables Spring Boot support.
* [Versions Maven plugin](http://www.mojohaus.org/versions-maven-plugin/) - Handles dependencies and plugins date.
* [Surefire Maven Plugin](http://maven.apache.org/surefire/maven-surefire-plugin/) - Runs unit tests.
* [Maven Failsafe Plugin](http://maven.apache.org/surefire/maven-failsafe-plugin/) - Runs integration tests.
* [Maven Site Plugin](http://maven.apache.org/plugins/maven-site-plugin/) - Generates site.
* [JaCoCo Maven Plugin](http://www.eclemma.org/jacoco/) - Code coverage report for JVM languages.
* [Maven Enforcer Plugin](http://maven.apache.org/enforcer/maven-enforcer-plugin/) Bans certain dependencies and ensures minimum Maven version is met.
* [Maven Source Plugin](https://maven.apache.org/plugins/maven-source-plugin/) - Generates source JAR file.

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

## Troubleshooting

* If the JaCoCo web report is not rendering properly in the GitHub page, please read this post for solution: [JaCoCo Web Report Not Rendering Properly in GitHub Pages](http://myshittycode.com/2015/07/22/jacoco-web-report-not-rendering-properly-in-github-pages/)                                    


