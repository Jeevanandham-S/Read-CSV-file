22:03:19,658 |-INFO in ch.qos.logback.classic.LoggerContext[default] - This is logback-classic version 1.5.8
22:03:19,662 |-INFO in ch.qos.logback.classic.util.ContextInitializer@51549490 - Here is a list of configurators discovered as a service, by rank: 
22:03:19,662 |-INFO in ch.qos.logback.classic.util.ContextInitializer@51549490 -   org.springframework.boot.logging.logback.RootLogLevelConfigurator
22:03:19,662 |-INFO in ch.qos.logback.classic.util.ContextInitializer@51549490 - They will be invoked in order until ExecutionStatus.DO_NOT_INVOKE_NEXT_IF_ANY is returned.
22:03:19,662 |-INFO in ch.qos.logback.classic.util.ContextInitializer@51549490 - Constructed configurator of type class org.springframework.boot.logging.logback.RootLogLevelConfigurator
22:03:19,668 |-INFO in ch.qos.logback.classic.util.ContextInitializer@51549490 - org.springframework.boot.logging.logback.RootLogLevelConfigurator.configure() call lasted 1 milliseconds. ExecutionStatus=INVOKE_NEXT_IF_ANY
22:03:19,668 |-INFO in ch.qos.logback.classic.util.ContextInitializer@51549490 - Trying to configure with ch.qos.logback.classic.joran.SerializedModelConfigurator
22:03:19,670 |-INFO in ch.qos.logback.classic.util.ContextInitializer@51549490 - Constructed configurator of type class ch.qos.logback.classic.joran.SerializedModelConfigurator
22:03:19,670 |-INFO in ch.qos.logback.classic.LoggerContext[default] - Could NOT find resource [logback-test.scmo]
22:03:19,671 |-INFO in ch.qos.logback.classic.LoggerContext[default] - Could NOT find resource [logback.scmo]
22:03:19,671 |-INFO in ch.qos.logback.classic.util.ContextInitializer@51549490 - ch.qos.logback.classic.joran.SerializedModelConfigurator.configure() call lasted 1 milliseconds. ExecutionStatus=INVOKE_NEXT_IF_ANY
22:03:19,671 |-INFO in ch.qos.logback.classic.util.ContextInitializer@51549490 - Trying to configure with ch.qos.logback.classic.util.DefaultJoranConfigurator
22:03:19,672 |-INFO in ch.qos.logback.classic.util.ContextInitializer@51549490 - Constructed configurator of type class ch.qos.logback.classic.util.DefaultJoranConfigurator
22:03:19,672 |-INFO in ch.qos.logback.classic.LoggerContext[default] - Could NOT find resource [logback-test.xml]
22:03:19,672 |-INFO in ch.qos.logback.classic.LoggerContext[default] - Found resource [logback.xml] at [file:/C:/Users/sje6dbg/vbuild-repos/oneaccesspar/bin/main/logback.xml]
22:03:19,802 |-INFO in ch.qos.logback.core.model.processor.AppenderModelHandler - Processing appender named [STDOUT]
22:03:19,802 |-INFO in ch.qos.logback.core.model.processor.AppenderModelHandler - About to instantiate appender of type [ch.qos.logback.core.ConsoleAppender]
22:03:19,809 |-INFO in ch.qos.logback.core.model.processor.ImplicitModelHandler - Assuming default type [ch.qos.logback.classic.encoder.PatternLayoutEncoder] for [encoder] property
22:03:19,851 |-INFO in ch.qos.logback.core.model.processor.AppenderModelHandler - Processing appender named [FILE]
22:03:19,851 |-INFO in ch.qos.logback.core.model.processor.AppenderModelHandler - About to instantiate appender of type [ch.qos.logback.core.rolling.RollingFileAppender]
22:03:19,859 |-INFO in c.q.l.core.rolling.TimeBasedRollingPolicy@1911155630 - setting totalSizeCap to 100 MB
22:03:19,860 |-ERROR in ch.qos.logback.core.model.processor.ImplicitModelHandler - Could not create component [timeBasedFileNamingAndTriggeringPolicy] of type [ch.qos.logback.core.rolling.SizeAndTimeBasedFNATP] java.lang.ClassNotFoundException: ch.qos.logback.core.rolling.SizeAndTimeBasedFNATP
	at java.lang.ClassNotFoundException: ch.qos.logback.core.rolling.SizeAndTimeBasedFNATP
	at 	at java.base/jdk.internal.loader.BuiltinClassLoader.loadClass(BuiltinClassLoader.java:641)
	at 	at java.base/jdk.internal.loader.ClassLoaders$AppClassLoader.loadClass(ClassLoaders.java:188)
	at 	at java.base/java.lang.ClassLoader.loadClass(ClassLoader.java:525)
	at 	at ch.qos.logback.core.util.Loader.loadClass(Loader.java:132)
	at 	at ch.qos.logback.core.model.processor.ImplicitModelHandler.doComplex(ImplicitModelHandler.java:134)
	at 	at ch.qos.logback.core.model.processor.ImplicitModelHandler.handle(ImplicitModelHandler.java:94)
	at 	at ch.qos.logback.core.model.processor.DefaultProcessor.secondPhaseTraverse(DefaultProcessor.java:241)
	at 	at ch.qos.logback.core.model.processor.DefaultProcessor.secondPhaseTraverse(DefaultProcessor.java:253)
	at 	at ch.qos.logback.core.model.processor.DefaultProcessor.secondPhaseTraverse(DefaultProcessor.java:253)
	at 	at ch.qos.logback.core.model.processor.DefaultProcessor.secondPhaseTraverse(DefaultProcessor.java:253)
	at 	at ch.qos.logback.core.model.processor.DefaultProcessor.traversalLoop(DefaultProcessor.java:90)
	at 	at ch.qos.logback.core.model.processor.DefaultProcessor.process(DefaultProcessor.java:106)
	at 	at ch.qos.logback.core.joran.GenericXMLConfigurator.processModel(GenericXMLConfigurator.java:222)
	at 	at ch.qos.logback.core.joran.GenericXMLConfigurator.doConfigure(GenericXMLConfigurator.java:178)
	at 	at ch.qos.logback.core.joran.GenericXMLConfigurator.doConfigure(GenericXMLConfigurator.java:123)
	at 	at ch.qos.logback.core.joran.GenericXMLConfigurator.doConfigure(GenericXMLConfigurator.java:66)
	at 	at ch.qos.logback.classic.util.DefaultJoranConfigurator.configureByResource(DefaultJoranConfigurator.java:68)
	at 	at ch.qos.logback.classic.util.DefaultJoranConfigurator.configure(DefaultJoranConfigurator.java:35)
	at 	at ch.qos.logback.classic.util.ContextInitializer.invokeConfigure(ContextInitializer.java:128)
	at 	at ch.qos.logback.classic.util.ContextInitializer.autoConfig(ContextInitializer.java:103)
	at 	at ch.qos.logback.classic.util.ContextInitializer.autoConfig(ContextInitializer.java:66)
	at 	at ch.qos.logback.classic.spi.LogbackServiceProvider.initializeLoggerContext(LogbackServiceProvider.java:52)
	at 	at ch.qos.logback.classic.spi.LogbackServiceProvider.initialize(LogbackServiceProvider.java:41)
	at 	at org.slf4j.LoggerFactory.bind(LoggerFactory.java:199)
	at 	at org.slf4j.LoggerFactory.performInitialization(LoggerFactory.java:186)
	at 	at org.slf4j.LoggerFactory.getProvider(LoggerFactory.java:496)
	at 	at org.slf4j.LoggerFactory.getILoggerFactory(LoggerFactory.java:482)
	at 	at org.slf4j.LoggerFactory.getLogger(LoggerFactory.java:431)
	at 	at org.slf4j.LoggerFactory.getLogger(LoggerFactory.java:457)
	at 	at com.verizon.oneaccess.par.ParApplication.<clinit>(ParApplication.java:42)
