# Test dependency BoM

Maven BoM (Bill of Materials) defining dependency versions for
  * JUnit,
  * Spock,
  * Geb,
  * Selenium + web drivers,
  * web driver manager by bonigarcia.

Please import this artifact with `type=pom`, `scope=import` from the `dependencyManagement` section of your project.

In order to also get the dependencies themselves plus basic configuration like GebConfig, please also add
the dependency `de.scrum-master.test:test-resources` with `scope=test` to your project.

Example:

```xml
<dependencyManagement>
  <dependencies>
    <!-- BoM with test dependency versions -->
    <dependency>
      <groupId>de.scrum-master.test</groupId>
      <artifactId>test-bom</artifactId>
      <version>1.0</version>
      <type>pom</type>
      <scope>import</scope>
    </dependency>
    <!-- Test resources + base configuration + base classes for Spock, Geb, Selenium -->
    <dependency>
      <groupId>de.scrum-master</groupId>
      <artifactId>test-resources</artifactId>
      <version>1.0</version>
      <scope>test</scope>
    </dependency>
  </dependencies>
</dependencyManagement>

<dependencies>
  <!-- Test resources + base configuration + base classes for Spock, Geb, Selenium -->
  <dependency>
    <groupId>de.scrum-master</groupId>
    <artifactId>test-resources</artifactId>
    <scope>test</scope>
  </dependency>
</dependencies>
```
