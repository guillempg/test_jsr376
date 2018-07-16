1- Check you're using Java 9+ (java -version)

2- From main folder:

Compile (as module) with:
javac --module-path libs -d mods/com.guillempg.testJSR376 $(find com.guillempg.testJSR376/com.guillempg.app -name "*.java")

and execute (as module) with:
java --module-path mods:libs -m com.guillempg.testJSR376/com.guillempg.app.TestApp

You can prepare a custom JRE with just enough Java modules to run your application with the command:

jlink --module-path mods:libs --add-modules com.guillempg.testJSR376,java.base --output customJRE

(but it will not work if you do not previously remove or comment out the "requires junit" from module-info.java file).