22:03:19,862 |-WARN in ch.qos.logback.core.model.processor.ImplicitModelHandler - Ignoring unknown property [maxFileSize] in [ch.qos.logback.core.rolling.TimeBasedRollingPolicy]
22:03:19,865 |-INFO in c.q.l.core.rolling.TimeBasedRollingPolicy@1911155630 - No compression will be used
22:03:19,866 |-INFO in c.q.l.core.rolling.TimeBasedRollingPolicy@1911155630 - Will use the pattern /tmp/oneAccess_par.%d{yyyy-MM-dd}.%i.log for the active file
22:03:19,896 |-INFO in c.q.l.core.rolling.DefaultTimeBasedFileNamingAndTriggeringPolicy - The date pattern is 'yyyy-MM-dd' from file name pattern '/tmp/oneAccess_par.%d{yyyy-MM-dd}.%i.log'.
22:03:19,896 |-INFO in c.q.l.core.rolling.DefaultTimeBasedFileNamingAndTriggeringPolicy - Roll-over at midnight.
22:03:19,908 |-INFO in c.q.l.core.rolling.DefaultTimeBasedFileNamingAndTriggeringPolicy - Setting initial period to 2024-10-17T09:27:28.571Z
22:03:19,909 |-ERROR in c.q.l.core.rolling.DefaultTimeBasedFileNamingAndTriggeringPolicy - Filename pattern [/tmp/oneAccess_par.%d{yyyy-MM-dd}.%i.log] contains an integer token converter, i.e. %i, INCOMPATIBLE with this configuration. Remove it.
22:03:19,909 |-WARN in c.q.l.core.rolling.TimeBasedRollingPolicy@1911155630 - Subcomponent did not start. TimeBasedRollingPolicy will not start.
22:03:19,909 |-WARN in ch.qos.logback.core.rolling.RollingFileAppender[FILE] - TriggeringPolicy has not started. RollingFileAppender will not start
22:03:19,909 |-INFO in ch.qos.logback.classic.model.processor.RootLoggerModelHandler - Setting level of ROOT logger to INFO
22:03:19,909 |-INFO in ch.qos.logback.core.model.processor.AppenderRefModelHandler - Attaching appender named [FILE] to Logger[ROOT]
22:03:19,910 |-INFO in ch.qos.logback.core.model.processor.AppenderRefModelHandler - Attaching appender named [STDOUT] to Logger[ROOT]
22:03:19,910 |-INFO in ch.qos.logback.core.model.processor.DefaultProcessor@7daa0fbd - End of configuration.
22:03:19,911 |-INFO in ch.qos.logback.classic.joran.JoranConfigurator@42530531 - Registering current configuration as safe fallback point
22:03:19,911 |-INFO in ch.qos.logback.classic.util.ContextInitializer@51549490 - ch.qos.logback.classic.util.DefaultJoranConfigurator.configure() call lasted 239 milliseconds. ExecutionStatus=DO_NOT_INVOKE_NEXT_IF_ANY

