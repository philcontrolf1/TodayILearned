# Creating Scala collections in Java

If you're interfacing with Scala code, you may well want to create some Scala
collections in Java.

## Seq

From a Java list:

```java
Seq<String, Integer> seq = JavaConversions$.MODULE$.asScalaBuffer(javaList).toSeq();
```

or from an array:

```java
Seq<String, Integer> seq = new WrappedArray.ofRef<>(array).toSeq();
```

## Map

From a Java map:

```java
Map<String, Integer> map = JavaConversions$.MODULE$.mapAsScalaMap(javaMap).toMap(Predef.conforms());
```

[Map source](http://stackoverflow.com/a/11903737/525010)
