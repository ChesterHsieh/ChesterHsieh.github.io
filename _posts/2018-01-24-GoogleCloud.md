# The task intro
You need to batch process the big data. One easy solution is to use spark. As data scientist the Pyspark is the easy solution. Since the whole data set and eco system is built on google in my case. This document has limited content because I just want the reader can follow the steps by steps to run the task. 

# Dataproc
## init the cluster
## Send the job


# Spark 
## Initial setting
N

```python
spark = SparkSession \  
    .builder \  
    .appName("Process termsToProducts") \  
    .config('spark.driver.memory', '4G') \  
    .config('spark.executor.memory', '4G') \  
    .config('spark.driver.maxResultSize', '0') \  
    .getOrCreate()
```

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTY5MTcyNjYyOSwtNTA4NTUyNDAwXX0=
-->