Logging system failed to initialize using configuration from 'null'
java.lang.IllegalStateException: Logback configuration error detected: 
ERROR in ch.qos.logback.core.model.processor.ImplicitModelHandler - Could not create component [timeBasedFileNamingAndTriggeringPolicy] of type [ch.qos.logback.core.rolling.SizeAndTimeBasedFNATP] java.lang.ClassNotFoundException: ch.qos.logback.core.rolling.SizeAndTimeBasedFNATP
ERROR in c.q.l.core.rolling.DefaultTimeBasedFileNamingAndTriggeringPolicy - Filename pattern [/tmp/oneAccess_par.%d{yyyy-MM-dd}.%i.log] contains an integer token converter, i.e. %i, INCOMPATIBLE with this configuration. Remove it.
	at org.springframework.boot.logging.logback.LogbackLoggingSystem.reportConfigurationErrorsIfNecessary(LogbackLoggingSystem.java:284)
	at org.springframework.boot.logging.logback.LogbackLoggingSystem.loadConfiguration(LogbackLoggingSystem.java:262)
	at org.springframework.boot.logging.logback.LogbackLoggingSystem.reinitialize(LogbackLoggingSystem.java:341)
	at org.springframework.boot.logging.AbstractLoggingSystem.initializeWithConventions(AbstractLoggingSystem.java:74)
	at org.springframework.boot.logging.AbstractLoggingSystem.initialize(AbstractLoggingSystem.java:61)
	at org.springframework.boot.logging.logback.LogbackLoggingSystem.initialize(LogbackLoggingSystem.java:193)
	at org.springframework.boot.context.logging.LoggingApplicationListener.initializeSystem(LoggingApplicationListener.java:332)
	at org.springframework.boot.context.logging.LoggingApplicationListener.initialize(LoggingApplicationListener.java:298)
	at org.springframework.boot.context.logging.LoggingApplicationListener.onApplicationEnvironmentPreparedEvent(LoggingApplicationListener.java:246)
	at org.springframework.boot.context.logging.LoggingApplicationListener.onApplicationEvent(LoggingApplicationListener.java:223)
	at org.springframework.context.event.SimpleApplicationEventMulticaster.doInvokeListener(SimpleApplicationEventMulticaster.java:185)
	at org.springframework.context.event.SimpleApplicationEventMulticaster.invokeListener(SimpleApplicationEventMulticaster.java:178)
	at org.springframework.context.event.SimpleApplicationEventMulticaster.multicastEvent(SimpleApplicationEventMulticaster.java:156)
	at org.springframework.context.event.SimpleApplicationEventMulticaster.multicastEvent(SimpleApplicationEventMulticaster.java:138)
	at org.springframework.boot.context.event.EventPublishingRunListener.multicastInitialEvent(EventPublishingRunListener.java:136)
	at org.springframework.boot.context.event.EventPublishingRunListener.environmentPrepared(EventPublishingRunListener.java:81)
	at org.springframework.boot.SpringApplicationRunListeners.lambda$environmentPrepared$2(SpringApplicationRunListeners.java:64)
	at java.base/java.lang.Iterable.forEach(Iterable.java:75)
	at org.springframework.boot.SpringApplicationRunListeners.doWithListeners(SpringApplicationRunListeners.java:118)
	at org.springframework.boot.SpringApplicationRunListeners.doWithListeners(SpringApplicationRunListeners.java:112)
	at org.springframework.boot.SpringApplicationRunListeners.environmentPrepared(SpringApplicationRunListeners.java:63)
	at org.springframework.boot.SpringApplication.prepareEnvironment(SpringApplication.java:370)
	at org.springframework.boot.SpringApplication.run(SpringApplication.java:330)
	at org.springframework.boot.SpringApplication.run(SpringApplication.java:1363)
	at org.springframework.boot.SpringApplication.run(SpringApplication.java:1352)
	at com.verizon.oneaccess.par.ParApplication.main(ParApplication.java:51)
	Suppressed: java.lang.ClassNotFoundException: ch.qos.logback.core.rolling.SizeAndTimeBasedFNATP
		at java.base/jdk.internal.loader.BuiltinClassLoader.loadClass(BuiltinClassLoader.java:641)
		at java.base/jdk.internal.loader.ClassLoaders$AppClassLoader.loadClass(ClassLoaders.java:188)
		at java.base/java.lang.ClassLoader.loadClass(ClassLoader.java:525)
		at ch.qos.logback.core.util.Loader.loadClass(Loader.java:132)
		at ch.qos.logback.core.model.processor.ImplicitModelHandler.doComplex(ImplicitModelHandler.java:134)
		at ch.qos.logback.core.model.processor.ImplicitModelHandler.handle(ImplicitModelHandler.java:94)
		at ch.qos.logback.core.model.processor.DefaultProcessor.secondPhaseTraverse(DefaultProcessor.java:241)
		at ch.qos.logback.core.model.processor.DefaultProcessor.secondPhaseTraverse(DefaultProcessor.java:253)
		at ch.qos.logback.core.model.processor.DefaultProcessor.secondPhaseTraverse(DefaultProcessor.java:253)
		at ch.qos.logback.core.model.processor.DefaultProcessor.secondPhaseTraverse(DefaultProcessor.java:253)
		at ch.qos.logback.core.model.processor.DefaultProcessor.traversalLoop(DefaultProcessor.java:90)
		at ch.qos.logback.core.model.processor.DefaultProcessor.process(DefaultProcessor.java:106)
		at ch.qos.logback.core.joran.GenericXMLConfigurator.processModel(GenericXMLConfigurator.java:222)
		at org.springframework.boot.logging.logback.SpringBootJoranConfigurator.processModel(SpringBootJoranConfigurator.java:133)
		at ch.qos.logback.core.joran.GenericXMLConfigurator.doConfigure(GenericXMLConfigurator.java:178)
		at ch.qos.logback.core.joran.GenericXMLConfigurator.doConfigure(GenericXMLConfigurator.java:123)
		at ch.qos.logback.core.joran.GenericXMLConfigurator.doConfigure(GenericXMLConfigurator.java:66)
		at org.springframework.boot.logging.logback.LogbackLoggingSystem.configureByResourceUrl(LogbackLoggingSystem.java:294)
		at org.springframework.boot.logging.logback.LogbackLoggingSystem.lambda$loadConfiguration$1(LogbackLoggingSystem.java:255)
		at org.springframework.boot.logging.logback.LogbackLoggingSystem.withLoggingSuppressed(LogbackLoggingSystem.java:474)
		at org.springframework.boot.logging.logback.LogbackLoggingSystem.loadConfiguration(LogbackLoggingSystem.java:249)
		... 24 more
