# graalvm-v2301-json-test

- For https://github.com/oracle/graal/issues/9929 and https://github.com/apache/shardingsphere/issues/32927 .

- Verified unit test under Ubuntu 22.04.4 LTS with `SDKMAN!`.

```shell
sdk install java 23.0.1-graalce

git clone git@github.com:linghengqian/graalvm-v2301-json-test.git
cd ./graalvm-v2301-json-test/
sdk use java 23.0.1-graalce
./mvnw -PgenerateMetadata -DskipNativeTests -e -T 1C clean test native:metadata-copy
```

- The log is as follows.

```shell
$ ./mvnw -PgenerateMetadata -DskipNativeTests -e -T 1C clean test native:metadata-copy
[INFO] Error stacktraces are turned on.
[INFO] Scanning for projects...
[INFO] Found GraalVM installation from JAVA_HOME variable.
[INFO] 
[INFO] Using the MultiThreadedBuilder implementation with a thread count of 16
[INFO] 
[INFO] -----------< io.github.linghengqian:graalvm-v2301-json-test >-----------
[INFO] Building graalvm-v2301-json-test 1.0-SNAPSHOT
[INFO]   from pom.xml
[INFO] --------------------------------[ jar ]---------------------------------
[INFO] 
[INFO] --- clean:3.2.0:clean (default-clean) @ graalvm-v2301-json-test ---
[INFO] Deleting /home/linghengqian/TwinklingLiftWorks/git/public/graalvm-v2301-json-test/target
[INFO] 
[INFO] --- resources:3.3.1:resources (default-resources) @ graalvm-v2301-json-test ---
[INFO] skip non existing resourceDirectory /home/linghengqian/TwinklingLiftWorks/git/public/graalvm-v2301-json-test/src/main/resources
[INFO] 
[INFO] --- compiler:3.13.0:compile (default-compile) @ graalvm-v2301-json-test ---
[INFO] No sources to compile
[INFO] 
[INFO] --- resources:3.3.1:testResources (default-testResources) @ graalvm-v2301-json-test ---
[INFO] skip non existing resourceDirectory /home/linghengqian/TwinklingLiftWorks/git/public/graalvm-v2301-json-test/src/test/resources
[INFO] 
[INFO] --- compiler:3.13.0:testCompile (default-testCompile) @ graalvm-v2301-json-test ---
[INFO] Recompiling the module because of changed source code.
[INFO] Compiling 1 source file with javac [debug target 23] to target/test-classes
[INFO] 
[INFO] --- surefire:3.2.5:test (default-test) @ graalvm-v2301-json-test ---
[WARNING]  Parameter 'systemProperties' is deprecated: Use systemPropertyVariables instead.
[INFO] Surefire report directory: /home/linghengqian/TwinklingLiftWorks/git/public/graalvm-v2301-json-test/target/surefire-reports
[INFO] Using auto detected provider org.apache.maven.surefire.junitplatform.JUnitPlatformProvider
[INFO] 
[INFO] -------------------------------------------------------
[INFO]  T E S T S
[INFO] -------------------------------------------------------
[INFO] Running io.github.linghengqian.SimpleTest
[INFO] Tests run: 1, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0.091 s -- in io.github.linghengqian.SimpleTest
[INFO] 
[INFO] Results:
[INFO] 
[INFO] Tests run: 1, Failures: 0, Errors: 0, Skipped: 0
[INFO] 
[INFO] 
[INFO] --- native:0.10.3:merge-agent-files (test-native) @ graalvm-v2301-json-test ---
[INFO] Merging agent 1 files into /home/linghengqian/TwinklingLiftWorks/git/public/graalvm-v2301-json-test/target/native/agent-output/test
jdk.graal.compiler.util.json.JsonParserException: line 2096 column 51 Expected , or } but found :
        at jdk.graal.compiler/jdk.graal.compiler.util.json.JsonParser.error(JsonParser.java:535)
        at jdk.graal.compiler/jdk.graal.compiler.util.json.JsonParser.expectedError(JsonParser.java:555)
        at jdk.graal.compiler/jdk.graal.compiler.util.json.JsonParser.parseObject(JsonParser.java:293)
        at jdk.graal.compiler/jdk.graal.compiler.util.json.JsonParser.parseLiteral(JsonParser.java:233)
        at jdk.graal.compiler/jdk.graal.compiler.util.json.JsonParser.parseObject(JsonParser.java:274)
        at jdk.graal.compiler/jdk.graal.compiler.util.json.JsonParser.parseLiteral(JsonParser.java:233)
        at jdk.graal.compiler/jdk.graal.compiler.util.json.JsonParser.parseArray(JsonParser.java:337)
        at jdk.graal.compiler/jdk.graal.compiler.util.json.JsonParser.parseLiteral(JsonParser.java:235)
        at jdk.graal.compiler/jdk.graal.compiler.util.json.JsonParser.parseObject(JsonParser.java:274)
        at jdk.graal.compiler/jdk.graal.compiler.util.json.JsonParser.parseLiteral(JsonParser.java:233)
        at jdk.graal.compiler/jdk.graal.compiler.util.json.JsonParser.parseArray(JsonParser.java:337)
        at jdk.graal.compiler/jdk.graal.compiler.util.json.JsonParser.parseLiteral(JsonParser.java:235)
        at jdk.graal.compiler/jdk.graal.compiler.util.json.JsonParser.parseObject(JsonParser.java:274)
        at jdk.graal.compiler/jdk.graal.compiler.util.json.JsonParser.parseLiteral(JsonParser.java:233)
        at jdk.graal.compiler/jdk.graal.compiler.util.json.JsonParser.parseArray(JsonParser.java:337)
        at jdk.graal.compiler/jdk.graal.compiler.util.json.JsonParser.parseLiteral(JsonParser.java:235)
        at jdk.graal.compiler/jdk.graal.compiler.util.json.JsonParser.parseObject(JsonParser.java:274)
        at jdk.graal.compiler/jdk.graal.compiler.util.json.JsonParser.parseLiteral(JsonParser.java:233)
        at jdk.graal.compiler/jdk.graal.compiler.util.json.JsonParser.parseArray(JsonParser.java:337)
        at jdk.graal.compiler/jdk.graal.compiler.util.json.JsonParser.parseLiteral(JsonParser.java:235)
        at jdk.graal.compiler/jdk.graal.compiler.util.json.JsonParser.parseObject(JsonParser.java:274)
        at jdk.graal.compiler/jdk.graal.compiler.util.json.JsonParser.parseLiteral(JsonParser.java:233)
        at jdk.graal.compiler/jdk.graal.compiler.util.json.JsonParser.parseArray(JsonParser.java:337)
        at jdk.graal.compiler/jdk.graal.compiler.util.json.JsonParser.parseLiteral(JsonParser.java:235)
        at jdk.graal.compiler/jdk.graal.compiler.util.json.JsonParser.parseObject(JsonParser.java:274)
        at jdk.graal.compiler/jdk.graal.compiler.util.json.JsonParser.parseLiteral(JsonParser.java:233)
        at jdk.graal.compiler/jdk.graal.compiler.util.json.JsonParser.parseArray(JsonParser.java:337)
        at jdk.graal.compiler/jdk.graal.compiler.util.json.JsonParser.parseLiteral(JsonParser.java:235)
        at jdk.graal.compiler/jdk.graal.compiler.util.json.JsonParser.parseObject(JsonParser.java:274)
        at jdk.graal.compiler/jdk.graal.compiler.util.json.JsonParser.parseLiteral(JsonParser.java:233)
        at jdk.graal.compiler/jdk.graal.compiler.util.json.JsonParser.parseArray(JsonParser.java:337)
        at jdk.graal.compiler/jdk.graal.compiler.util.json.JsonParser.parseLiteral(JsonParser.java:235)
        at jdk.graal.compiler/jdk.graal.compiler.util.json.JsonParser.parseObject(JsonParser.java:274)
        at jdk.graal.compiler/jdk.graal.compiler.util.json.JsonParser.parseLiteral(JsonParser.java:233)
        at jdk.graal.compiler/jdk.graal.compiler.util.json.JsonParser.parseArray(JsonParser.java:337)
        at jdk.graal.compiler/jdk.graal.compiler.util.json.JsonParser.parseLiteral(JsonParser.java:235)
        at jdk.graal.compiler/jdk.graal.compiler.util.json.JsonParser.parseObject(JsonParser.java:274)
        at jdk.graal.compiler/jdk.graal.compiler.util.json.JsonParser.parseLiteral(JsonParser.java:233)
        at jdk.graal.compiler/jdk.graal.compiler.util.json.JsonParser.parseArray(JsonParser.java:337)
        at jdk.graal.compiler/jdk.graal.compiler.util.json.JsonParser.parseLiteral(JsonParser.java:235)
        at jdk.graal.compiler/jdk.graal.compiler.util.json.JsonParser.parseObject(JsonParser.java:274)
        at jdk.graal.compiler/jdk.graal.compiler.util.json.JsonParser.parseLiteral(JsonParser.java:233)
        at jdk.graal.compiler/jdk.graal.compiler.util.json.JsonParser.parseArray(JsonParser.java:337)
        at jdk.graal.compiler/jdk.graal.compiler.util.json.JsonParser.parseLiteral(JsonParser.java:235)
        at jdk.graal.compiler/jdk.graal.compiler.util.json.JsonParser.parseObject(JsonParser.java:274)
        at jdk.graal.compiler/jdk.graal.compiler.util.json.JsonParser.parseLiteral(JsonParser.java:233)
        at jdk.graal.compiler/jdk.graal.compiler.util.json.JsonParser.parseArray(JsonParser.java:337)
        at jdk.graal.compiler/jdk.graal.compiler.util.json.JsonParser.parseLiteral(JsonParser.java:235)
        at jdk.graal.compiler/jdk.graal.compiler.util.json.JsonParser.parseObject(JsonParser.java:274)
        at jdk.graal.compiler/jdk.graal.compiler.util.json.JsonParser.parseLiteral(JsonParser.java:233)
        at jdk.graal.compiler/jdk.graal.compiler.util.json.JsonParser.parseObject(JsonParser.java:274)
        at jdk.graal.compiler/jdk.graal.compiler.util.json.JsonParser.parseLiteral(JsonParser.java:233)
        at jdk.graal.compiler/jdk.graal.compiler.util.json.JsonParser.parse(JsonParser.java:127)
        at org.graalvm.nativeimage.builder/com.oracle.svm.core.configure.ConfigurationParser.parseAndRegister(ConfigurationParser.java:90)
        at org.graalvm.nativeimage.configure/com.oracle.svm.configure.command.ConfigurationGenerateConditionalsCommand.apply(ConfigurationGenerateConditionalsCommand.java:119)
        at org.graalvm.nativeimage.configure/com.oracle.svm.configure.ConfigurationTool.main(ConfigurationTool.java:84)
[INFO] ------------------------------------------------------------------------
[INFO] BUILD FAILURE
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  2.245 s (Wall Clock)
[INFO] Finished at: 2024-10-20T22:37:36+08:00
[INFO] ------------------------------------------------------------------------
[ERROR] Failed to execute goal org.graalvm.buildtools:native-maven-plugin:0.10.3:merge-agent-files (test-native) on project graalvm-v2301-json-test: Execution of /home/linghengqian/.sdkman/candidates/java/23.0.1-graalce/bin/native-image-configure generate-conditional --user-code-filter=/home/linghengqian/TwinklingLiftWorks/git/public/graalvm-v2301-json-test/user-code-filter.json --class-name-filter=/home/linghengqian/TwinklingLiftWorks/git/public/graalvm-v2301-json-test/extra-filter.json --input-dir=/home/linghengqian/TwinklingLiftWorks/git/public/graalvm-v2301-json-test/target/native/agent-output/test/session-147422-20241020T143735Z --output-dir=/home/linghengqian/TwinklingLiftWorks/git/public/graalvm-v2301-json-test/target/native/agent-output/test returned non-zero result -> [Help 1]
org.apache.maven.lifecycle.LifecycleExecutionException: Failed to execute goal org.graalvm.buildtools:native-maven-plugin:0.10.3:merge-agent-files (test-native) on project graalvm-v2301-json-test: Execution of /home/linghengqian/.sdkman/candidates/java/23.0.1-graalce/bin/native-image-configure generate-conditional --user-code-filter=/home/linghengqian/TwinklingLiftWorks/git/public/graalvm-v2301-json-test/user-code-filter.json --class-name-filter=/home/linghengqian/TwinklingLiftWorks/git/public/graalvm-v2301-json-test/extra-filter.json --input-dir=/home/linghengqian/TwinklingLiftWorks/git/public/graalvm-v2301-json-test/target/native/agent-output/test/session-147422-20241020T143735Z --output-dir=/home/linghengqian/TwinklingLiftWorks/git/public/graalvm-v2301-json-test/target/native/agent-output/test returned non-zero result
    at org.apache.maven.lifecycle.internal.MojoExecutor.doExecute2 (MojoExecutor.java:333)
    at org.apache.maven.lifecycle.internal.MojoExecutor.doExecute (MojoExecutor.java:316)
    at org.apache.maven.lifecycle.internal.MojoExecutor.execute (MojoExecutor.java:212)
    at org.apache.maven.lifecycle.internal.MojoExecutor.execute (MojoExecutor.java:174)
    at org.apache.maven.lifecycle.internal.MojoExecutor.access$000 (MojoExecutor.java:75)
    at org.apache.maven.lifecycle.internal.MojoExecutor$1.run (MojoExecutor.java:162)
    at org.apache.maven.plugin.DefaultMojosExecutionStrategy.execute (DefaultMojosExecutionStrategy.java:39)
    at org.apache.maven.lifecycle.internal.MojoExecutor.execute (MojoExecutor.java:159)
    at org.apache.maven.lifecycle.internal.LifecycleModuleBuilder.buildProject (LifecycleModuleBuilder.java:105)
    at org.apache.maven.lifecycle.internal.builder.multithreaded.MultiThreadedBuilder$1.call (MultiThreadedBuilder.java:193)
    at org.apache.maven.lifecycle.internal.builder.multithreaded.MultiThreadedBuilder$1.call (MultiThreadedBuilder.java:180)
    at java.util.concurrent.FutureTask.run (FutureTask.java:317)
    at java.util.concurrent.Executors$RunnableAdapter.call (Executors.java:572)
    at java.util.concurrent.FutureTask.run (FutureTask.java:317)
    at java.util.concurrent.ThreadPoolExecutor.runWorker (ThreadPoolExecutor.java:1144)
    at java.util.concurrent.ThreadPoolExecutor$Worker.run (ThreadPoolExecutor.java:642)
    at java.lang.Thread.run (Thread.java:1575)
Caused by: org.apache.maven.plugin.MojoExecutionException: Execution of /home/linghengqian/.sdkman/candidates/java/23.0.1-graalce/bin/native-image-configure generate-conditional --user-code-filter=/home/linghengqian/TwinklingLiftWorks/git/public/graalvm-v2301-json-test/user-code-filter.json --class-name-filter=/home/linghengqian/TwinklingLiftWorks/git/public/graalvm-v2301-json-test/extra-filter.json --input-dir=/home/linghengqian/TwinklingLiftWorks/git/public/graalvm-v2301-json-test/target/native/agent-output/test/session-147422-20241020T143735Z --output-dir=/home/linghengqian/TwinklingLiftWorks/git/public/graalvm-v2301-json-test/target/native/agent-output/test returned non-zero result
    at org.graalvm.buildtools.maven.MergeAgentFilesMojo.invokeMerge (MergeAgentFilesMojo.java:153)
    at org.graalvm.buildtools.maven.MergeAgentFilesMojo.mergeForGivenDir (MergeAgentFilesMojo.java:122)
    at org.graalvm.buildtools.maven.MergeAgentFilesMojo.execute (MergeAgentFilesMojo.java:110)
    at org.apache.maven.plugin.DefaultBuildPluginManager.executeMojo (DefaultBuildPluginManager.java:126)
    at org.apache.maven.lifecycle.internal.MojoExecutor.doExecute2 (MojoExecutor.java:328)
    at org.apache.maven.lifecycle.internal.MojoExecutor.doExecute (MojoExecutor.java:316)
    at org.apache.maven.lifecycle.internal.MojoExecutor.execute (MojoExecutor.java:212)
    at org.apache.maven.lifecycle.internal.MojoExecutor.execute (MojoExecutor.java:174)
    at org.apache.maven.lifecycle.internal.MojoExecutor.access$000 (MojoExecutor.java:75)
    at org.apache.maven.lifecycle.internal.MojoExecutor$1.run (MojoExecutor.java:162)
    at org.apache.maven.plugin.DefaultMojosExecutionStrategy.execute (DefaultMojosExecutionStrategy.java:39)
    at org.apache.maven.lifecycle.internal.MojoExecutor.execute (MojoExecutor.java:159)
    at org.apache.maven.lifecycle.internal.LifecycleModuleBuilder.buildProject (LifecycleModuleBuilder.java:105)
    at org.apache.maven.lifecycle.internal.builder.multithreaded.MultiThreadedBuilder$1.call (MultiThreadedBuilder.java:193)
    at org.apache.maven.lifecycle.internal.builder.multithreaded.MultiThreadedBuilder$1.call (MultiThreadedBuilder.java:180)
    at java.util.concurrent.FutureTask.run (FutureTask.java:317)
    at java.util.concurrent.Executors$RunnableAdapter.call (Executors.java:572)
    at java.util.concurrent.FutureTask.run (FutureTask.java:317)
    at java.util.concurrent.ThreadPoolExecutor.runWorker (ThreadPoolExecutor.java:1144)
    at java.util.concurrent.ThreadPoolExecutor$Worker.run (ThreadPoolExecutor.java:642)
    at java.lang.Thread.run (Thread.java:1575)
[ERROR] 
[ERROR] Re-run Maven using the -X switch to enable full debug logging.
[ERROR] 
[ERROR] For more information about the errors and possible solutions, please read the following articles:
[ERROR] [Help 1] http://cwiki.apache.org/confluence/display/MAVEN/MojoExecutionException
```