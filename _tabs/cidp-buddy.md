---
icon: fas fa-notes-medical
title: CIDP Buddy
permalink: /cidp-buddy/
order: 7
description: >-
  CIDP Buddy by Bastian Machek (Fokuspunk): organise infusions, medication,
  supplies and a symptom diary. A free app built from personal experience with CIDP.
image: /assets/img/cidp-buddy/cidpbuddy_feature_graphic.png
project_schema: cidp-buddy
faq:
  - q: "What is CIDP Buddy?"
    a: "CIDP Buddy is a mobile app for patients with Chronic Inflammatory Demyelinating Polyneuropathy (CIDP). It helps manage complex infusion and medication schedules, track supply inventory, and record vitals and symptoms in a diary."
  - q: "What platforms does CIDP Buddy support?"
    a: "CIDP Buddy is built with Flutter and targets Android and iOS."
  - q: "Is CIDP Buddy free?"
    a: "Yes. CIDP Buddy is free and open source, released under the GNU General Public License v3.0. Source code is available at github.com/bmachek/CIDPbuddy."
  - q: "What types of medications does CIDP Buddy support?"
    a: "CIDP Buddy supports both infusion-based treatments (IVIG/SCIG) and pill-based medications, with batch tracking, inventory management, automated scheduling, and low-stock warnings."
---



![CIDP Buddy Feature Graphic](/assets/img/cidp-buddy/cidpbuddy_feature_graphic.png){: width="100%" style="border-radius: 12px; margin-bottom: 1.5rem;" }

<img src="/assets/img/cidp-buddy/app_icon.png" alt="CIDP Buddy Logo" style="width: 72px; border-radius: 16px; float: left; margin: 0 1rem 0.5rem 0;" />

**CIDP Buddy** is a medication and symptom management app for patients with **Chronic Inflammatory Demyelinating Polyneuropathy (CIDP)**. It helps manage complex infusion schedules, keep track of medication and supply inventory, and monitor health through a vitals and symptom diary.

**Source:** [github.com/bmachek/CIDPbuddy](https://github.com/bmachek/CIDPbuddy) · [Issues](https://github.com/bmachek/CIDPbuddy/issues)

## Why I built CIDP Buddy

I live with CIDP myself. Keeping treatment dates, supplies and everyday observations together is the practical problem behind this app. Read more [about me, Bastian Machek / Fokuspunk]({{ '/about-me/' | relative_url }}).

For the app's data-handling details, see the [privacy policy (German)]({{ '/cidp-buddy/privacy/' | relative_url }}). Source and build instructions are available on GitHub; the Flutter project targets Android and iOS.

## Features

## Medication & Infusion Management
- Support for both **infusions** (IVIG/SCIG) and **pill-based** medications.
- **Batch tracking**: record batch numbers and body weight for every infusion for precise documentation.
- Complete **intake history** of all past treatments.

## Inventory & Supply Management
- **Smart stock tracking** — automatically decrements stock when doses are logged.
- **Accessory management** for medical supplies (needles, syringes, etc.) linked to specific medications.
- **Low-stock warnings** with visual indicators based on "days remaining" logic.

## Smart Scheduling
- Flexible plans: daily, weekly, interval-based, or specific weekdays.
- **Automated appointments** generated from your defined rhythm.
- **Local notifications** as precise reminders for upcoming intakes.

## Vitals & Symptom Diary
- Track **blood pressure, heart rate, temperature, and body weight**.
- **CIDP-specific metrics** for strength, sensory, fatigue, pain, and balance.
- **History view** for trends and notes you can share with healthcare providers.

## Order Wizard
- **Automated calculations** for what to order based on current stock and upcoming requirements.
- **Delivery tracking** — manage pending orders and confirm deliveries to update inventory automatically.

## Screenshots

<div style="display: flex; gap: 1rem; flex-wrap: wrap; margin-bottom: 1.5rem;">
  <img src="/assets/img/cidp-buddy/Screenshot_1.png" alt="CIDP Buddy Dashboard" style="width: 200px; border-radius: 16px; box-shadow: 0 4px 16px rgba(0,0,0,0.15);" />
  <img src="/assets/img/cidp-buddy/Screenshot_2.png" alt="CIDP Buddy Settings" style="width: 200px; border-radius: 16px; box-shadow: 0 4px 16px rgba(0,0,0,0.15);" />
</div>

## Tech Stack

- **Framework:** [Flutter](https://flutter.dev/)
- **Database:** [Drift](https://drift.simonbinder.eu/) (SQLite) for reactive local storage
- **State management:** [Provider](https://pub.dev/packages/provider)
- **Notifications:** [flutter_local_notifications](https://pub.dev/packages/flutter_local_notifications)
- **Charts:** [FL Chart](https://pub.dev/packages/fl_chart) for health data visualization

## License

Released under the **GNU General Public License v3.0**.

## Frequently asked questions

{% for item in page.faq %}
### {{ item.q }}

{{ item.a }}
{% endfor %}

{% include project-author.html %}
