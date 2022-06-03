---
layout: post
title:  "DB Tables Aggregation"
---
#### Team:  
* Idea: Stas
* Project Manager: Nikita
* Project Developer: Alina


### Description:  
Given two tables , combine them using combined key into one and insert into new table.  
**Challenges:**  
* Tables are around 7M rows each 
* Tables are hosted in different databases
* Job needs to be run regularly  

**Additional challenges:**  
* Update only changed and new rows in combined table
* Use ORM
* Look into parallel computing  

### Input:  
Tables examples:  
table_1:

| Merchant_id | message_filter_id | sent_date | total_cnt | success_cnt | problematic_cnt | mtm_problematic_cnt | nbo_cnt | non_usd_count |  
|:-----------:|:-----------------:|:---------:|:---------:|:-----------:|:---------------:|:-------------------:|:-------:|:-------------:|  
|01|010101|2022-05-21|1000|950|50|47|2|1|
|02|020101|2022-05-26|2000|1900|100|47|42|11|

table_2:

| MerchantId | OrderDate | filterId | ordercount |
|:----------:|:---------:|:--------:|:----------:|
|01|2022-05-21|010101|900|
|02|2022-05-26|020101|1800|

Resulting table:

| Merchant_id | message_filter_id | sent_date | total_cnt | success_cnt | problematic_cnt | mtm_problematic_cnt | nbo_cnt | non_usd_count | ordercount |
|:-----------:|:-----------------:|:---------:|:---------:|:-----------:|:---------------:|:-------------------:|:-------:|:-------------:|:----------:|
|01|010101|2022-05-21|1000|950|50|47|2|1|900|
|02|020101|2022-05-26|2000|1900|100|47|42|11|1800|


You can generate fake table entries using [mockbase](https://github.com/PythonLearningClub/mockbase).