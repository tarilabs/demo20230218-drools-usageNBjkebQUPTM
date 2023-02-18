Cannot reproduce.

To replicate the steps:

```sh
curl https://repo.maven.apache.org/maven2/org/kie/kie-api/7.73.0.Final/kie-api-7.73.0.Final.jar --output kie-api-7.73.0.Final.jar
unzip -p kie-api-7.73.0.Final.jar org/kie/api/runtime/KieContainer.class > KieContainer.class
javap -verbose KieContainer.class
```

Gives:

```
Classfile /Users/mmortari/git/tmp/demo20230218-drools-usageNBjkebQUPTM/KieContainer.class
  Last modified Feb 18, 2023; size 2561 bytes
  MD5 checksum 30703f76c83e07d5bbdf362cf8496ea7
  Compiled from "KieContainer.java"
public interface org.kie.api.runtime.KieContainer
  minor version: 0
  major version: 52
  flags: ACC_PUBLIC, ACC_INTERFACE, ACC_ABSTRACT
Constant pool:
   #1 = Class              #52            // org/kie/api/runtime/KieContainer
   #2 = Class              #53            // java/lang/Object

....
```

So the original claim is invalid.

Further, this project is just the result of the archetype generation

```sh
mvn archetype:generate -DarchetypeGroupId=org.kie -DarchetypeArtifactId=kie-drools-archetype -DarchetypeVersion=7.73.0.Final
```

and integrated with GHA usign JDK 1.8.