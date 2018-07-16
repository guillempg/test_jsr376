1- Check you're using Java 9+ (java -version)

2- From main folder:

Compile (as module) with:
javac --module-path libs -d mods/com.guillempg.testJSR376 $(find com.guillempg.testJSR376/com.guillempg.app -name "*.java")

and execute (as module) with:
java --module-path mods:libs -m com.guillempg.testJSR376/com.guillempg.app.TestApp
