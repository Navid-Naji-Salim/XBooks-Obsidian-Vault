# Home Dashboard Review

## Overall Assessment

The current Home dashboard has a strong foundation. The information being presented is meaningful and grounded in actual accounting concepts rather than filler or fake analytics.

After understanding the accounting terminology and intent behind each section, the dashboard feels much more useful than it initially appeared.

The remaining issues are primarily related to **communication, visual hierarchy, and presentation**, not the underlying business concepts.

---

# 1. Hero Description

## Current

The subtitle currently reads something similar to:

> Live bookkeeping pulse for X customers, Y vendors, Z invoices...

## Problem

This feels overly descriptive and somewhat artificial. It reads more like an explanation of the application than a professional dashboard.

The user already knows how many customers or invoices exist, and this information does not help them make better decisions.

## Recommendation

Replace it with a short, calm, professional sentence that communicates the purpose of the dashboard rather than listing statistics.

Examples:

- Everything you need to monitor your business today.
- Your financial overview at a glance.
- Monitor receivables, payables, and cash position from one place.
- Here's today's financial overview.

---

# 2. Cash Flow Widget

## Overall

The accounting concept is good.

The visualization is not communicating it effectively.

---

## Missing Legend

### Problem

The chart never explains what each visual element represents.

The user has to guess.

### Recommendation

Include a small legend explaining:

- Green = Incoming money
- Red = Outgoing money
- Blue = Running cash balance

The chart should explain itself without requiring interpretation.

---

## Blue Line Is Unclear

### Problem

The blue line represents the running cash balance, but nothing tells the user that.

Without reading the code, its purpose is unclear.

### Recommendation

Keep the running balance, but clearly identify it in the chart legend and make its purpose obvious.

---

## Month Labels

### Problem

The graph only displays month names.

When looking at historical data, the year is missing.

### Recommendation

Display the fiscal year alongside the months where appropriate.

Examples:

- Jan '26
- Feb '26

or otherwise make the active fiscal year obvious.

---

## "Refreshes Automatically"

### Problem

This is implementation detail rather than useful business information.

Users naturally expect dashboards to remain current.

### Recommendation

Remove it completely.

---

# 3. Income vs Purchases

## Orientation

### Problem

This visualization is horizontal while the Cash Flow visualization uses a different visual direction.

This creates inconsistency without a clear reason.

### Recommendation

Use a consistent visualization language throughout the dashboard.

If one financial chart is vertical, similar financial charts should generally follow the same direction unless there is a compelling reason not to.

---

## Communication

This chart suffers from many of the same problems as the Cash Flow section.

It lacks sufficient explanation and does not clearly communicate the story behind the data.

The underlying accounting information is useful, but the visualization should communicate trends more effectively.

---

# 4. Graph Communication

## Current Issue

The graphs successfully display data.

They do not successfully communicate insights.

A graph should immediately answer questions such as:

- Is income increasing?
- Is spending decreasing?
- Are payments becoming overdue?
- Is cash position improving?

Currently, the visualizations require interpretation rather than providing immediate understanding.

---

# 5. Visual Hierarchy

The dashboard currently gives nearly every section similar visual weight.

As a result, important operational information competes with analytical information.

The dashboard should instead establish a clearer hierarchy.

The primary focus should remain:

- Outstanding receivables
- Outstanding payables
- Cash position

Secondary information should support these areas rather than compete with them.

---

# 6. Snapshot Values vs. Over-Time Values

One of the biggest conceptual inconsistencies is that the dashboard mixes two different kinds of financial information without visually distinguishing them.

## Snapshot Values

These describe the current financial position at a single moment.

Examples:

- Outstanding receivables
- Current receivables
- Overdue receivables
- Outstanding payables
- Current payables
- Overdue payables

These answer:

> "What is the situation right now?"

---

## Over-Time Values

These describe financial movement across a period.

Examples:

- Cash flow
- Income
- Purchases
- Running cash balance

These answer:

> "How has money moved over time?"

---

## Recommendation

These two categories should feel visually distinct.

Snapshot values should emphasize the current financial position.

Trend-based information should emphasize movement over time.

Separating these concepts visually will make the dashboard easier to understand.

---

# Conclusion

The Home dashboard already has a strong accounting foundation.

The data being displayed is meaningful and relevant.

The remaining improvements are primarily related to:

- Better communication
- Stronger visual hierarchy
- More consistent visualization
- Clearer chart explanations
- Better distinction between operational information and trend analysis

The goal is not to redesign the dashboard from scratch, but to refine its presentation so that every element immediately communicates its purpose.
[[Bug 1]]