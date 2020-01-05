#ANT 
Ant is a build tool, a small program designed to help software teams develop big programs
by automating all the drudge-work tasks of compiling code, running tests, and
packaging the results for redistribution. 

Ant is written in Java and is designed to be cross-platform, easy to use, extensible, and scalable. It can be used in a small personal project, or it can be used in a large, multi-team software project. It aims to automate
your entire build process.

In the Java world, it’s the primary build tool for large and multiperson projects—
things bigger than a single person can do under an IDE. Why? Well, we’ll get to that
in section 1.2—the main thing is that it’s written in Java and focuses on building and
testing Java projects.

Ant has an XML syntax, which is good for developers already familiar with XML.
For developers unfamiliar with XML, well, it’s one place to learn the language. These
days, all Java developers need to be familiar with XML.

In a software project experiencing constant change, an automated build can provide
a foundation of stability. Even as requirements change and developers struggle to
catch up, having a build process that needs little maintenance and remembers to test
everything can take a lot of housekeeping off developers’ shoulders. Ant can be the
means of controlling the building and deployment of Java software projects that
would otherwise overwhelm a team.

## The core concepts of Ant
We have just told you why Ant is great, but now we are going to show you what makes
it great: its ingredients, the core concepts. The first is the design goal: Ant was designed
to be an extensible tool to automate the build process of a Java development project.
A software build process is a means of going from your source—code and documents—
to the product you actually deliver. If you have a software project, you have
a build process, whether or not you know it. It may just be “hit the compile button
on the IDE,” or it may be “drag and drop some files by hand.” Neither of these are
very good because they aren’t automated and they’re often limited in scope.

With Ant, you can delegate the work to the machine and add new stages to your
build process. Testing, for example. Or the creation of XML configuration files from
your Java source. Maybe even the automatic generation of the documentation.

Once you have an automated build, you can let anyone build the system. Then you
can find a spare computer and give it the job of rebuilding the project continuously.
This is why automation is so powerful: it starts to give you control of your project.

## Build Files

Ant uses XML files called build files to describe how to build a project. In the build file
developers list the high-level various goals of the build—the targets—and actions to
take to achieve each goal—the tasks.

## A build file contains one project

Each build file describes how to build one project. Very large projects may be composed
of multiple smaller projects, each with its own build file. A higher-level build
file can coordinate the builds of the subprojects.

## Each project contains multiple targets
Within the build file’s single project, you declare different targets. These targets may
represent actual outputs of the build, such as a redistributable file, or activities, such
as compiling the source or running the tests.

## Targets can depend on other targets

When declaring a target, you can declare which targets have to be built first. This can
ensure that the source gets compiled before the tests are run and built, and that the
application is not uploaded until the tests have passed. When Ant builds a project, it
executes targets in the order implied by their dependencies.

## Targets contain tasks

Inside targets, you declare what work is needed to complete that stage of the build
process. You do this by listing the tasks that constitute each stage. When Ant executes
a target, it executes the tasks inside, one after the other.

## Tasks do the work

Ant tasks are XML elements, elements that the Ant runtime turns into actions. Behind
each task is a Java class that performs the work described by the task’s attributes and
nested data. These tasks are expected to be smart—to handle much of their own argument
validation, dependency checking, and error reporting.

## Sample ANT Build file

`
<?xml version="1.0" ?>
<project name="ourproject" default="deploy">
<target name="init">
<mkdir dir="build/classes" />
<mkdir dir="dist" />
</target>
<target name="compile" depends="init">
<javac srcdir="src"
destdir="build/classes"/>
</target>
<target name="doc" depends="init" >
<javadoc destdir="build/classes"
sourcepath="src"
packagenames="org.*" />
</target>
<target name="package" depends="compile,doc" >
<jar destfile="dist/project.jar"
basedir="build/classes"/>
</target>
<target name="deploy" depends="package" >
<ftp server="${server.name}"
userid="${ftp.username}"
password="${ftp.password}">
<fileset dir="dist"/>
</ftp>
</target>
</project>
`