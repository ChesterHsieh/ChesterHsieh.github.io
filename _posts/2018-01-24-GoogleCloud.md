# The task intro
You need to batch process the big data. One easy solution is to use spark. As data scientist the Pyspark is the easy solution. Since the whole data set and eco system is built on google in my case. This document has limited content because I just want the reader can follow the steps by steps to run the task. 

# Dataproc
## init the cluster
## Send the job


# Spark 
## Initial setting
The process to ask resource from computer. Here's two example for **Local** and **Cluster**

For the Local:
```python
spark = SparkSession \  
    .builder \  
    .appName("Process termsToProducts") \  
    .config('spark.driver.memory', '4G') \  
    .config('spark.executor.memory', '4G') \  
    .config('spark.driver.maxResultSize', '0') \  
    .getOrCreate()
```
You might wonder why we need to put spark on Local. Two reason I'm doing this:
1. Unit test for partial function. It's still easier to debug at local computer. You can shutdown anytime and without overhead. 
2. If you read the file b

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTg2NzY3OTQ1NiwtNTA4NTUyNDAwXX0=
-->