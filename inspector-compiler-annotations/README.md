inspector-compiler-annotations
======================================

This artifact contains optional compile-time annotations for the `inspector-compiler`. 
These are extracted so you can use them as a `compileOnly` dependency in Android projects without 
placing the full annotation processor in the factory compiler artifact on your classpath.

See the `inspector-compiler` README for full documentation.

[![Maven Central](https://img.shields.io/maven-central/v/io.sweers.inspector/inspector-compiler-annotations.svg)](https://mvnrepository.com/artifact/io.sweers.inspector/inspector-compiler-annotations)
```gradle
implementation 'io.sweers.inspector:inspector-compiler-annotations:x.y.z'
```

Proguard rules for obfuscation:

```proguard
# Retain generated classes that end in the suffix
-keepnames class Validator_**

# Prevent obfuscation of types which use @GenerateValidator since the simple name
# is used to reflectively look up the generated adapter.
-keepnames @io.sweers.inspector.compiler.annotations.GenerateValidator class *
```
