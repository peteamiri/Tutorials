# Explain the concepts and capabilities of ANT.

Ant is a build tool that is java based. A build tool performs the following tasks:

1. Compiling java code into byte code
2. Placing this byte code in a package
3. Deployment to production systems
4. Document creation and release notes preparation.

# Capabilities of ANT:

ANT tool is extended by using java classes. The configuration files are XML-based. Each task of building directory tree is executed by using the object that implements the Task interface.

ANT provides the cross-platform deployment that can run on any platform.
Explain the concepts and capabilities of ANT.

Open
Ant is an open source project available under the Apache license. Therefore, its source code can be downloaded and modified.
Additionally, Ant uses XML build files which make its development easy.

Cross Platform
Use of XML along with Java makes Ant the perfect solution for developing programs designed to run or be built across a range of different operating systems.

Extensible
New tasks are used to extend the capabilities of the build process, while build listeners are used to help hook into the build process to add extra error tracking functionality.

Integration
As Ant is extensible and open, it can be integrated with any editor or development environment easily.

## Question 1. What Is Ant?
Answer :
Ant is an open source code .It is Java-based build tool sponsored by Apache Software Foundation. It is a program for putting all the pieces of a program together. A simple definition might state that “Ant is a Java-based build tool from Apache Software Foundation”. Ant is kind of like Make.
## Question 2. Why Do You Call It Ant?
Answer :
The ant is acronym of ”Another Neat Tool” according to James Duncan Davidson. Ants are very small and can carry heavy weight. So as Job of Apache ant. Its name is called ANT.
Question 3. What Is A Build Tool?
Answer :
A built tool is software which is used to build project, directory structure, copy necessary files to that directory ,compile files ,create jars, set path and class-path ,Build the documentation ,Validate the source code, deploy, debug, and run, clear the workspace.
Question 4. Explain The Concepts Of Ant?
Answer :
Ant is a build tool that is java based. A build tool performs the following tasks:
Open: Ant is an open source project available under the Apache license. Therefore, its source code can be downloaded and modified.
Additionally, Ant uses XML build files which make its development easy.
Cross Platform: Use of XML along with Java makes Ant makes it the perfect solution for developing programs designed to run or be built across a range of different operating systems.
Extensible: New tasks are used to extend the capabilities of the build process, while build listeners are used to help hook into the build process to add extra error tracking functionality.
Integration: As Ant is extensible and open, it can be integrated with any editor or development environment easily.
Question 5. What Are The Capabilities Of Ant?
Answer :
ANT tool is extended by using java classes. The configuration files are XML-based. Each task of building directory tree is executed by using the object that implements the Task interface.
ANT provides the cross-platform deployment that can run on any platform.
Question 6. Why Ant Is A Great Build Tool?
Answer :
Ant is great build tool due to following reason:
Ant is a Java-based build tool designed to be cross-platform, easy to use, extensible, and scalable.
Ant can be used in a small personal project as well as ant can be used in a large, multi-team software project.
Ant syntax is very easy to learn.
Ant syntax used XML format .We need only specifies our task only on build.xml file.
Ant is easy to use .eliminating the full-time make file engineer common on large Make-based software projects.
Question 7. How Many Ways We Can Set Properties Into Build Ant File?
Answer :
There are six ways to set properties:
Supplying both the name and value attribute.<property name=”src.dir” value=”src”/>
Supplying both the name and refid attribute.
Setting the file attribute with the filename of the property file to load.
Setting the url attribute with the url from which to load the properties.
Setting the resource attribute with the resource name of the property file to load.
Setting the environment attribute with a prefix to use.
We can use the combinations of all above in our build files .But only one should be used at a time.
Question 8. How You Can Explain Ant Property?
Answer :
A project can have a set of properties .A property has name and value .The name is case sensitive and Properties are immutable this mean once set property its will not change. Properties may be used in the value of task attributes.
Question 9. What Is Dependency? How It Is Used Into Ant? What Is Its Use?
Answer :
Dependencies are do something when complete it. In ant we are using dependencies by using an attribute “depends” .In this attribute we have pass values for which the target depends .This mean we first need to execute the target which is passed into this attribute.
Question 10. How We Can Create A Jar Using Ant?
Answer :
To make a jar of classes we need set target as jar. In this target we need to make directory in which jar will stored. Then we need jar tag to make the jar .In this tag we have pass two attributes first is name of destination directory and second one is the name of base directory where our all class files are stored .We need a manifest to create a jar file. In manifest tag we have pass two attributes first is name of manifest file name and second is its value.
Question 11. How You Can Prepare A Project In Ant?
Answer :
We can prepare a project by making a build.xml as a build file and using following tag. Inside this tag we have defined standard targets (such as build, clean etc), etc.
Question 12. What Is Different Between Ant And Make?
Answer :
The most important difference between Ant and Make is that Ant uses XML to describe the build process and its dependencies, whereas Make uses its Makefile format. By default the ant XML file is named build.xml.
Question 13. What Is Ivy?
Answer :
Ivy is a popular dependency manager .IVY is basically focused on flexibility and simplicity.
The latest version of Ivy is 2.1.0.
Key features of the 2.1.0 release are
The Key features of Ivy is enhanced Maven2 compatibility, with several bug fixes and more pom features covered.
new options for the Ivy Ant tasks and commandline
configuration intersections and configuration groups
numerous bug fixes & improvements as documented in Jira and in the release notes
Question 14. How We Can Set Path Path And Classpath Into An Ant Build File?
Answer :
Ant does not need to set class path.
Question 15. Explain Ant Functionality?
Answer :
Ant is an open source project available under the Apache license. Therefore, its source code can be downloaded and modified. 
Additionally, Ant uses XML build files which make its development easy.
Cross Platform.
Use of XML along with Java makes Ant makes it the perfect solution for developing programs designed to run or be built across a range of different operating systems.
Extensible.
New tasks are used to extend the capabilities of the build process, while build listeners are used to help hook into the build process to add extra error tracking functionality.
As Ant is extensible and open, it can be integrated with any editor or development environment easily.
Question 16. Explain Using Ant And Give An Small Example?
Answer :
Before start using ANT, we should be clear about the project name and the .java files and most importantly, the path where the .class files are to be placed.
For example, we want the application HelloWorld to be used with ant. The Java source files are in a subdirectory called Dirhelloworld, and the .class files are to put into a sub directory called Helloworldclassfiles.
1. The build file by name build.xml is to be written. The script is as follows
<project name=”HelloWorld” default=”compiler” basedir=”.”> 
<target name=”compiler”> 
<mkdir dir = “Helloworldclassfiles”> 
<javac srcdir=”Dirhelloworld” destdir=”Helloworldclassfiles”> 
</target> 
</project>
2. Now run the ant script to perform the compilation:
C :\> ant 
Buildfile: build.xml
and see the results in the extra files and directory created:
c:\>dir Dirhelloworld 
c:\>dir Helloworldclassfiles
All the .java files are in Dirhelloworld directory and all the corresponding .class are in Helloworldclassfiles directory.
Question 17. Explain How To Import .jar Files?
Answer :
<path id="classpath.base">
<pathelement location="${glassfish.home}/lib/javaee.jar" />
<fileset dir="${lib.dir}">
<include name="log4j-1.2.15.jar" />
<include name="el-impl-1.0.jar" />
</fileset>
</path>
Question 18. Explain How To Use Clean In Ant Script?
Answer :
<target name="clean" depends="-clean" />
<target name="-clean">
<delete dir="${build.dir}/*" />
<delete dir="${build.dir}/classes" />
<delete dir="${build.dir}/test-classes" />
<delete dir="${build.dir}/release" />
<delete file="${build.dir}/*.jar" />
<delete file="${build.dir}/VERSION.txt" />
</target>
Question 19. Explain How To Use Pmd Validation In Ant Script?
Answer :
<target name="validate" depends="-init">
<mkdir dir="${build.dir}/pmd-reports" />
<pmd shortFilenames="true" rulesetfiles="${basedir}/.ruleset">
<formatter type="xml" tofile="${build.dir}/pmd-reports/report.xml" />
<fileset dir="${src.dir}/main/java/com/" includes="**/*.java" />
<fileset dir="${src.dir}/test/java" includes="**/*.java" />
</pmd>
<xslt style="${ant.home}/etc/xslt/pmd-report-per-class.xslt"
in="${build.dir}/pmd-reports/report.xml"
out="${build.dir}/pmd-reports/report.html" />
</target>
Question 20. Explain How To Compile Using Ant Script?
Answer :
<target name="compile" depends="-init">
<mkdir dir="${build.dir}/classes" />
<javac destdir="${build.dir}/classes" includeantruntime="false" debug="true" optimize="true" verbose="false" deprecation="false" source="1.5" target="1.5">
<classpath refid="classpath.base" />
<src path="${src.dir}/main/java" />
</javac>
</target>
Question 21. Explain How To Test Classes For Junit Using Ant Script?
Answer :
<target name="test" depends="-copytestresources, compile">
<mkdir dir="${build.dir}/junit-reports" />
<junit printsummary="false"
fork="on"
haltonfailure="false"
failureproperty="test.failure">
<classpath refid="classpath.junit" />
<formatter type="plain" />
<batchtest todir="${build.dir}/junit-reports">
<fileset dir="${build.dir}/test-classes" includes="**/*Test.class" />
</batchtest>
</junit>
<junitreport tofile="target/junit-reports/TEST.xml">
<fileset dir="${target}/junit-reports" includes="TEST-*.xml" />
<report format="frames" todir="${target}/junit-reports" />
</junitreport>
</target>
Question 22. Explain How To Make Ant User Interactive?
Answer :
The org.apache.tools.ant.input.InputHandler interface is used to implement the user input. To perform the user input, the application creates InputRequest object and this object will be passed to InputHandler. The user input will be rejected if it is invalid.
The InputHandler interface has exactly one method, by name handleInput(InputRequest request). This method throws org.apache.tools.ant.BuildException, if the input is invalid.
Question 23. Explain How To Use Ant-contrib Tasks?
Answer :
Copy the ant-contrib.jar to the directory ant*/lib. Copy ant-contrib.jar to your ant*/lib directory.
Append the following code snippet to avail all the ant-contrib tasks.
<taskdef resource=”net/sf/antcontrib/antcontrib.properties”/>
Question 24. Explain How To Debug My Ant Script?
Answer :
ANT script can be debugged in the following ways:
By echoing at the place to debug. The problem is easily known. This is similar to printf() function in C and System.out.println() in Java.
By using project.log (“message”) in the java script or the customized ant task.
By running ANT with –verbose / -debug options. These options provide more information on what is the process going and at which location.
Question 25. How Can I Use Ant To Run A Java Application?
Answer :
The following is an example to run a Java application in using ANT:
<target name=”run” depends=”some.target”,some.other.target”>
<java classname=”${run.class}” fork=”yes”>
<classpath>
<path refrid = “classpath” />
</classpath>
<jvmarg line=”${debug.jvmargs}”/>
<jvmarg line=”${my.jvmargs}”/> < BR>
<jvmarg line=”${run.jvmargs}”/>
<arg line=”${run.args}”/>
</java>
</target>
## Question 26. Explain How To Use Runtime In Ant?
Answer :
There is no need to use Runtime in ant. Because ant has Runtime counterpart by name ExecTask. ExecTask is in the package org.apache.tools.ant.taskdefs. The Task is created by using the code in the customized ant Task. The code snippet is as follows:
ExecTask execTask = (ExecTask)project.createTask (“exec”);
## Question 27. Explain How To Modify Properties In Ant?
Answer :
We can not modify the properties in ant. The properties in ant are immutable in nature.