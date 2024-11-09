# Mental-Health-Prevalence-Analysis
This files contains SQL-based analyses on mental health disorder prevalence across countries, exploring trends by gender, region, and time. It includes setup instructions, data import methods, and optimized SQL queries for insights on disorders like anxiety, depression, bipolar disorder, schizophrenia, and eating disorders.

I use the Schema icon (create new schema) and then I create table and use table data import wizard. to import out five tables
But if you want to write SQL code to create table you can do something like this:
note that I do not use following code in my project:

CREATE DATABASE databasename
USE databasename;
SHOW VARIABLES LIKE 'local_infile';
SET GLOBAL local_infile = 'ON';
DROP TABLE anxiety;
CREATE TABLE anxiety (
    `index` INT PRIMARY KEY,
    Entity VARCHAR(255),
    Code VARCHAR(10),
    Year INT,
    Prevalence_Male FLOAT,
    Prevalence_Female FLOAT,
    Population INT,
    Continent VARCHAR(255)
);
LOAD DATA LOCAL INFILE 'prevalence_of_anxiety_disorders_males_vs_females.csv'
INTO TABLE anxiety
FIELDS TERMINATED BY ','
ENCLOSED BY '"'
LINES TERMINATED BY '\n'
IGNORE 1 ROWS
(`index`, and other columns name);
