# pkjava9hiperf

## 1
If most of your strings can be encoded either as 
ISO-8859-1 or Latin-1 (1 byte per character), they'll be stored much more efficiently in Java 9.
### Modular development and its impact
```
java --list-modules
java --list-modules java.base
```
link modules together
```
jlink --module-path $JAVA_HOME/jmods:mlib --add-modules java.desktop --output myawesomeimage
myawesomeimage/bin/java --list-modules
```
#### The world of heap
- the garbage collector efficiently collects all the unused objects and reclaims memory. 
- When this young space gets filled up with new objects, the garbage collector takes charge and moves any of those
who have lived long enough in the young space to the old space. This way, there is always room for more objects in the young space.

#### Why bother compressing strings?
data type:
Utf-16: 2 byte per char[]
Latin1 String : 1 byte per char[]

#### What is the escape route?
The JPM team has provided a kill switch
```--XX: -CompactStrings``` using which you can disable this feature.

####　Indify String Concatenation
ByteCode Outline plugin

## Microservices
### Why microservices?
