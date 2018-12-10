This is what I have:

    # arnaud at MacBook-Air in ~/Lab/foobar on git:master ● [13:51:23]
    λ tree ~/.m2/repository/com/datomic
    /Users/arnaud/.m2/repository/com/datomic
    ├── client-api
    │   └── 0.8.7
    │       ├── _maven.repositories
    │       ├── client-api-0.8.7.jar
    │       ├── client-api-0.8.7.jar.sha1
    │       ├── client-api-0.8.7.pom
    │       └── client-api-0.8.7.pom.sha1
    ├── datomic-lucene-core
    │   └── 3.3.0
    │       ├── _maven.repositories
    │       ├── datomic-lucene-core-3.3.0.jar
    │       ├── datomic-lucene-core-3.3.0.jar.sha1
    │       ├── datomic-lucene-core-3.3.0.pom
    │       └── datomic-lucene-core-3.3.0.pom.sha1
    └── datomic-pro
        └── 0.9.5786
            ├── _maven.repositories
            ├── datomic-pro-0.9.5786.jar
            ├── datomic-pro-0.9.5786.jar.sha1
            ├── datomic-pro-0.9.5786.pom
            └── datomic-pro-0.9.5786.pom.sha1
    
    6 directories, 15 files

This is what I do:

    # arnaud at MacBook-Air in ~/Lab/foobar on git:master ✖︎ [13:44:49]
    λ clj -Adev --repl

This is what I get:

    Exception in thread "main" java.lang.ExceptionInInitializerError
        at clojure.main.<clinit>(main.java:20)
    Caused by: java.lang.IllegalArgumentException: Unable to load client, make sure com.datomic/client is on your classpath, compiling:(user.clj:10:13)
        at clojure.lang.Compiler$InvokeExpr.eval(Compiler.java:3700)
        at clojure.lang.Compiler$DefExpr.eval(Compiler.java:457)
        at clojure.lang.Compiler.eval(Compiler.java:7067)
        at clojure.lang.Compiler.load(Compiler.java:7514)
        at clojure.lang.RT.loadResourceScript(RT.java:379)
        at clojure.lang.RT.loadResourceScript(RT.java:366)
        at clojure.lang.RT.maybeLoadResourceScript(RT.java:362)
        at clojure.lang.RT.doInit(RT.java:482)
        at clojure.lang.RT.<clinit>(RT.java:336)
        ... 1 more
    Caused by: java.lang.IllegalArgumentException: Unable to load client, make sure com.datomic/client is on your classpath
        at datomic.client.api.impl$dynaload.invokeStatic(impl.clj:13)
        at datomic.client.api.impl$dynaload.invoke(impl.clj:7)
        at datomic.client.api.impl$dynacall.invokeStatic(impl.clj:25)
        at datomic.client.api.impl$dynacall.invoke(impl.clj:23)
        at datomic.client.api$client.invokeStatic(api.clj:79)
        at datomic.client.api$client.invoke(api.clj:45)
        at clojure.lang.AFn.applyToHelper(AFn.java:154)
        at clojure.lang.AFn.applyTo(AFn.java:144)
        at clojure.lang.Compiler$InvokeExpr.eval(Compiler.java:3695)
        ... 9 more
    Caused by: java.io.FileNotFoundException: Could not locate datomic/client/api/sync__init.class or datomic/client/api/sync.clj on classpath.
        at clojure.lang.RT.load(RT.java:463)
        at clojure.lang.RT.load(RT.java:426)
        at clojure.core$load$fn__6548.invoke(core.clj:6046)
        at clojure.core$load.invokeStatic(core.clj:6045)
        at clojure.core$load.doInvoke(core.clj:6029)
        at clojure.lang.RestFn.invoke(RestFn.java:408)
        at clojure.core$load_one.invokeStatic(core.clj:5848)
        at clojure.core$load_one.invoke(core.clj:5843)
        at clojure.core$load_lib$fn__6493.invoke(core.clj:5888)
        at clojure.core$load_lib.invokeStatic(core.clj:5887)
        at clojure.core$load_lib.doInvoke(core.clj:5868)
        at clojure.lang.RestFn.applyTo(RestFn.java:142)
        at clojure.core$apply.invokeStatic(core.clj:659)
        at clojure.core$load_libs.invokeStatic(core.clj:5925)
        at clojure.core$load_libs.doInvoke(core.clj:5909)
        at clojure.lang.RestFn.applyTo(RestFn.java:137)
        at clojure.core$apply.invokeStatic(core.clj:659)
        at clojure.core$require.invokeStatic(core.clj:5947)
        at clojure.core$require.doInvoke(core.clj:5947)
        at clojure.lang.RestFn.invoke(RestFn.java:408)
        at datomic.client.api.impl$dynaload.invokeStatic(impl.clj:10)
        ... 17 more
