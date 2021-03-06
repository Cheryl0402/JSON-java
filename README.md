![Json-Java logo](https://github.com/stleary/JSON-java/blob/master/images/JsonJava.png?raw=true)

<sub><sup>image credit: Ismael Pérez Ortiz</sup></sub>


JSON in Java [package org.json]
===============================

[![Maven Central](https://img.shields.io/maven-central/v/org.json/json.svg)](https://mvnrepository.com/artifact/org.json/json)

**[Click here if you just want the latest release jar file.](https://search.maven.org/remotecontent?filepath=org/json/json/20211205/json-20211205.jar)**


# Overview

[JSON](http://www.JSON.org/) is a light-weight language-independent data interchange format.

The JSON-Java package is a reference implementation that demonstrates how to parse JSON documents into Java objects and how to generate new JSON documents from the Java classes.

Project goals include:
* Reliable and consistent results
* Adherence to the JSON specification 
* Easy to build, use, and include in other projects
* No external dependencies
* Fast execution and low memory footprint
* Maintain backward compatibility
* Designed and tested to use on Java versions 1.6 - 1.11

The files in this package implement JSON encoders and decoders. The package can also convert between JSON and XML, HTTP headers, Cookies, and CDL.

The license includes this restriction: ["The software shall be used for good, not evil."](https://en.wikipedia.org/wiki/Douglas_Crockford#%22Good,_not_Evil%22) If your conscience cannot live with that, then choose a different package.

# If you would like to contribute to this project

For more information on contributions, please see [CONTRIBUTING.md](https://github.com/stleary/JSON-java/blob/master/docs/CONTRIBUTING.md)

Bug fixes, code improvements, and unit test coverage changes are welcome! Because this project is currently in the maintenance phase, the kinds of changes that can be accepted are limited. For more information, please read the [FAQ](https://github.com/stleary/JSON-java/wiki/FAQ).

# Build Instructions

The org.json package can be built from the command line, Maven, and Gradle. The unit tests can be executed from Maven, Gradle, or individually in an IDE e.g. Eclipse.

**Building from the command line**

*Build the class files from the package root directory src/main/java*
````
javac org/json/*.java
````

*Create the jar file in the current directory*
````
jar cf json-java.jar org/json/*.class
````

*Compile a program that uses the jar (see example code below)*
````
javac -cp .;json-java.jar Test.java (Windows)
javac -cp .:json-java.jar Test.java (Unix Systems)
````

*Test file contents*

````
import org.json.JSONObject;
public class Test {
    public static void main(String args[]){
       JSONObject jo = new JSONObject("{ \"abc\" : \"def\" }");
       System.out.println(jo.toString());
    }
}
````

*Execute the Test file*
```` 
java -cp .;json-java.jar Test (Windows)
java -cp .:json-java.jar Test (Unix Systems)
````

*Expected output*

````
{"abc":"def"}
````


**Tools to build the package and execute the unit tests**

Execute the test suite with Maven:
```
mvn clean test
```

Execute the test suite with Gradlew:

```
gradlew clean build test
```
# Team Member:
- Yi Chen (Cheryl0402)
- Chao Liu (lordchao)

# Notes about Milestone 2
You can build the project using ways mentioned above.
@@ -107,16 +13,3 @@ If you are using IntelliJ, just simply open the project. You will be able to run
They are in the last part of the XMLTest class
- task1 test --- run the extractObjectTest() 
- task2 replace test --- run the replaceObjectTest() 


# Notes

For more information, please see [NOTES.md](https://github.com/stleary/JSON-java/blob/master/docs/NOTES.md)

# Files

For more information on files, please see [FILES.md](https://github.com/stleary/JSON-java/blob/master/docs/FILES.md)

# Release history:

For the release history, please see [RELEASES.md](https://github.com/stleary/JSON-java/blob/master/docs/RELEASES.md)


# Milestone 3

 **Team Member:**
- Yi Chen (Cheryl0402)
- Chao Liu (lordchao)


**What we did**

Inside *src/main/java/org.json* folder, we added a static method toJSONObject(Reader reader, YOURTYPEHERE keyTransformer)  
to XML.java class. It takes a String reader and a function as a parameter, which allows clients to apply any kinds of key
transformation.
With an abstract function type as a parameter, clients can do any customized key modification to an jsonObject without
changing code inside the method. Clients can simply define a transform function and pass it to the toJSONObject,which
can greatly improve the re-usability of the toJSONObject method and the performance of clients use.

**To Build**

Load and build the project following the instructions above.
If you use IntelliJ, you can simply open it with the IDE.


**To test the method**

Go to *src/test/XMLTest*, you can click the run button beside the addPrefixFunctionTest and
reverseFunctionTest to run the test cases.

# Milestone 4

**Team Member:**
- Yi Chen (Cheryl0402)
- Chao Liu (lordchao)


**What we did**

Inside `src/main/java/org.json` folder, we added a streaming method to JSONObject.java class by using interface Spliterator
This method transforms JSONObject to <key, value> pair JSONObject stream so the client can trace JSONObject node with 
stream operations.

**To Build**

Load and build the project following the instructions above.
If you use IntelliJ, you can simply open it with the IDE.


**To test the method**

Go to `src/test/JSONObjectTest`, you can click the run button beside the toStreamTest1(), toStreamTest2(), and 
toStreamTest3() to run the test cases. The first test focuses on checking if the streaming method is successfully transformed 
an JSONObject into <key, value> pair JSONObject node. The second and third tests test stream operations on the transformed 
JSONObject node stream.

# Milestone 5

**Team Member:**
- Yi Chen (Cheryl0402)
- Chao Liu (lordchao)

**To Build**

Load and build the project following the instructions above.
If you use IntelliJ, you can simply open it with the IDE.


**To test the method**

Go to `src/test/XMLTest`, you can click the run button beside the test cases inside the milestone5 test
part.