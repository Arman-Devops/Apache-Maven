# Apache Maven 

```bash
$ mvn -version

Apache Maven 3.9.4 (dfbb324ad4a7c8fb0bf182e6d91b0ae20e3d2dd9)
Maven home: /opt/maven
Java version: 11.0.20.1, vendor: Ubuntu, runtime: /usr/lib/jvm/java-11-openjdk-amd64
Default locale: en_US, platform encoding: UTF-8
OS name: "linux", version: "5.15.0-71-generic", arch: "amd64", family: "unix"
```
## mvn compile
This command is used to compile the main source code of the project located in src/main/java of the project. The command compiles all the Java files in the main directory. The command does not perform any tasks beyond the compile phase.

```bash
mvn compile

```
Sample Output:
```bash
[INFO] Compiling 1 source file with javac [debug target 1.8] to target/classes
[WARNING] bootstrap class path not set in conjunction with -source 8
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  3.363 s
[INFO] Finished at: 2023-09-18T13:18:32+03:00
[INFO] ------------------------------------------------------------------------

```

# mvn package
It is used when building the Maven project into a JAR, WAR etc. To use it, execute the command:
```bash
mvn package
```
Sample output:
```bash
[INFO] Building jar: /home/thor/mvn-projects/my-app/target/my-app-1.0-SNAPSHOT.jar
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  5.826 s
[INFO] Finished at: 2023-09-18T13:20:05+03:00
[INFO] ------------------------------------------------------------------------
```
Once complete, you will see the location of the JAR file printed. The command executes the compile, testCompile and test before proceeding with the build.

## mvn install
This command will build and install the JAR, WAR, pom.xml etc project files to the local repo. To use it, run:
```bash
mvn install
```
Sample Output:
```bash
[INFO] Installing /home/thor/mvn-projects/my-app/pom.xml to /home/thor/.m2/repository/com/mycompany/app/my-app/1.0-SNAPSHOT/my-app-1.0-SNAPSHOT.pom
[INFO] Installing /home/thor/mvn-projects/my-app/target/my-app-1.0-SNAPSHOT.jar to /home/thor/.m2/repository/com/mycompany/app/my-app/1.0-SNAPSHOT/my-app-1.0-SNAPSHOT.jar
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  2.838 s
[INFO] Finished at: 2023-09-18T13:21:06+03:00
[INFO] ------------------------------------------------------------------------
```
## mvn deploy
It deploys the artefacts to a remote repository configured in the pom.xmlfile under with distributionManagement tag. To provide authentication details, include them in the settings.xml file.
```bash
mvn deploy
```
## mvn validate
It is used to validate and ensure that all the settings and the required information are correct for the Maven project.
```bash
mvn validate
```
Sample Output:
```bash
$ mvn validate
[INFO] Scanning for projects...
[INFO] 
[INFO] ----------------------< com.mycompany.app:my-app >----------------------
[INFO] Building my-app 1.0-SNAPSHOT
[INFO]   from pom.xml
[INFO] --------------------------------[ jar ]---------------------------------
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  0.196 s
[INFO] Finished at: 2023-09-18T13:21:59+03:00
[INFO] ------------------------------------------------------------------------
```
## mvn test
This is used when running the test cases for your Maven project. For example:
```bash
$ mvn test
[INFO]  T E S T S
[INFO] -------------------------------------------------------
[INFO] Running com.mycompany.app.AppTest
[INFO] Tests run: 1, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0.036 s -- in com.mycompany.app.AppTest
[INFO] 
[INFO] Results:
[INFO] 
[INFO] Tests run: 1, Failures: 0, Errors: 0, Skipped: 0
[INFO] 
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  2.231 s
[INFO] Finished at: 2023-09-18T13:35:08+03:00
[INFO] ------------------------------------------------------------------------
```
## mvn verify
```bash
mvn verify
```
Sample Output:
```bash
INFO]  T E S T S
[INFO] -------------------------------------------------------
[INFO] Running com.mycompany.app.AppTest
[INFO] Tests run: 1, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0.039 s -- in com.mycompany.app.AppTest
[INFO] 
[INFO] Results:
[INFO] 
[INFO] Tests run: 1, Failures: 0, Errors: 0, Skipped: 0
[INFO] 
[INFO] 
[INFO] --- jar:3.3.0:jar (default-jar) @ my-app ---
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  2.564 s
[INFO] Finished at: 2023-09-18T13:35:56+03:00
[INFO] ------------------------------------------------------------------------
```
## mvn Clean
This command is used when deleting the Maven project. It cleans and deletes the target directory. To use it, switch to the Maven directory and issue:

```bash
$ mvn clean
[INFO] Scanning for projects...
[INFO] 
[INFO] ----------------------< com.mycompany.app:my-app >----------------------
[INFO] Building my-app 1.0-SNAPSHOT
[INFO]   from pom.xml
[INFO] --------------------------------[ jar ]---------------------------------
[INFO] 
[INFO] --- clean:3.2.0:clean (default-clean) @ my-app ---
[INFO] Deleting /home/thor/mvn-projects/my-app/target
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  0.554 s
[INFO] Finished at: 2023-09-18T13:36:22+03:00
[INFO] ------------------------------------------------------------------------
```
## mvn -f dir/pom.xml package
The command is used when building a project from another path. You need to specify the location of the pom.xml file:
```bash
mvn -f dir/pom.xml package
```
## mvn -DskipTests package
The option is used to skip the tests during the build process:



```bash
mvn -DskipTests package
##OR
mvn -Dmaven.test.skip=true package

```