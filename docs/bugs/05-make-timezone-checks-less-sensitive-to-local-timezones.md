Link: https://github.com/mwinteringham/restful-booker-platform/issues/50

Summary: Make timezone checks less sensitive to local timezones
Status: Closed
Reopened with: https://github.com/mwinteringham/restful-booker-platform/issues/102

Environment:

OS: Mac OSX Mojave
JVM: Java 8
Node: 8.14.0
JVM_HOME: Set

I tried running the tests two different ways.
1.) Via run_locally.sh
2.) Via mvn clean test

Expected Results:
Tests Pass and I can deploy the application

Actual Results:

This is the log when running with -X flag.

```
[INFO]
[INFO] Results:
[INFO]
[ERROR] Errors:
[ERROR]   BuildReportTest.testGettingBookingsSearchResults:49 »  Failed Approval
  Appro...
[INFO]
[ERROR] Tests run: 3, Failures: 0, Errors: 1, Skipped: 0
[INFO]
[INFO] ------------------------------------------------------------------------
[INFO] Reactor Summary for restful-booker-platform 1.0-SNAPSHOT:
[INFO]
[INFO] restful-booker-platform-auth ....................... SUCCESS [01:39 min]
[INFO] restful-booker-platform-booking .................... SUCCESS [ 34.396 s]
[INFO] restful-booker-platform-room ....................... SUCCESS [01:03 min]
[INFO] restful-booker-platform-search ..................... SUCCESS [  0.842 s]
[INFO] restful-booker-platform-report ..................... FAILURE [  4.139 s]
[INFO] restful-booker-platform-ui ......................... SKIPPED
[INFO] restful-booker-platform ............................ SKIPPED
[INFO] ------------------------------------------------------------------------
[INFO] BUILD FAILURE
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  03:22 min
[INFO] Finished at: 2018-12-13T15:42:37-05:00
[INFO] ------------------------------------------------------------------------
[ERROR] Failed to execute goal org.apache.maven.plugins:maven-surefire-plugin:2.22.0:test (default-test) on project restful-booker-platform-report: There are test failures.
[ERROR]
[ERROR] Please refer to /Users/silne30/Desktop/selenium-article/restful-booker-platform/report/target/surefire-reports for the individual test results.
[ERROR] Please refer to dump files (if any exist) [date]-jvmRun[N].dump, [date].dumpstream and [date]-jvmRun[N].dumpstream.
[ERROR] -> [Help 1]
org.apache.maven.lifecycle.LifecycleExecutionException: Failed to execute goal org.apache.maven.plugins:maven-surefire-plugin:2.22.0:test (default-test) on project restful-booker-platform-report: There are test failures.

Please refer to /Users/silne30/Desktop/selenium-article/restful-booker-platform/report/target/surefire-reports for the individual test results.
Please refer to dump files (if any exist) [date]-jvmRun[N].dump, [date].dumpstream and [date]-jvmRun[N].dumpstream.
    at org.apache.maven.lifecycle.internal.MojoExecutor.execute (MojoExecutor.java:215)
    at org.apache.maven.lifecycle.internal.MojoExecutor.execute (MojoExecutor.java:156)
    at org.apache.maven.lifecycle.internal.MojoExecutor.execute (MojoExecutor.java:148)
    at org.apache.maven.lifecycle.internal.LifecycleModuleBuilder.buildProject (LifecycleModuleBuilder.java:117)
    at org.apache.maven.lifecycle.internal.LifecycleModuleBuilder.buildProject (LifecycleModuleBuilder.java:81)
    at org.apache.maven.lifecycle.internal.builder.singlethreaded.SingleThreadedBuilder.build (SingleThreadedBuilder.java:56)
    at org.apache.maven.lifecycle.internal.LifecycleStarter.execute (LifecycleStarter.java:128)
    at org.apache.maven.DefaultMaven.doExecute (DefaultMaven.java:305)
    at org.apache.maven.DefaultMaven.doExecute (DefaultMaven.java:192)
    at org.apache.maven.DefaultMaven.execute (DefaultMaven.java:105)
    at org.apache.maven.cli.MavenCli.execute (MavenCli.java:956)
    at org.apache.maven.cli.MavenCli.doMain (MavenCli.java:288)
    at org.apache.maven.cli.MavenCli.main (MavenCli.java:192)
    at sun.reflect.NativeMethodAccessorImpl.invoke0 (Native Method)
    at sun.reflect.NativeMethodAccessorImpl.invoke (NativeMethodAccessorImpl.java:62)
    at sun.reflect.DelegatingMethodAccessorImpl.invoke (DelegatingMethodAccessorImpl.java:43)
    at java.lang.reflect.Method.invoke (Method.java:498)
    at org.codehaus.plexus.classworlds.launcher.Launcher.launchEnhanced (Launcher.java:289)
    at org.codehaus.plexus.classworlds.launcher.Launcher.launch (Launcher.java:229)
    at org.codehaus.plexus.classworlds.launcher.Launcher.mainWithExitCode (Launcher.java:415)
    at org.codehaus.plexus.classworlds.launcher.Launcher.main (Launcher.java:356)
Caused by: org.apache.maven.plugin.MojoFailureException: There are test failures.

Please refer to /Users/silne30/Desktop/selenium-article/restful-booker-platform/report/target/surefire-reports for the individual test results.
Please refer to dump files (if any exist) [date]-jvmRun[N].dump, [date].dumpstream and [date]-jvmRun[N].dumpstream.
    at org.apache.maven.plugin.surefire.SurefireHelper.throwException (SurefireHelper.java:240)
    at org.apache.maven.plugin.surefire.SurefireHelper.reportExecution (SurefireHelper.java:112)
    at org.apache.maven.plugin.surefire.SurefirePlugin.handleSummary (SurefirePlugin.java:364)
    at org.apache.maven.plugin.surefire.AbstractSurefireMojo.executeAfterPreconditionsChecked (AbstractSurefireMojo.java:1052)
    at org.apache.maven.plugin.surefire.AbstractSurefireMojo.execute (AbstractSurefireMojo.java:868)
    at org.apache.maven.plugin.DefaultBuildPluginManager.executeMojo (DefaultBuildPluginManager.java:137)
    at org.apache.maven.lifecycle.internal.MojoExecutor.execute (MojoExecutor.java:210)
    at org.apache.maven.lifecycle.internal.MojoExecutor.execute (MojoExecutor.java:156)
    at org.apache.maven.lifecycle.internal.MojoExecutor.execute (MojoExecutor.java:148)
    at org.apache.maven.lifecycle.internal.LifecycleModuleBuilder.buildProject (LifecycleModuleBuilder.java:117)
    at org.apache.maven.lifecycle.internal.LifecycleModuleBuilder.buildProject (LifecycleModuleBuilder.java:81)
    at org.apache.maven.lifecycle.internal.builder.singlethreaded.SingleThreadedBuilder.build (SingleThreadedBuilder.java:56)
    at org.apache.maven.lifecycle.internal.LifecycleStarter.execute (LifecycleStarter.java:128)
    at org.apache.maven.DefaultMaven.doExecute (DefaultMaven.java:305)
    at org.apache.maven.DefaultMaven.doExecute (DefaultMaven.java:192)
    at org.apache.maven.DefaultMaven.execute (DefaultMaven.java:105)
    at org.apache.maven.cli.MavenCli.execute (MavenCli.java:956)
    at org.apache.maven.cli.MavenCli.doMain (MavenCli.java:288)
    at org.apache.maven.cli.MavenCli.main (MavenCli.java:192)
    at sun.reflect.NativeMethodAccessorImpl.invoke0 (Native Method)
    at sun.reflect.NativeMethodAccessorImpl.invoke (NativeMethodAccessorImpl.java:62)
    at sun.reflect.DelegatingMethodAccessorImpl.invoke (DelegatingMethodAccessorImpl.java:43)
    at java.lang.reflect.Method.invoke (Method.java:498)
    at org.codehaus.plexus.classworlds.launcher.Launcher.launchEnhanced (Launcher.java:289)
    at org.codehaus.plexus.classworlds.launcher.Launcher.launch (Launcher.java:229)
    at org.codehaus.plexus.classworlds.launcher.Launcher.mainWithExitCode (Launcher.java:415)
    at org.codehaus.plexus.classworlds.launcher.Launcher.main (Launcher.java:356)
[ERROR]
[ERROR]
[ERROR] For more information about the errors and possible solutions, please read the following articles:
[ERROR] [Help 1] http://cwiki.apache.org/confluence/display/MAVEN/MojoFailureException
[ERROR]
[ERROR] After correcting the problems, you can resume the build with the command
```






