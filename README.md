
[![CircleCI](https://circleci.com/gh/circleci/USING-JAXB-TO-GET-XML.svg?style=svg)](https://github.com/zikozee/USING_JAXB_TO_GET_XML)



To get XML, also JSON as we did using seperate modules

XML(Main focus)
we got the json, 
converted it in postman and setting header Content-type application/xml, Accept application/xml, by using the below
        <dependency>
            <groupId>com.fasterxml.jackson.dataformat</groupId>
            <artifactId>jackson-dataformat-xml</artifactId>
        </dependency>
        <dependency>
            <groupId>org.codehaus.woodstox</groupId>
            <artifactId>woodstox-core-asl</artifactId>
            <version>4.4.1</version>
        </dependency>
 so the JSON can be converted to xml in postman
 
 we then picked the xml in postman and went to https://www.freeformatter.com/xsd-generator.html#ad-output
 using venetianBlind
 
 we generated xsd and placed in customer.xsd and then generated needed classes using JAXB2
 using the below plugin 
 <build>
        <plugins>
            <plugin>
                <groupId>org.codehaus.mojo</groupId>
                <artifactId>jaxb2-maven-plugin</artifactId><!--Note there is a dependency version 2-->
                <version>2.3.1</version>
                <executions>
                    <execution>
                        <id>xjc</id>
                        <goals>
                            <goal>xjc</goal>
                        </goals>
                    </execution>
                </executions>
                <configuration>
                    <!-- The package of your generated sources -->
                    <packageName>guru.springframework.model</packageName>
                    <sources>
                        <source>src/main/resources/xsd</source>
                    </sources>
                </configuration>
            </plugin>
        </plugins>
    </build>
 
 **Then we can then refactor in all places to use generated model class, that way we can properly generate XML and JSON simultaneouly
 only tweaking header content**
 
 and the XML will be properly formatted
 remember there is shorter cut using jez data-faster...xml
 
 UNIT Test and INTEGRATED TEST EMBEDDED


