checkstyle-rules
================

Set of checkstyle rules i usually use in my projects.

to use it include following repository in your pom.xml

```
<repositories>
	<repository>
		<id>bintray-milenkovicm</id>
		<url>http://dl.bintray.com/milenkovicm/maven/</url>
		<releases>
			<enabled>true</enabled>
		</releases>
		<snapshots>
			<enabled>false</enabled>
		</snapshots>
	</repository>
</repositories>
<pluginRepositories>
	<pluginRepository>
		<id>bintray-milenkovicm</id>
		<url>http://dl.bintray.com/milenkovicm/maven/</url>
		<releases>
			<enabled>true</enabled>
		</releases>
		<snapshots>
			<enabled>false</enabled>
		</snapshots>
	</pluginRepository>
</pluginRepositories>
```
```
<plugin>
	<artifactId>maven-checkstyle-plugin</artifactId>
	<version>2.10</version>
	<dependencies>
		<dependency>
			<groupId>com.github.milenkovicm</groupId>
			<artifactId>checkstyle-rules</artifactId>
			<version>1.0.0-SNAPSHOT</version>
		</dependency>
	</dependencies>

	<executions>
		<execution>
			<id>check-style</id>
			<goals>
				<goal>check</goal>
			</goals>
			<phase>validate</phase>
			<configuration>
				<consoleOutput>true</consoleOutput>
				<logViolationsToConsole>true</logViolationsToConsole>
				<failsOnError>true</failsOnError>
				<failOnViolation>true</failOnViolation>
				<configLocation>default/checkstyle.xml</configLocation>
				<includeTestSourceDirectory>false</includeTestSourceDirectory>
			</configuration>
		</execution>
	</executions>
</plugin>
```