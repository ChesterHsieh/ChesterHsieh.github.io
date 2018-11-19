## Read file

The .collect() method returns all the elements of the RDD to the
driver where it is serialized as a list.


## Transformation
#### map
## Actions
#### count()
#### take(# of smaple)
#### collect()
#### reduce
## Lazy Priciple


## DataFrame
#### Catalyst Optimizer refresh
![catalyst](../img/catalyst.png)

#### Speed ISSUE

It is important to note that while, with DataFrames, PySpark is often
significantly faster, there are some exceptions. The most prominent one
is the use of Python UDFs, which results in round-trip communication
between Python and the JVM. Note, this would be the worst-case
scenario which would be similar if the compute was done on RDDs

#### No map here :(