2024-10-21 22:03:20.557 [main] ERROR o.s.boot.SpringApplication : reportFailure(859) - Application run failed
java.lang.IllegalStateException: java.lang.IllegalStateException: Logback configuration error detected: 
ERROR in ch.qos.logback.core.model.processor.ImplicitModelHandler - Could not create component [timeBasedFileNamingAndTriggeringPolicy] of type [ch.qos.logback.core.rolling.SizeAndTimeBasedFNATP] java.lang.ClassNotFoundException: ch.qos.logback.core.rolling.SizeAndTimeBasedFNATP
ERROR in c.q.l.core.rolling.DefaultTimeBasedFileNamingAndTriggeringPolicy - Filename pattern [/tmp/oneAccess_par.%d{yyyy-MM-dd}.%i.log] contains an integer token converter, i.e. %i, INCOMPATIBLE with this configuration. Remove it.
	at org.springframework.boot.context.logging.LoggingApplicationListener.initializeSystem(LoggingApplicationListener.java:347)
	at org.springframework.boot.context.logging.LoggingApplicationListener.initialize(LoggingApplicationListener.java:298)
	at org.springframework.boot.context.logging.LoggingApplicationListener.onApplicationEnvironmentPreparedEvent(LoggingApplicationListener.java:246)
	at org.springframework.boot.context.logging.LoggingApplicationListener.onApplicationEvent(LoggingApplicationListener.java:223)
	at org.springframework.context.event.SimpleApplicationEventMulticaster.doInvokeListener(SimpleApplicationEventMulticaster.java:185)
	at org.springframework.context.event.SimpleApplicationEventMulticaster.invokeListener(SimpleApplicationEventMulticaster.java:178)
	at org.springframework.context.event.SimpleApplicationEventMulticaster.multicastEvent(SimpleApplicationEventMulticaster.java:156)
	at org.springframework.context.event.SimpleApplicationEventMulticaster.multicastEvent(SimpleApplicationEventMulticaster.java:138)
	at org.springframework.boot.context.event.EventPublishingRunListener.multicastInitialEvent(EventPublishingRunListener.java:136)
	at org.springframework.boot.context.event.EventPublishingRunListener.environmentPrepared(EventPublishingRunListener.java:81)
	at org.springframework.boot.SpringApplicationRunListeners.lambda$environmentPrepared$2(SpringApplicationRunListeners.java:64)
	at java.base/java.lang.Iterable.forEach(Iterable.java:75)
	at org.springframework.boot.SpringApplicationRunListeners.doWithListeners(SpringApplicationRunListeners.java:118)
	at org.springframework.boot.SpringApplicationRunListeners.doWithListeners(SpringApplicationRunListeners.java:112)
	at org.springframework.boot.SpringApplicationRunListeners.environmentPrepared(SpringApplicationRunListeners.java:63)
	at org.springframework.boot.SpringApplication.prepareEnvironment(SpringApplication.java:370)
	at org.springframework.boot.SpringApplication.run(SpringApplication.java:330)
	at org.springframework.boot.SpringApplication.run(SpringApplication.java:1363)
	at org.springframework.boot.SpringApplication.run(SpringApplication.java:1352)
	at com.verizon.oneaccess.par.ParApplication.main(ParApplication.java:51)
