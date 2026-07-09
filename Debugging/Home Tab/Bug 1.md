# Dashboard Calculations Belong in the Backend

## Problem

The Home dashboard calculates business metrics on the frontend using raw data (e.g. invoices and bills) instead of receiving precomputed values from the backend.

While this works functionally, it places business logic in the presentation layer.

---

## Why This Is a Problem

The frontend should be responsible for displaying data, not calculating accounting metrics.

Calculations such as:

- Receivables
- Payables
- Cash flow
- Income vs. Purchases
- Top expenses
- Outstanding balances
- Overdue totals

are business logic and should originate from the backend.

Keeping these calculations in the frontend creates several issues:

- Duplicates business logic.
- Makes the frontend more complex.
- Increases the amount of data that must be sent to the client.
- Makes it easier for different pages to calculate the same metric differently.
- Becomes less scalable as the application grows.

---

## Correct Architecture

```
Database
    ↓
Backend
    ├── Calculate dashboard metrics
    ├── Aggregate accounting data
    └── Return a DashboardSummary object
            ↓
Frontend
    ├── Display values
    ├── Format numbers
    ├── Render charts
    └── Handle UI interactions
```

The frontend should only transform the received data into visual components (cards, charts, tables, etc.), not perform accounting calculations.

---

## Acceptable Frontend Logic

The frontend may still perform lightweight presentation logic, such as:

- Currency formatting
- Date formatting
- Chart point mapping
- Percentage widths for progress bars
- Sorting or filtering already-received display data

These are UI concerns rather than business rules.

---

## Recommendation

Move all dashboard business calculations into the backend (e.g. the summary endpoint) and return a fully populated `DashboardSummary`.

The frontend should consume that object directly and remain focused solely on presentation.