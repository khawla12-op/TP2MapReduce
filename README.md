# MapReduce Jobs for Sales Analysis

## Overview
This repository contains MapReduce jobs developed for analyzing sales data from a company. The data is stored in a text file named `ventes.txt` and consists of records with the following structure:
Each record represents a sale with information about the date, city, product, and price.

## Job 1: Total Sales per City
The first MapReduce job calculates the total sales for each city based on the sales data in `ventes.txt`.

### Input
- `ventes.txt`: Sales data file in the specified format.

### Output
- Total sales per city.

### Instructions
1. Start the containers using Docker Compose:

   ```docker-compose up -d ```

2. Copy the `ventes.txt`  and the jar file to the Hadoop cluster:
   
   ```docker cp ventes.txt 72e44bd23:/opt/hadoop```
   ```docker cp TP3_MapReduce-1.0-SNAPSHOT.jar 95a26e1:/opt/hadoop```
4. Enter the Namenode container:
 ```docker exec -it 72e44bd23 bash```
5. Visualize the file `ventes.txt ` with ``` cat /opt/hadoop/ventes.txt```
   ![1](https://github.com/khawla12-op/TP2MapReduce/assets/108635784/8503b821-256e-461a-aa64-916a7d3c6eb9)

6. Make sure that the jar file and the txt file are in the docker container
![2](https://github.com/khawla12-op/TP2MapReduce/assets/108635784/d8971e21-ec52-4ca1-a231-3a885d8145df)
7. Copy the file "ventes.txt" from your Docker container's local file system to HDFS using the following command: ```hdfs dfs -put /opt/hadoop/ventes.txt /```
8. Now that you have confirmed that the "ventes.txt" file is present in HDFS, you can execute your MapReduce job using the "ventes.txt" file as input. Here's how you can do it:

![3](https://github.com/khawla12-op/TP2MapReduce/assets/108635784/090ad11e-9ab2-4533-9073-8a2d6605fb7f)
8. See the result of the output file:
![4](https://github.com/khawla12-op/TP2MapReduce/assets/108635784/d244538d-4134-4255-9e12-30954c69d604)
]![5](https://github.com/khawla12-op/TP2MapReduce/assets/108635784/9e59223a-2628-464c-901f-57e0464ea40e)
![6](https://github.com/khawla12-op/TP2MapReduce/assets/108635784/01ce0a27-dd05-4a37-90e4-0dd05b10382e)
## Job 2: Total Sales per Product per City for a Given Year

The second MapReduce job calculates the total sales for each product in each city for a specific year.

### Input
ventes.txt: Sales data file in the specified format.
### Output
Total sales per product per city for the given year.
```  hadoop jar TP3_MapReduce-1.0-SNAPSHOT.jar hadoop.mapreduce.job2.Driver /ventes.txt output_per_year 2024```
