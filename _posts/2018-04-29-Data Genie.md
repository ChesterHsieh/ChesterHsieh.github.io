# Milestone
1. Run Sqlova test code
	1.1 Start to train with wikisql
	1.2
2.	 Modified 
	2.1 To understand the data format
3. Pytorch Tutorial
	3.1 Know where's entry point

# Run NLIDB-transfer learning
## Download
- might need to add **__init__.py** file
- change some file prvlig: **chmod -R 777 desired_location/**
- Need download glove embeddeding file
## Environment
must be installed as python2
- conda create -n env_psudo



# Run sqlova sample code
## To setup a new machine
```
gcloud compute instances create my-instance
```
## To run sqlova .sh initial shell file
pip3 install requests
pip3 install records
pip3 install tqdm
pip3 install babel
pip3 install matplotlib
pip3 install defusedxml

install zip
sudo apt install unzip

## Need to download raw data

 1. [download google drive download tool](https://medium.com/tinghaochen/how-to-download-files-from-google-drive-through-terminal-4a6802707dbb)
 2. python download_gdrive.py 1iJvsf38f16el58H4NPINQ7uzal5-V4v4 /jet/prs/workspace/sqlova/annotated_data/xxx.zip
 3. 
 4. modify file train.py line 558 & 559 path_h = '/jet/prs/workspace/sqlova/data/'
 5. 
## Dump postgres sql 2 sqlite
[BLOG provide solution](https://manuelvanrijn.nl/blog/2012/01/18/convert-postgresql-to-sqlite/)


## File summery
evaluation_ws.py : take results_xxx.jsonl and xxx.jsonl to compute accuracy
train.py: Not only train the file but also prediction and generate result_xxx.json1 file.

## train.py mod
Need


# ETL - postgres SQL -> BQ
https://github.com/Powerspace/pg2bq
Most of the code can rely on this.
Follow the instruction it will be fine. 
# Pytorch Basics


# Rasa 
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE0MDgxOTExNzYsMjc5NjEwNjAxLDE5Nz
c3MzcyNDYsLTEyMzI4MDE0OTAsLTk4Njc2OTY2MywtNTUzMjQw
Mjk4LDM1MTM1ODgyNywxOTc2MDU1MDQ3LDEyNzI0NzE5MjYsLT
YxNjA5NDIxNV19
-->