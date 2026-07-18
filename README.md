# M-Agriculture Solutions

## Automated Daily Milk Recording for Small-Scale Farms

This repository defines a **mobile-based dairy farm records management solution** focused on replacing manual notebooks with a simple daily digital workflow.

## Problem Addressed

Small-scale dairy farmers often track milk records manually, which causes:
- missing or inconsistent daily entries
- delayed and inaccurate reporting
- difficult traceability per cow and per milking session

## Solution Overview

The M-Agriculture solution provides:
- **Mobile-first daily milk entry** (morning/evening and per cow)
- **Automated daily record generation** with date, farmer, and animal context
- **Historical record storage** for trend analysis and auditability
- **Instant summaries** (per cow, per day, and total farm output)
- **Manual-book elimination** through searchable digital records

## Minimum Functional Requirements

1. Register and manage farmer profile, cows, and lactation status.
2. Capture milk volumes per cow for each milking session every day.
3. Auto-create a daily record for each farm date and prevent accidental duplicates.
4. Allow offline capture and later sync when network is available.
5. Provide daily/weekly/monthly production reports.
6. Export/share summaries for cooperative collection or accounting.

## Core Data Model (Conceptual)

- `Farmer(id, name, phone, location)`
- `Cow(id, farmer_id, tag_number, breed, status)`
- `MilkEntry(id, cow_id, date, session, liters, captured_at, captured_by)`
- `DailySummary(id, farmer_id, date, total_liters, cows_milked, synced)`

## Expected User Flow

1. Farmer opens the mobile app.
2. Selects date (defaults to today) and session (morning/evening).
3. Enters liters per cow.
4. App validates entries and saves locally.
5. App auto-generates/updates daily summary totals.
6. Data syncs to central storage when online.

## Acceptance Criteria

- Farmers can submit complete daily milk entries for all active cows in less than 5 minutes.
- System flags missing cow entries before day closure.
- No duplicate records for the same cow/date/session.
- Daily totals and per-cow history are available immediately after entry.
- Records remain available even when the device is temporarily offline.