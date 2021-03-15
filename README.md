Wildfly Bootable Apache MyFaces JSF Galleon Pack
==============================================================================

This Wildfly Bootable Galleon feature pack allows you to use Apache MyFaces JSF implementation 
instead of the built in Mojarra implementation.  Apache MyFaces has much better performance
and memory usage than Mojarra as well as less bugs. See [JSF Benchmark](https://github.com/tandraschko/jsfbench)

## Java EE 8 Usage
To use with Wildfly Bootable with Java EE8 you must use the `8.x` version of this feature pack based on MyFaces [2.3.x](https://myfaces.apache.org/#/core23).

## Jakarta EE 9 Usage
To use with Wildfly Bootable with Jakarta EE9 you must use the `9.x` version of this feature pack based on MyFaces [3.0.x](https://myfaces.apache.org/#/core30)

## Plugin Example
Using the plugin you must add the plugin itself and then add the `<layer>myfaces</layer>` like:

```xml
<plugin>
    <groupId>org.wildfly.plugins</groupId>
    <artifactId>wildfly-jar-maven-plugin</artifactId>
    <configuration>
        <feature-packs>
            <feature-pack>
                <location>wildfly@maven(org.jboss.universe:community-universe)#${version.wildfly}</location>
            </feature-pack>
            <feature-pack>
                <groupId>com.melloware</groupId>
                <artifactId>wildfly-myfaces-galleon-pack</artifactId>
                <version>8.0.0.Final</version>
            </feature-pack>
        </feature-packs>
        <layers>
            <layer>ejb-lite</layer>
            <layer>jpa</layer>
            <layer>jsf</layer>
            <layer>myfaces</layer>
        </layers>
        <plugin-options>
            <jboss-fork-embedded>${plugin.fork.embedded}</jboss-fork-embedded>
        </plugin-options>
    </configuration>
    <executions>
        <execution>
            <goals>
                <goal>package</goal>
            </goals>
        </execution>
    </executions>
</plugin>
```

## Real World Example

[Wildfly Faces](https://github.com/melloware/wildfly-faces) is a sample JSF application using the PrimeFaces Showcase and makes it a Wildfly Bootable application.
It uses this plugin to use MyFaces instead of Mojarra.
