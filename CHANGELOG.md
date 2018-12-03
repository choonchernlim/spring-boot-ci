# Change Log

## 0.4.0 - 2018-12-03

* Configured Maven Surefire Plugin to always use JUnit as provider instead of accidentally detecting other test frameworks, such as TestNG.
* Added Spock to "Dependency Management" block.
* Spring Boot 2.1.1 no longer have `groovy-all` due to 
```
org.springframework.boot:spring-boot-starter-parent  2.0.4.RELEASE -> 2.1.1.RELEASE

${cglib-nodep.version} ............................... 3.2.7 -> 3.2.9
${groovy-eclipse-batch.version} ............... 2.4.15-01 -> 2.5.4-01
${maven-pmd-plugin.version} ........................ 3.10.0 -> 3.11.0
${maven-jxr-plugin.version} ............................ 2.5 -> 3.0.0
${maven-surefire-report-plugin.version} .......... 2.22.0 -> 3.0.0-M1
${jacoco-maven-plugin.version} ....................... 0.8.1 -> 0.8.2
${spock.version} ................... 1.1-groovy-2.4 -> 1.2-groovy-2.5
```

## 0.3.2 - 2018-08-16

* BUG - `java.lang.NoClassDefFoundError: org/apache/maven/doxia/siterenderer/DocumentContent` when running `mvn site`.

## 0.3.1 - 2018-08-15

* Upgraded `spring-boot` from `2.0.4.RELEASE` to take advantage of Spring Core `5.0.8.RELEASE`, which fixes URI encoding problem. See https://jira.spring.io/browse/SPR-17039.

```

${groovy-eclipse-compiler.version} ............. 2.9.2-01 -> 3.0.0-01
${groovy-eclipse-batch.version} ............... 2.4.3-01 -> 2.4.15-01
${cglib-nodep.version} ............................... 3.2.6 -> 3.2.7
${maven-project-info-reports-plugin.version} ........... 2.9 -> 3.0.0
${maven-surefire-report-plugin.version} ............ 2.21.0 -> 2.22.0
```

## 0.3.0 - 2018-06-13

* Upgraded `spring-boot` from v1.x to v2.x.

```
PARENT
org.springframework.boot:spring-boot-starter-parent  1.5.9.RELEASE -> 2.0.2.RELEASE

PLUGINS
maven-pmd-plugin ...................................... 3.8 -> 3.10.0
maven-surefire-report-plugin ....................... 2.20.1 -> 2.21.0
org.jacoco:jacoco-maven-plugin ....................... 0.7.9 -> 0.8.1

DEPENDENCIES
cglib:cglib-nodep .................................... 3.2.5 -> 3.2.6
```

## 0.2.4 - 2017-11-29

```
PARENT
org.springframework.boot:spring-boot-starter-parent  1.5.6.RELEASE -> 1.5.9.RELEASE

PLUGINS
maven-surefire-report-plugin ......................... 2.20 -> 2.20.1
org.codehaus.mojo:findbugs-maven-plugin .............. 3.0.4 -> 3.0.5
```

## 0.2.3 - 2017-08-07

* Configured Maven GPG Plugin to work with GPG 2.1 so that it will pick up `gpg.passphrase` defined in `settings.xml`.

## 0.2.2 - 2017-08-02

* Configured Jacoco to work.
* Removed `joda-time` from banned dependencies because it is too restricting.
* Updated dependencies.

```
PARENT
org.springframework.boot:spring-boot-starter-parent  1.5.3.RELEASE -> 1.5.6.RELEASE
```

## 0.2.1 - 2017-05-30

* Configured `mvn package` to generate source JAR file.
* Dependency Management: Added `cglib-nodep`.
* Fixed "... uses prerequisites which is only intended for maven-plugin projects but not for non maven-plugin projects" warning.

## 0.2.0 - 2017-05-16

* Upgraded Spock from 1.0 to 1.1 to get `@SpringBootTest` to work.
* Fixed "Failure to find com.gemstone.gemfire:gemfire:pom:x.x.x" error thrown by `maven-project-info-reports-plugin`.
* Enabled Groovy compiler.
* Enabled Maven enforcer plugin to prevent certain dependencies from getting through and to ensure minimum Maven version is used.
* Configured `mvn package` to create 2 artifacts: one as a dependency and another as a fat JAR.

## 0.1.0 - 2017-05-15

* Initial.
