---
layout: page
title: "Getting Started"
description: ""
---
{% include JB/setup %}

ND4J requires [Java 7](http://www.oracle.com/technetwork/java/javase/downloads/jdk7-downloads-1880260.html).

### Maven

You can install both ND4J and Deeplearning4j separately via [Maven](https://maven.apache.org/download.cgi), a build automation tool used for Java projects. Maven installations require you to: 

* Create your root directory; e.g. nd4j or deeplearning4j.
* Create a pom.xml file within that directory.
* Add dependencies and other information to that POM file (see below).
* Choose your IDE -- [Eclipse](http://books.sonatype.com/m2eclipse-book/reference/creating-sect-importing-projects.html), [IntelliJ](https://www.jetbrains.com/idea/help/importing-project-from-maven-model.html) or [Netbeans](http://wiki.netbeans.org/MavenBestPractices) -- and import the project via Maven. (Alternatively, you can run *mvn install* within the root.)
* Note that by using Maven you never run git clone (everything is called from the POM), and you never have to deal with source code, only byte code and jar files.  

For your POM, you need to specify two dependencies, which are detailed in the [Readme](https://github.com/SkymindIO/nd4j/blob/master/README.md). The API, like so:

	 <dependency>
	   <groupId>org.nd4j</groupId>
	   <artifactId>nd4j-api</artifactId>
	   <version>${nd4j.version}</version>
	 </dependency>

This is the core implementation that handles most of the interop.

You'll also need to specify a backend dependency. 

ND4J supports several backends, ranging from Cuda to different native implementations. While there are several Blas implementations on the JVM, none of them support a Matlab/Numpy-like interface, so we had to make one. 

See our [downloads](http://nd4j.org/downloads.html) page for a more thorough explanation on the backends available.
    
## Jblas

 <dependency>
   <groupId>org.nd4j</groupId>
   <artifactId>nd4j-jblas</artifactId>
   <version>${nd4j.version}</version>
 </dependency>
  
## Net lib Blas:
 
 <dependency>
   <groupId>org.nd4j</groupId>
   <artifactId>nd4j-api</artifactId>
   <version>${nd4j.version}</version>
 </dependency>

## Jcublas (Cuda/GPUs):

 <dependency>
   <groupId>org.nd4j</groupId>
   <artifactId>nd4j-jcublas</artifactId>
   <version>${nd4j.version}</version>
 </dependency>

##Bypassing Maven

See our [downloads](http://nd4j.org/downloads.html) page.

You can then manually import the jar files in to [Eclipse](http://stackoverflow.com/questions/3280353/how-to-import-a-jar-in-eclipse), [Intellij](http://stackoverflow.com/questions/1051640/correct-way-to-add-lib-jar-to-an-intellij-idea-project) or [Netbeans](http://gpraveenkumar.wordpress.com/2009/06/17/abc-to-import-a-jar-file-in-netbeans-6-5/).

###Working with source

If you want to develop for ND4J, just *git clone* the software and run this Maven command:

    mvn clean install -DskipTests -Dmaven.javadoc.skip=true

### Next Steps

Now you're ready to run the examples cited in our [documentation](../elementwise.html).

Here's our [Github repo](https://github.com/SkymindIO/nd4j). You can access the core through [Maven](http://maven.apache.org/download.cgi).