# Content Catalog Analytics Dashboard

An interactive Excel-based analytics dashboard designed to analyze a large content catalog using Power Query, Excel Data Model, DAX measures, PivotTables, PivotCharts, dynamic arrays, slicers, timelines, and title-level exploration.

The project follows an end-to-end data analytics workflow:

**Data Cleaning → Transformation → Data Modeling → Analytical Measures → Interactive Dashboard → Detailed Content Exploration**

---

## Project Overview

This project analyzes a content catalog containing movies and TV shows across different countries, genres, ratings, audience groups, release years, and content durations.

The objective was to transform a raw dataset into a structured analytical model and build an interactive dashboard that allows users to explore the catalog from both portfolio-level and title-level perspectives.

The final workbook contains two main user-facing pages:

- **KPI's** — Executive analytics dashboard
- **DETAILS** — Title-level content explorer

## Business Questions

The dashboard was designed to answer questions such as:

- How large is the content catalog?
- What is the distribution between Movies and TV Shows?
- Which countries contribute the most content?
- Which genres dominate the catalog?
- How is content distributed across rating/audience groups?
- How has content addition changed over time?
- How does the catalog respond to different country, genre, type, rating, and date selections?
- What information is associated with a specific title?
- Which titles are similar to a selected title?
- How significant is the selected title's genre, country, and audience group within the catalog?

# Data Preparation

## Power Query

Power Query was used as the primary ETL layer.

The transformation process included:

- Data type standardization
- Text cleanup
- Date transformation
- Separation of duration value and duration unit
- Country normalization
- Genre-related preparation
- Rating classification
- Creation of analytical categories
- Handling of inconsistent/malformed text
- Preparation of fields for Data Model analysis

Power Query was intentionally used to keep data preparation separate from dashboard calculations.

# Data Model
The final workbook uses an Excel Data Model with a structured relational architecture.

Main components include:

- Main content table
- Country dimension
- Genre dimension
- Rating/category table
- Date dimension
- Duration unit dimension
The model separates descriptive dimensions from the main analytical content table and allows slicers and measures to propagate filters through relationships.

# Excel Features Used
Feature                                                     	Purpose
Power Query	                                                  ETL and data transformation
Excel Data Model	                                            Relational analytical model
Relationships	                                                Filter propagation between tables
DAX	                                                          Reusable analytical measures
PivotTables	                                                  Aggregation and analytical summaries
PivotCharts	                                                  Interactive visualizations
Slicers	                                                      Interactive categorical filtering
Timeline	                                                    Date-based filtering
Dynamic Arrays	                                              Dynamic Top-N and analytical outputs
LET	                                                          Readable multi-step formulas
FILTER	                                                      Context-based filtering
SORT	                                                        Ranking and ordering
TAKE	                                                        Dynamic Top-N extraction
HSTACK	                                                      Combining dynamic outputs
UNIQUE	                                                      Distinct-value analysis
XLOOKUP	                                                      Title-level attribute retrieval
Data Validation	                                              Interactive title selection
Hyperlinks	                                                  Dashboard navigation
Sheet Protection	                                            Protecting analytical/model layers

# Key Design Decisions
## Why Power Query?
To keep data cleaning and transformation separate from analytical calculations.

## Why a Data Model?
To create a reusable relational structure and allow multiple analytical components to share the same dimensions and measures.

## Why DAX measures?
To avoid repeating business logic across PivotTables and ensure consistent calculations.

## Why Slicers and Timeline?
To provide interactive filtering without requiring users to manipulate PivotTables manually.

## Why Dynamic Arrays?
To build flexible calculations such as dynamic Top-N analysis and title-level outputs.

## Why a separate DETAILS page?
The dashboard answers:
"What is happening?"

The Details page answers:
"Which content is responsible for it?"
### Simplified Model
Used Star Scheme in the data Modelling part with one to many cardinalities. 
