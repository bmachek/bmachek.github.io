---
icon: fas fa-notes-medical
title: CIDP Buddy
permalink: /cidp-buddy/
order: 5
---

## CIDP Buddy

**CIDP Buddy** is a medication and symptom management app for patients with **Chronic Inflammatory Demyelinating Polyneuropathy (CIDP)**. It helps manage complex infusion schedules, keep track of medication and supply inventory, and monitor health through a vitals and symptom diary.

**Source:** [github.com/bmachek/CIDPbuddy](https://github.com/bmachek/CIDPbuddy) · [Issues](https://github.com/bmachek/CIDPbuddy/issues)

### Features

#### Medication & Infusion Management
- Support for both **infusions** (IVIG/SCIG) and **pill-based** medications.
- **Batch tracking**: record batch numbers and body weight for every infusion for precise documentation.
- Complete **intake history** of all past treatments.

#### Inventory & Supply Management
- **Smart stock tracking** — automatically decrements stock when doses are logged.
- **Accessory management** for medical supplies (needles, syringes, etc.) linked to specific medications.
- **Low-stock warnings** with visual indicators based on "days remaining" logic.

#### Smart Scheduling
- Flexible plans: daily, weekly, interval-based, or specific weekdays.
- **Automated appointments** generated from your defined rhythm.
- **Local notifications** as precise reminders for upcoming intakes.

#### Vitals & Symptom Diary
- Track **blood pressure, heart rate, temperature, and body weight**.
- **CIDP-specific metrics** for strength, sensory, fatigue, pain, and balance.
- **History view** for trends and notes you can share with healthcare providers.

#### Order Wizard
- **Automated calculations** for what to order based on current stock and upcoming requirements.
- **Delivery tracking** — manage pending orders and confirm deliveries to update inventory automatically.

### Tech Stack

- **Framework:** [Flutter](https://flutter.dev/)
- **Database:** [Drift](https://drift.simonbinder.eu/) (SQLite) for reactive local storage
- **State management:** [Provider](https://pub.dev/packages/provider)
- **Notifications:** [flutter_local_notifications](https://pub.dev/packages/flutter_local_notifications)
- **Charts:** [FL Chart](https://pub.dev/packages/fl_chart) for health data visualization

### License

Released under the **GNU General Public License v3.0**.

---
*Developed with care for the CIDP community.*
