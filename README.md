Sparkify Airflow Data Pipeline
Udacity Data Engineering Nanodegree Project 5: Data Pipelines 
 Overview
This mission builds a statistics pipeline for Sparkify the usage of Apache Airflow that automates and video display units the walking of an ETL pipeline. 
 The ETL masses music and log statistics in JSON layout from S3 and approaches the statistics into analytics tables in a celebrity schema on Reshift. A big name schema has been used to permit the Sparkify group to with ease run queries to research person hobby on their app. Airflow frequently schedules this ETL and video display units its achievement via way of means of walking a statistics excellent test. 
 Structure
udac_example_dag.py consists of the duties and dependencies of the DAG. It ought to be positioned withinside the dags listing of your Airflow installation.
create_tables.square consists of the SQL queries used to create all of the required tables in Redshift. It ought to be positioned withinside the dags listing of your Airflow installation.
sql_queries.py consists of the SQL queries used withinside the ETL process. It ought to be positioned withinside the plugins/helpers listing of your Airflow installation.
The following operators ought to be positioned withinside the plugins/operators listing of your Airflow installation: 
 stage_redshift.py consists of StageToRedshiftOperator, which copies JSON statistics from S3 to staging tables withinside the Redshift statistics warehouse.
load_dimension.py consists of LoadDimensionOperator, which masses a size desk from statistics withinside the staging desk(s).
load_fact.py consists of LoadFactOperator, which masses a truth desk from statistics withinside the staging desk(s).
data_quality.py consists of DataQualityOperator, which runs a statistics excellent test via way of means of passing an SQL question and anticipated end result as arguments, failing if the consequences don`t match.
Configuration
Make certain to feature the subsequent Airflow connections:
AWS credentials
Connection to Postgres database