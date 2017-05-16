# Change Log

## 0.2.1 - XXXX

* Configured `mvn package` to generate source JAR file.

## 0.2.0 - 2017-01-16

* Upgraded Spock from 1.0 to 1.1 to get `@SpringBootTest` to work.
* Fixed "Failure to find com.gemstone.gemfire:gemfire:pom:x.x.x" error thrown by `maven-project-info-reports-plugin`.
* Enabled Groovy compiler.
* Enabled Maven enforcer plugin to prevent certain dependencies from getting through and to ensure minimum Maven version is used.
* Configured `mvn package` to create 2 artifacts: one as a dependency and another as a fat JAR.

## 0.1.0 - 2017-01-15

* Initial.
