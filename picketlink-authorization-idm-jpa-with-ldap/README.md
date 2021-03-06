picketlink-authorization-idm-jpa-with-ldap: PicketLink IDM Authorization Example using JPA
===============================
Author: Pedro Igor
Level: Intermediate
Technologies: CDI, PicketLink
Summary: Basic example that demonstrates IDM-based authorization using a JPA and LDAP identity store to store different types
Source: <https://github.com/jboss-developer/jboss-picketlink-quickstarts/>

What is it?
-----------

This example demonstrates the use of *CDI 1.0* and *PicketLink IDM* to store different types using different identity stores.

It will show you how to use a LDAP identity store to store your users, groups and group membership relationship.
While using the JPA identity store to store roles and support ad-hoc attributes.

System requirements
-------------------

All you need to build this project is Java 6.0 (Java SDK 1.6) or better, Maven 3.0 or better.

The application this project produces is designed to be run on JBoss Enterprise Application Platform 6 or WildFly.


Configure Maven
---------------

If you have not yet done so, you must [Configure Maven](http://www.jboss.org/jdf/quickstarts/jboss-as-quickstart/#configure_maven) before testing the quickstarts.


Start JBoss Enterprise Application Platform 6 or WildFly with the Web Profile
-------------------------

1. Open a command line and navigate to the root of the JBoss server directory.
2. The following shows the command line to start the server with the web profile:

        For Linux:   JBOSS_HOME/bin/standalone.sh
        For Windows: JBOSS_HOME\bin\standalone.bat

Configure LDAP
--------------------

You can run this quickstart using your own or the embedded LDAP server. You must configure the LDAP server *before* you build and deploy the quickstart.

### Configure the Quickstart to Use Your LDAP Server

To run this quickstart using your own LDAP Server, modify the String constant values in the  `org.jboss.as.quickstarts.picketlink.idm.ldap.IDMConfiguration` class to the connection values for your LDAP server.

### Configure the Quickstart to Use the Embedded LDAP Server

To run this quickstart using an embedded LDAP server:

1. Open a new command line an navigate to the root of this quickstart directory.

2. Execute the following command:

        mvn -Dtest=LDAPServer test
3. The prompt does not return and you should see the following messages indicating the embedded LDAP server has started successfully:

        Running LDAPServer
        Starting Apache DS server
        Time taken = 71milisec
        Going to import LDIF:ldap/users.ldif
        Time taken = 6milisec

To terminate the embedded LDAP serve, hit CTRL-C.

Build and Deploy the Quickstart
-------------------------

_NOTE: The following build command assumes you have configured your Maven user settings. If you have not, you must include Maven setting arguments on the command line. See [Build and Deploy the Quickstarts](../README.md#build-and-deploy-the-quickstarts) for complete instructions and additional options._

1. Make sure you have started the JBoss Server as described above.
2. Open a command line and navigate to the root directory of this quickstart.
3. Type this command to build and deploy the archive:

        For EAP 6:     mvn clean package jboss-as:deploy
        For WildFly:   mvn -Pwildfly clean package wildfly:deploy

4. This will deploy `target/picketlink-authorization-idm-jpa-with-ldap.war` to the running instance of the server.


Access the application
---------------------

The application will be running at the following URL: <http://localhost:8080/picketlink-authorization-idm-jpa-with-ldap>.


Undeploy the Archive
--------------------

1. Make sure you have started the JBoss Server as described above.
2. Open a command line and navigate to the root directory of this quickstart.
3. When you are finished testing, type this command to undeploy the archive:

        For EAP 6:     mvn jboss-as:undeploy
        For WildFly:   mvn -Pwildfly wildfly:undeploy


Run the Quickstart in JBoss Developer Studio or Eclipse
-------------------------------------
You can also start the server and deploy the quickstarts from Eclipse using JBoss tools. For more information, see [Use JBoss Developer Studio or Eclipse to Run the Quickstarts](../README.md#use-jboss-developer-studio-or-eclipse-to-run-the-quickstarts)


Debug the Application
------------------------------------

If you want to debug the source code or look at the Javadocs of any library in the project, run either of the following commands to pull them into your local repository. The IDE should then detect them.

        mvn dependency:sources
        mvn dependency:resolve -Dclassifier=javadoc
