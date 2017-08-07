# Change Log

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
