[![CircleCI](https://circleci.com/gh/circleci/USING_JAXB_TO_GET_XML.svg?style=shield)](https://github.com/zikozee/USING_JAXB_TO_GET_XML)

To get XML, also JSON as we did using seperate modules

XML(Main focus)
we got the json, 
converted it in postman Content-type application/xml, Accept application/xml, by using the below
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
 
 we generated xsd and placed in customer.xsd
 
 and then generated needed classes using JAXB2


