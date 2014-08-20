Maven Plugin : filtered-enforce-rule
====================================

This component contains a custom Enforcer Rule for [Maven Dependency Convergence](http://maven.apache.org/enforcer/enforcer-rules/dependencyConvergence.html). Convergence rule can now accept a include/exclude artifact set.


Sample Usage
------------
```XML
    <build>
        <plugins>
            <plugin>
                <groupId>org.apache.maven.plugins</groupId>
                <artifactId>maven-enforcer-plugin</artifactId>
                <version>1.3.1</version>
                <dependencies>
                    <dependency>
                        <groupId>com.basil.maven.enforcer</groupId>
                        <artifactId>enforcer-rules</artifactId>
                        <version>1.0</version>
                    </dependency>
                </dependencies>
                <executions>
                    <execution>
                        <id>custom-enforce</id>
                        <configuration>
                            <rules>
                                <myCustomRule
                                    implementation="org.basil.maven.enforcer.rules.FilteredDependencyConvergence">
                                    <includes>
                                        <include>com.basil.*</include>
                                        <include>org.apache.commons</include>
                                    </includes>
                                </myCustomRule>
                            </rules>
                        </configuration>
                        <goals>
                            <goal>enforce</goal>
                        </goals>
                    </execution>
                </executions>
            </plugin>
        </plugins>
    </build>
```