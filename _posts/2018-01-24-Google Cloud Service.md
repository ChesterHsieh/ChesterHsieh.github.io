# The task intro
You need to batch process the big data. One easy solution is to use spark. As data scientist the Pyspark is the easy solution. Since the whole data set and eco system is built on google in my case. This document has limited content because I just want the reader can follow the steps by steps to run the task. 

# Dataproc
**Dataproc** is the friendly cluster environment provided by google cloud service. 
## init the cluster
To create the cluster 

    gcloud dataproc clusters create userbehavior-tagger-serch --region us-east1 --num-workers 4 --master-machine-type n1-standard-8 --project hd-srch-dev --tags=dataproc,all-bastion-ssh,solr,zookeeper,zkhost --subnet backend-us-east1-subnet --zone us-east1-b --initialization-actions gs://cxh89s9-tagger-experiment/ss_init_env.sh

- cluster name
- --initialization-action 
	put .sh file path in bucket
	


## Send the job
 

# Run sqlova sample code
## To setup a new machine
```
gcloud compute instances create my-instance
```
## To run sqlova .sh initial shell file
pip3 install requests
pip3 install records
pip3 install 
## Need to download raw data

 1. [download google drive download tool](https://medium.com/tinghaochen/how-to-download-files-from-google-drive-through-terminal-4a6802707dbb](https://medium.com/tinghaochen/how-to-download-files-from-google-drive-through-terminal-4a6802707dbb))
 2. python download_gdrive.py 1iJvsf38f16el58H4NPINQ7uzal5-V4v4 /jet/prs/workspace/sqlova/annotated_data/
 3. modify file train.py line 558 & 559 path_h = '/jet/prs/workspace/sqlova/data/'
 4. 
## Dump postgres sql 2 sqlite
[BLOG provide solution](https://manuelvanrijn.nl/blog/2012/01/18/convert-postgresql-to-sqlite/)


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
2. If you read the file bigger than ram size. Using pandas with chunk is one way, using spark is other way to explore the data set. Moreover, you'll need to put in cloud and deal with big data in production. 

For the cluster :
```python
spark = SparkSession \  
    .builder \  
    .appName("Process termsToProducts") \  
    .config('spark.driver.memory', '19G') \  
    .config('spark.executor.memory', '9G') \  
    .config('spark.driver.maxResultSize', '0') \  
    .getOrCreate()
```

## Why?
### Why use cache?

### Why use repartition?

Hi. I am not sure if repartition is needed everywhere. I hoped that Spark is clever enough to do it itself.
When some failure is reproducible only at cluster and each retry takes 2 hours you probably do something redundant to avoid failure.
Job was failing a lot because of not enough memory.
Also initially I created cluster with single machine. Now I run 1+4 machines.
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTIwODI4NDIyNDEsLTg3NzA1NDE1OCwtOD
c0NzEwNjMyLC01NzgwNzQyOTQsMTU3OTY4NzY2Nl19
-->