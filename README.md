# Airline-De-Project
# Travel & Airline — Flight Operations Analytics

An end-to-end data engineering and analytics pipeline for **airline flight operations and passenger analytics**. This project works with a fully normalized **MySQL OLTP database**, processes the data using **PySpark**, transforms it into an analytical **Star Schema**, and loads business-ready data into **Databricks Delta Lake** for operational and passenger analytics.

## Problem Statement

The project focuses on building a complete airline data platform capable of handling operational, passenger, booking, revenue, baggage, and flight-status data.

The pipeline addresses the following key requirements:

* **Normalized Airline OLTP Source:** Design and work with a fully normalized MySQL database containing airlines, airports, aircraft, passengers, customers, flights, schedules, bookings, tickets, payments, baggage, crew, flight status, cancellations, and other core airline entities with appropriate primary-key and foreign-key relationships.
* **Automated ETL Pipeline:** Build an end-to-end ETL pipeline using PySpark to extract data from MySQL, perform cleansing, validation, joins, transformations, and airline business-rule calculations, and load the processed data into Databricks Delta Lake.
* **OLTP-to-OLAP Transformation:** Transform the normalized OLTP model into a Star Schema optimized for flight operations, passenger analytics, airline performance, airport performance, booking analysis, revenue analysis, and delay monitoring.
* **Data Quality & Incremental Processing:** Implement duplicate detection, null validation, invalid flight-time checks, airport and airline reference validation, negative fare detection, passenger-count validation, referential-integrity checks, and source-to-target reconciliation. Incremental processing is implemented using timestamps or change-tracking columns.
* **Airline Analytics & Reporting:** Build analytical tables and dashboards covering flight delays, cancellations, passenger volume, booking trends, airline performance, airport performance, route performance, ticket revenue, baggage statistics, flight occupancy, and operational KPIs.

## Architecture & Data Flow

### MySQL OLTP Layer

The source system follows a normalized relational database design to maintain airline operational data and reduce data redundancy.

Core entities include:

* Airlines
* Airports
* Aircraft
* Passengers
* Customers
* Flights
* Flight Schedules
* Bookings
* Tickets
* Payments
* Baggage
* Crew
* Flight Status
* Cancellations

### PySpark ETL Layer

PySpark is used to extract and process data from the MySQL OLTP database.

The ETL process performs:

* Data extraction from MySQL
* Schema validation
* Data type conversion
* Null and duplicate handling
* Referential-integrity validation
* Data cleansing
* Table joins
* Business-rule calculations
* Flight delay calculations
* Passenger and occupancy calculations
* Revenue calculations
* Incremental data processing

### Databricks Delta Lake

The transformed data is stored as Delta tables in Databricks, providing reliable and scalable analytical storage.

The pipeline separates the processed data into business-ready analytical tables following a Star Schema.

## OLTP to OLAP — Star Schema

The normalized OLTP database is transformed into a dimensional model optimized for analytics.

### Fact Tables

Example analytical fact tables include:

* `fact_flight_operations`
* `fact_bookings`
* `fact_ticket_revenue`
* `fact_baggage`
* `fact_passenger_activity`

### Dimension Tables

Example dimensions include:

* `dim_airline`
* `dim_airport`
* `dim_aircraft`
* `dim_passenger`
* `dim_customer`
* `dim_flight`
* `dim_route`
* `dim_date`
* `dim_crew`

The Star Schema enables efficient analysis of flight operations, passengers, bookings, revenue, routes, airports, and airlines.

## Data Quality & Validation

The pipeline includes multiple data-quality checks to ensure reliable analytical results.

Key validations include:

* Duplicate record detection
* Null-value validation
* Invalid flight-time detection
* Invalid airport references
* Invalid airline references
* Negative fare detection
* Invalid passenger counts
* Referential-integrity checks
* Source-to-target reconciliation
* Schema and data-type validation

Invalid records are identified before they reach the analytical layer.

## Incremental Processing

The ETL pipeline supports incremental processing using timestamp or change-tracking columns.

Instead of processing the entire source database during every execution, the pipeline identifies newly inserted or modified records and processes only the required data.

This approach helps to:

* Reduce processing time
* Reduce compute requirements
* Improve pipeline efficiency
* Support regular data refreshes
* Maintain up-to-date analytical tables

## Airline Analytics & Reporting

The final analytical tables support dashboards and reporting for key airline business areas.

### Flight Operations

Analysis of:

* Total flights
* On-time vs delayed flights
* Average delay duration
* Flight cancellations
* Flight status
* Route performance
* Flight occupancy

### Passenger Analytics

Analysis of:

* Total passengers
* Passenger volume by airline
* Passenger volume by airport
* Passenger trends
* Passenger distribution across routes
* Flight occupancy rates

### Airline Performance

Comparison of:

* Airline flight volume
* On-time performance
* Cancellation rates
* Passenger volume
* Revenue
* Average flight delays

### Airport Performance

Analysis of:

* Arrivals and departures
* Passenger traffic
* Delays by airport
* Cancellations
* Airport-wise flight volume

### Booking & Revenue Analytics

Analysis of:

* Booking trends
* Ticket sales
* Ticket revenue
* Average ticket fare
* Revenue by airline
* Revenue by route
* Revenue trends

### Baggage Analytics

Analysis of:

* Total baggage
* Baggage volume by flight
* Baggage statistics by airport
* Baggage-related operational metrics

## Tech Stack

* **Database:** MySQL
* **Data Processing:** PySpark
* **Data Platform:** Databricks
* **Storage:** Delta Lake
* **Query Language:** SQL
* **Programming Language:** Python
* **BI / Visualization:** Power BI

## Project Workflow

```text
MySQL OLTP Database
        ↓
   Data Extraction
        ↓
     PySpark ETL
        ↓
 Data Cleaning & Validation
        ↓
 Business Transformations
        ↓
 Incremental Processing
        ↓
 Databricks Delta Lake
        ↓
   Star Schema / OLAP
        ↓
 Analytical Tables
        ↓
     Power BI
        ↓
Airline Operations & Passenger Analytics
```

## Key Performance Indicators (KPIs)

The project provides analytical KPIs such as:

* Total Flights
* Total Passengers
* Total Revenue
* Average Ticket Fare
* Flight Occupancy Rate
* Average Flight Delay
* On-Time Performance
* Cancellation Rate
* Total Bookings
* Total Baggage
* Revenue by Airline
* Revenue by Route
* Passenger Volume by Airport

## Team Members

* **Shubagita P S**
* **Sudharshinee S K**
* **Tamil B S**
* **Vaishnavi M**