Caused by: java.lang.IllegalStateException: Logback configuration error detected: 
ERROR in ch.qos.logback.core.model.processor.ImplicitModelHandler - Could not create component [timeBasedFileNamingAndTriggeringPolicy] of type [ch.qos.logback.core.rolling.SizeAndTimeBasedFNATP] java.lang.ClassNotFoundException: ch.qos.logback.core.rolling.SizeAndTimeBasedFNATP
ERROR in c.q.l.core.rolling.DefaultTimeBasedFileNamingAndTriggeringPolicy - Filename pattern [/tmp/oneAccess_par.%d{yyyy-MM-dd}.%i.log] contains an integer token converter, i.e. %i, INCOMPATIBLE with this configuration. Remove it.
	at org.springframework.boot.logging.logback.LogbackLoggingSystem.reportConfigurationErrorsIfNecessary(LogbackLoggingSystem.java:284)
	at org.springframework.boot.logging.logback.LogbackLoggingSystem.loadConfiguration(LogbackLoggingSystem.java:262)
	at org.springframework.boot.logging.logback.LogbackLoggingSystem.reinitialize(LogbackLoggingSystem.java:341)
	at org.springframework.boot.logging.AbstractLoggingSystem.initializeWithConventions(AbstractLoggingSystem.java:74)
	at org.springframework.boot.logging.AbstractLoggingSystem.initialize(AbstractLoggingSystem.java:61)
	at org.springframework.boot.logging.logback.LogbackLoggingSystem.initialize(LogbackLoggingSystem.java:193)
	at org.springframework.boot.context.logging.LoggingApplicationListener.initializeSystem(LoggingApplicationListener.java:332)
	... 19 common frames omitted
	Suppressed: java.lang.ClassNotFoundException: ch.qos.logback.core.rolling.SizeAndTimeBasedFNATP
		at java.base/jdk.internal.loader.BuiltinClassLoader.loadClass(BuiltinClassLoader.java:641)
		at java.base/jdk.internal.loader.ClassLoaders$AppClassLoader.loadClass(ClassLoaders.java:188)
		at java.base/java.lang.ClassLoader.loadClass(ClassLoader.java:525)
		at ch.qos.logback.core.util.Loader.loadClass(Loader.java:132)
		at ch.qos.logback.core.model.processor.ImplicitModelHandler.doComplex(ImplicitModelHandler.java:134)
		at ch.qos.logback.core.model.processor.ImplicitModelHandler.handle(ImplicitModelHandler.java:94)
		at ch.qos.logback.core.model.processor.DefaultProcessor.secondPhaseTraverse(DefaultProcessor.java:241)
		at ch.qos.logback.core.model.processor.DefaultProcessor.secondPhaseTraverse(DefaultProcessor.java:253)
		at ch.qos.logback.core.model.processor.DefaultProcessor.secondPhaseTraverse(DefaultProcessor.java:253)
		at ch.qos.logback.core.model.processor.DefaultProcessor.secondPhaseTraverse(DefaultProcessor.java:253)
		at ch.qos.logback.core.model.processor.DefaultProcessor.traversalLoop(DefaultProcessor.java:90)
		at ch.qos.logback.core.model.processor.DefaultProcessor.process(DefaultProcessor.java:106)
		at ch.qos.logback.core.joran.GenericXMLConfigurator.processModel(GenericXMLConfigurator.java:222)
		at org.springframework.boot.logging.logback.SpringBootJoranConfigurator.processModel(SpringBootJoranConfigurator.java:133)
		at ch.qos.logback.core.joran.GenericXMLConfigurator.doConfigure(GenericXMLConfigurator.java:178)
		at ch.qos.logback.core.joran.GenericXMLConfigurator.doConfigure(GenericXMLConfigurator.java:123)
		at ch.qos.logback.core.joran.GenericXMLConfigurator.doConfigure(GenericXMLConfigurator.java:66)
		at org.springframework.boot.logging.logback.LogbackLoggingSystem.configureByResourceUrl(LogbackLoggingSystem.java:294)
		at org.springframework.boot.logging.logback.LogbackLoggingSystem.lambda$loadConfiguration$1(LogbackLoggingSystem.java:255)
		at org.springframework.boot.logging.logback.LogbackLoggingSystem.withLoggingSuppressed(LogbackLoggingSystem.java:474)
		at org.springframework.boot.logging.logback.LogbackLoggingSystem.loadConfiguration(LogbackLoggingSystem.java:249)
		... 24 common frames omitted
