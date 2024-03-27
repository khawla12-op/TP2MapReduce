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
5. Visualize the file `ventes.txt `
   








hadoop jar <path_to_jar_file> hadoop.mapreduce.job1.Driver /path/to/ventes.txt /output_ventes
## Job 2: Total Sales per Product per City for a Given Year

The second MapReduce job calculates the total sales for each product in each city for a specific year.

### Input
ventes.txt: Sales data file in the specified format.
### Output
Total sales per product per city for the given year.
