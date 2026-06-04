# FWDGuard

A fork of xDrip+ stripped down to low-alert-only functionality for parents/guardians of children with diabetes.

## Core Goal
- Monitor blood glucose (BG) via Dexcom Follow and xDrip Sync Follow
- Alert a parent/guardian ONLY when BG drops below a configured threshold
- BG numbers are NEVER displayed in any UI, notification text, or log — internal use only

## Data Sources to KEEP
- Dexcom Follow collector
- xDrip Sync Follow (REST follower)

## What to REMOVE (gradually, in separate branches)
- All other CGM collectors (G4, G5, G6 direct, Libre, Medtronic, etc.)
- All graph/chart views
- Calibration features
- Nightscout/Mongo sync
- Smartwatch support
- Treatments/insulin tracking
- Any UI that displays a numeric BG value

## Privacy Rule (most important)
BG values must NEVER be shown in the main app UI, history, or graphs.
The child's ongoing BG data is private.

EXCEPTION: When a low alert fires, the notification sent to the parent/guardian
MAY include the current BG value so they can gauge urgency.
e.g. "⚠️ Low Alert — Emma's BG is 52 mg/dL"

BG values must NOT appear anywhere else — no home screen, no widget,
no log, no settings screen.

## Alert Logic to KEEP
- Configurable low threshold alert (e.g. 55 mg/dL)
- Urgent low alert (e.g. 40 mg/dL)
- No-data / sensor lost alert
- Snooze functionality

## License
GPL v3 — fork of xDrip+ by NightscoutFoundation