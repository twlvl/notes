## The language and the platform
_The Java language_ — The Java language is the statically typed, object-oriented language that we lightly lampooned in the “About this book” section. Hopefully, it’s already very familiar to you. One obvious point about source code written in the Java language is that it’s human-readable (or it should be!).

_The Java platform_ — The platform is the software that provides a runtime environment. It’s the JVM that links and executes your code as provided to it in the form of (not human-readable) class files. It doesn’t directly interpret Java language source files but instead requires them to be converted to class files first.

The link between the language and platform is the shared definition of the class file format (the `.class` files).

![[./img/java-class.png]]
Some people describe the Java system as “dynamically compiled.” This emphasizes that the compilation that matters is the JIT compilation at runtime, not the creation of the class file during the build process.
## The new Java release model
Java 7 was the first version of Java to be developed under an open source software (OSS) license. The primary focus for open source development of the Java platform since then has been the [OpenJDK project](https://openjdk.java.net), and that continues to this day.

A lot of the project discussion takes place on mailing lists that cover aspects of the overall codebase. There are “permanent” lists such as core-libs (core libraries), as well as more transient lists that are formed as part of specific OpenJDK projects such as lambda-dev (lambdas), which then become inactive when a particular project has been completed.

A new version of Java is released every six months (“feature releases”). The various providers (Oracle, Eclipse Adoptium, Amazon, Azul, et al.) can choose to make _any_ of those releases a Long-Term Support (LTS) release. However, in practice, all of the vendors follow having one release every three years being named as the LTS release.
![[./img/java-releases.png]]

The changes made to the LTS versions are deliberately small in scope and are “housekeeping updates.” Apart from security and small bug fixes, only a minimal set of changes are permitted.
One other necessary change is that the build scripts for macOS needed to be updated to work with a recent version of Apple’s Xcode tool so that they will continue to work on new releases of Apple’s operating system.
## Enhanced type inference (var keyword)