2024-10-21 22:03:20.560 [main] ERROR c.v.oneaccess.par.ParApplication : main(77) - 
java.lang.IllegalStateException: java.lang.IllegalStateException: Logback configuration error detected: 
ERROR in ch.qos.logback.core.model.processor.ImplicitModelHandler - Could not create component [timeBasedFileNamingAndTriggeringPolicy] of type [ch.qos.logback.core.rolling.SizeAndTimeBasedFNATP] java.lang.ClassNotFoundException: ch.qos.logback.core.rolling.SizeAndTimeBasedFNATP
ERROR in c.q.l.core.rolling.DefaultTimeBasedFileNamingAndTriggeringPolicy - Filename pattern [/tmp/oneAccess_par.%d{yyyy-MM-dd}.%i.log] contains an integer token converter, i.e. %i, INCOMPATIBLE with this configuration. Remove it.
	at org.springframework.boot.context.logging.LoggingApplicationListener.initializeSystem(LoggingApplicationListener.java:347)
	at org.springframework.boot.context.logging.LoggingApplicationListener.initialize(LoggingApplicationListener.java:298)
	at org.springframework.boot.context.logging.LoggingApplicationListener.onApplicationEnvironmentPreparedEvent(LoggingApplicationListener.java:246)
	at org.springframework.boot.context.logging.LoggingApplicationListener.onApplicationEvent(LoggingApplicationListener.java:223)
	at org.springframework.context.event.SimpleApplicationEventMulticaster.doInvokeListener(SimpleApplicationEventMulticaster.java:185)
	at org.springframework.context.event.SimpleApplicationEventMulticaster.invokeListener(SimpleApplicationEventMulticaster.java:178)
	at org.springframework.context.event.SimpleApplicationEventMulticaster.multicastEvent(SimpleApplicationEventMulticaster.java:156)
	at org.springframework.context.event.SimpleApplicationEventMulticaster.multicastEvent(SimpleApplicationEventMulticaster.java:138)
	at org.springframework.boot.context.event.EventPublishingRunListener.multicastInitialEvent(EventPublishingRunListener.java:136)
	at org.springframework.boot.context.event.EventPublishingRunListener.environmentPrepared(EventPublishingRunListener.java:81)
	at org.springframework.boot.SpringApplicationRunListeners.lambda$environmentPrepared$2(SpringApplicationRunListeners.java:64)
	at java.base/java.lang.Iterable.forEach(Iterable.java:75)
	at org.springframework.boot.SpringApplicationRunListeners.doWithListeners(SpringApplicationRunListeners.java:118)
	at org.springframework.boot.SpringApplicationRunListeners.doWithListeners(SpringApplicationRunListeners.java:112)
	at org.springframework.boot.SpringApplicationRunListeners.environmentPrepared(SpringApplicationRunListeners.java:63)
	at org.springframework.boot.SpringApplication.prepareEnvironment(SpringApplication.java:370)
	at org.springframework.boot.SpringApplication.run(SpringApplication.java:330)
	at org.springframework.boot.SpringApplication.run(SpringApplication.java:1363)
	at org.springframework.boot.SpringApplication.run(SpringApplication.java:1352)
	at com.verizon.oneaccess.par.ParApplication.main(ParApplication.java:51)
