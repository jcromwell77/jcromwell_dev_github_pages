---
layout: default
title: Jonny Cromwell | Data Engineer
---

# Jonny Cromwell

**Data Engineer**

[LinkedIn](https://www.linkedin.com/in/jonny-cromwell) · [GitHub](https://github.com/jcromwell77)

---

## About

Data engineer with hands-on experience building ELT pipelines, data warehouses, and transformation layers across multiple platforms. Currently focused on healthcare data interoperability, specifically HL7 FHIR R4 data standards. I approach complex problems by combining practical engineering skills with a willingness to learn new domains — whether that means parsing deeply nested clinical JSON structures or standing up containerized database environments from scratch.

---

## Projects

### HL7 FHIR End-to-End Data Engineering Pipeline
**Status:** Pipeline 1 of 3 complete

A production-style ELT pipeline that ingests synthetic HL7 FHIR R4 healthcare data and transforms it into an analytics-ready data warehouse using the medallion architecture.

**The problem:** FHIR data is deeply nested JSON with extension-based fields, coded terminology systems (LOINC, SNOMED), and cross-resource references. Flattening this into queryable relational tables requires parsing patterns that don't exist in traditional CSV or flat-file pipelines.

**What I built:**
- Generated synthetic FHIR R4 patient data (Patient, Encounter, Observation resources) using Synthea in both NDJSON and Bundle formats
- Loaded raw FHIR JSON into PostgreSQL JSONB tables (bronze layer) using Python with batch inserts
- Built dbt models that flatten nested FHIR structures, parse resource references into foreign keys, and extract extension fields like race, ethnicity, and geolocation (silver layer)
- Created dimension and fact tables with calculated ages, lab panel classification, clinical reference ranges, and abnormal result flagging (gold layer)
- Implemented 23 automated data tests validating uniqueness, null checks, and referential integrity across all layers

**Tech stack:** Python · PostgreSQL 17 · dbt · Docker · Synthea

**Planned expansions:**
- Pipeline 2: SQL Server + SSIS
- Pipeline 3: AWS (S3, Glue/Lambda, Redshift/Athena)

[View Repository](https://github.com/jcromwell77/fhir_project) · [View dbt Documentation](https://jcromwell77.github.io/fhir_project/)

---

### Synthetic Health Data Generator
A Python-based synthetic data generator built with the Faker library for creating large-scale healthcare datasets. Designed to produce configurable volumes of patient demographics and daily health records (vitals, blood pressure, weight) partitioned by year and month.

**What it demonstrates:**
- Generated over 40 million records (10,000 patients across 10 years) for stress-testing ETL pipelines
- Configurable patient count and date range for scalable test data
- Used as source data for building and validating pipelines in both PostgreSQL/Python and SQL Server/SSIS environments

**Tech stack:** Python · Faker · Pandas

[View Repository](https://github.com/jcromwell77/synthetic_health_data)

---

## Development Approach

I build these projects collaboratively with AI tools (primarily Claude) to bridge knowledge gaps and accelerate development, while ensuring I understand every component end-to-end. Each project includes documentation I wrote myself explaining the architecture, design decisions, and implementation details. I believe the ability to work effectively with AI tools is itself an engineering skill — knowing what to ask, how to validate the output, and when to push back on a recommendation.
