# Neo-Bank Unified Analytics Platform

A production-style, end-to-end data engineering pipeline on Databricks, implementing a medallion architecture (Bronze->Silver->Gold->Semantic Layer) for a fictional Neo-Bank. Built to demonstrate real-world patterns for metadata driven ingestion, incremental processing, idempotent transformations and business facing analytics.

## Table of Contents

- Project Overview
- Architecture Overview
- Tech Stack
- Data Sources
- Layer-by-Layer Design
- Key Engineering Decisions
- Repository Structure
- Dashboard
- Orchestration
- Know Issues and Roadmap
- How to run the project

## Project Overview

This project integrates the Neo-Bank data stored in multiple sources, formats i.e customer, account, branch and transaction data flowing in from an operational database, blended with external file-based feeds(credit bureau reports, payment gateway logs) into a unified analytics platform.This provides business users with self service analytics for operational and risk insights.

![Architecture diagram](architecure/architure.png)