Caused by: java.lang.IllegalStateException: Logback configuration error detected: 
ERROR in ch.qos.logback.core.model.processor.ImplicitModelHandler - Could not create component [timeBasedFileNamingAndTriggeringPolicy] of type [ch.qos.logback.core.rolling.SizeAndTimeBasedFNATP] java.lang.ClassNotFoundException: ch.qos.logback.core.rolling.SizeAndTimeBasedFNATP
ERROR in c.q.l.core.rolling.DefaultTimeBasedFileNamingAndTriggeringPolicy - Filename pattern [/tmp/oneAccess_par.%d{yyyy-MM-dd}.%i.log] contains an integer token converter, i.e. %i, INCOMPATIBLE with this configuration. Remove it.
	at org.springframework.boot.logging.logback.LogbackLoggingSystem.reportConfigurationErrorsIfNecessary(LogbackLoggingSystem.java:284)
	at org.springframework.boot.logging.logback.LogbackLoggingSystem.loadConfiguration(LogbackLoggingSystem.java:262)
	at org.springframework.boot.logging.logback.LogbackLoggingSystem.reinitialize(LogbackLoggingSystem.java:341)
	at org.springframework.boot.logging.AbstractLoggingSystem.initializeWithConventions(AbstractLoggingSystem.java:74)
	at org.springframework.boot.logging.AbstractLoggingSystem.initialize(AbstractLoggingSystem.java:61)
	at org.springframework.boot.logging.logback.LogbackLoggingSystem.initialize(LogbackLoggingSystem.java:193)
	at org.springframework.boot.context.logging.LoggingApplicationListener.initializeSystem(LoggingApplicationListener.java:332)
	... 19 common frames omitted
	Suppressed: java.lang.ClassNotFoundException: ch.qos.logback.core.rolling.SizeAndTimeBasedFNATP
		at java.base/jdk.internal.loader.BuiltinClassLoader.loadClass(BuiltinClassLoader.java:641)
		at java.base/jdk.internal.loader.ClassLoaders$AppClassLoader.loadClass(ClassLoaders.java:188)
		at java.base/java.lang.ClassLoader.loadClass(ClassLoader.java:525)
		at ch.qos.logback.core.util.Loader.loadClass(Loader.java:132)
		at ch.qos.logback.core.model.processor.ImplicitModelHandler.doComplex(ImplicitModelHandler.java:134)
		at ch.qos.logback.core.model.processor.ImplicitModelHandler.handle(ImplicitModelHandler.java:94)
		at ch.qos.logback.core.model.processor.DefaultProcessor.secondPhaseTraverse(DefaultProcessor.java:241)
		at ch.qos.logback.core.model.processor.DefaultProcessor.secondPhaseTraverse(DefaultProcessor.java:253)
		at ch.qos.logback.core.model.processor.DefaultProcessor.secondPhaseTraverse(DefaultProcessor.java:253)
		at ch.qos.logback.core.model.processor.DefaultProcessor.secondPhaseTraverse(DefaultProcessor.java:253)
		at ch.qos.logback.core.model.processor.DefaultProcessor.traversalLoop(DefaultProcessor.java:90)
		at ch.qos.logback.core.model.processor.DefaultProcessor.process(DefaultProcessor.java:106)
		at ch.qos.logback.core.joran.GenericXMLConfigurator.processModel(GenericXMLConfigurator.java:222)
		at org.springframework.boot.logging.logback.SpringBootJoranConfigurator.processModel(SpringBootJoranConfigurator.java:133)
		at ch.qos.logback.core.joran.GenericXMLConfigurator.doConfigure(GenericXMLConfigurator.java:178)
		at ch.qos.logback.core.joran.GenericXMLConfigurator.doConfigure(GenericXMLConfigurator.java:123)
		at ch.qos.logback.core.joran.GenericXMLConfigurator.doConfigure(GenericXMLConfigurator.java:66)
		at org.springframework.boot.logging.logback.LogbackLoggingSystem.configureByResourceUrl(LogbackLoggingSystem.java:294)
		at org.springframework.boot.logging.logback.LogbackLoggingSystem.lambda$loadConfiguration$1(LogbackLoggingSystem.java:255)
		at org.springframework.boot.logging.logback.LogbackLoggingSystem.withLoggingSuppressed(LogbackLoggingSystem.java:474)
		at org.springframework.boot.logging.logback.LogbackLoggingSystem.loadConfiguration(LogbackLoggingSystem.java:249)
		... 24 common frames omitted
