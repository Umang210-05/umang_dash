# Test Execution Analytics Dashboard

## Overview

A Plotly Dash based analytics dashboard for monitoring automated test execution results across multiple CSV reports.

The dashboard automatically loads all CSV files from the `reports` folder, combines them into a single dataset, and provides interactive analytics, filtering, monitoring, and reporting capabilities.

---

## Features

### Automatic CSV Loading

The application automatically loads all CSV files present in:

```text
reports/
```

Example:

```text
reports/
├── test-summary-2026-06-08.csv
├── 9 June.csv
├── 10 June.csv
```

No code changes are required when new CSV files are added.

---

## Dashboard Components

### KPI Cards

Displays:

* Total Tests
* Passed Tests
* Failed Tests
* Skipped Tests
* Broken Tests

---

### Date Filters

Users can:

* Select Start Date
* Select End Date

Dashboard updates automatically.

---

### Status Filter

Filter test executions by:

* PASS
* FAIL
* SKIPPED
* BROKEN

Multiple selections supported.

---

## Charts

### 1. Test Status Distribution

Donut chart showing:

* PASS
* FAIL
* SKIPPED
* BROKEN

Color Mapping:

| Status  | Color  |
| ------- | ------ |
| PASS    | Green  |
| FAIL    | Red    |
| SKIPPED | Yellow |
| BROKEN  | Purple |

---

### 2. Duration Analysis

Bar chart showing execution duration ranges:

* 0–10 Seconds
* 10–20 Seconds
* 20–30 Seconds
* 30–40 Seconds
* 40–50 Seconds
* 50–60 Seconds
* 60+ Seconds

---

### 3. Failed Test Analysis

Displays failed test executions grouped by date.

Supports stacked analysis if a test categorization column is available.

---

### 4. Daily Test Trend

Three line chart trends:

#### Total Tests

Running cumulative total.

Example:

```text
8 June → 10 Tests
9 June → 20 Tests

Total:
8 June → 10
9 June → 30
```

#### New Tests

New executions per day.

#### Updated Tests

Tests having values in:

```text
UPDATED AT
```

column.

---

### 5. Monitor Status Analysis

Stacked chart displaying:

* HIGH
* CRITICAL
* MONITOR CLOSELY

broken down by execution status.

Useful for monitoring high-risk automated tests.

---

### 6. Failure Root Cause Analysis

Donut chart showing:

* Failure Root Cause distribution
* Total failed root causes count displayed in center

Example:

```text
Login Failure
Database Issue
API Timeout
Network Error
```

---

## Interactive Tables

### View New Tests

Displays:

```text
DATE
TEST ID
TEST NAME
STATUS
DURATION (S)
```

---

### View Updated Tests

Displays:

```text
DATE
UPDATED AT
TEST ID
TEST NAME
STATUS
```

---

### Failed Tests

Displays only failed test executions.

Useful for quick defect analysis.

---

### Full CSV Table

Displays the complete merged dataset.

Supports:

* Sorting
* Filtering
* Search

---

## Auto Refresh

Dashboard refreshes every:

```text
60 Seconds
```

using:

```python
dcc.Interval()
```

Any changes made to CSV files are reflected automatically after refresh.

---

## Folder Structure

```text
infocus/
│
├── infocus.py
│
├── reports/
│   ├── test-summary-2026-06-08.csv
│   ├── 9 June.csv
│   ├── 10 June.csv
│   └── ...
│
└── README.md
```

---

## Installation

Create virtual environment:

```bash
python -m venv venv
```

Activate:

### Windows

```bash
venv\Scripts\activate
```

Install dependencies:

```bash
pip install dash pandas plotly numpy
```

---

## Run Dashboard

```bash
python infocus.py
```

Open:

```text
http://127.0.0.1:8052
```

---

## Technologies Used

* Python
* Pandas
* Plotly
* Dash
* NumPy

---

## Future Enhancements

* Export to Excel
* PDF Reports
* User Authentication
* Dark Mode
* Scheduled Email Reports
* Trend Forecasting
* Defect Prediction Analytics

---

## Author

QA Analytics Dashboard Project

Built using Python, Dash and Plotly.
