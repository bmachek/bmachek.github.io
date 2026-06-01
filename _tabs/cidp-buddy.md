---
icon: fas fa-notes-medical
title: CIDP Buddy
permalink: /cidp-buddy/
order: 5
description: >-
  CIDP Buddy is a free Flutter app for CIDP patients to manage infusions, medications,
  supply inventory, appointment schedules, and a vitals and symptom diary.
---

<!-- SoftwareApplication + FAQ structured data for rich results -->
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@type": "SoftwareApplication",
      "name": "CIDP Buddy",
      "operatingSystem": "Android, iOS",
      "applicationCategory": "HealthApplication",
      "description": "Free Flutter app for patients with Chronic Inflammatory Demyelinating Polyneuropathy (CIDP) to manage infusions, medications, supply inventory, schedules, and a vitals and symptom diary.",
      "url": "https://blog.fokuspunk.de/cidp-buddy/",
      "downloadUrl": "https://github.com/bmachek/CIDPbuddy/releases",
      "author": { "@type": "Person", "@id": "https://blog.fokuspunk.de/#person", "name": "Bastian Machek" },
      "license": "https://www.gnu.org/licenses/gpl-3.0.html",
      "offers": { "@type": "Offer", "price": "0", "priceCurrency": "USD" }
    },
    {
      "@type": "FAQPage",
      "mainEntity": [
        {
          "@type": "Question",
          "name": "What is CIDP Buddy?",
          "acceptedAnswer": { "@type": "Answer", "text": "CIDP Buddy is a mobile app for patients with Chronic Inflammatory Demyelinating Polyneuropathy (CIDP). It helps manage complex infusion and medication schedules, track supply inventory, and record vitals and symptoms in a diary." }
        },
        {
          "@type": "Question",
          "name": "What platforms does CIDP Buddy support?",
          "acceptedAnswer": { "@type": "Answer", "text": "CIDP Buddy is built with Flutter and targets Android and iOS." }
        },
        {
          "@type": "Question",
          "name": "Is CIDP Buddy free?",
          "acceptedAnswer": { "@type": "Answer", "text": "Yes. CIDP Buddy is free and open source, released under the GNU General Public License v3.0. Source code is available at github.com/bmachek/CIDPbuddy." }
        },
        {
          "@type": "Question",
          "name": "What types of medications does CIDP Buddy support?",
          "acceptedAnswer": { "@type": "Answer", "text": "CIDP Buddy supports both infusion-based treatments (IVIG/SCIG) and pill-based medications, with batch tracking, inventory management, automated scheduling, and low-stock warnings." }
        }
      ]
    }
  ]
}
</script>

![CIDP Buddy Feature Graphic](/assets/img/cidp-buddy/cidpbuddy_feature_graphic.png){: width="100%" style="border-radius: 12px; margin-bottom: 1.5rem;" }

<img src="/assets/img/cidp-buddy/app_icon.png" alt="CIDP Buddy Logo" style="width: 72px; border-radius: 16px; float: left; margin: 0 1rem 0.5rem 0;" />

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

### Screenshots

<div style="display: flex; gap: 1rem; flex-wrap: wrap; margin-bottom: 1.5rem;">
  <img src="/assets/img/cidp-buddy/Screenshot_1.png" alt="CIDP Buddy Dashboard" style="width: 200px; border-radius: 16px; box-shadow: 0 4px 16px rgba(0,0,0,0.15);" />
  <img src="/assets/img/cidp-buddy/Screenshot_2.png" alt="CIDP Buddy Settings" style="width: 200px; border-radius: 16px; box-shadow: 0 4px 16px rgba(0,0,0,0.15);" />
</div>

### Tech Stack

- **Framework:** [Flutter](https://flutter.dev/)
- **Database:** [Drift](https://drift.simonbinder.eu/) (SQLite) for reactive local storage
- **State management:** [Provider](https://pub.dev/packages/provider)
- **Notifications:** [flutter_local_notifications](https://pub.dev/packages/flutter_local_notifications)
- **Charts:** [FL Chart](https://pub.dev/packages/fl_chart) for health data visualization

### License

Released under the **GNU General Public License v3.0**.

### Frequently asked questions

**What is CIDP Buddy?**

CIDP Buddy is a mobile app for patients with **Chronic Inflammatory Demyelinating Polyneuropathy (CIDP)**. It helps manage complex infusion and medication schedules, track supply inventory, and record vitals and symptoms in a diary that you can share with healthcare providers.

**What platforms does CIDP Buddy support?**

CIDP Buddy is built with [Flutter](https://flutter.dev/) and targets **Android and iOS**.

**Is CIDP Buddy free?**

Yes. CIDP Buddy is free and open source, released under the **GNU General Public License v3.0**. Source code is at [github.com/bmachek/CIDPbuddy](https://github.com/bmachek/CIDPbuddy).

**What types of medications does CIDP Buddy support?**

CIDP Buddy supports both **infusion-based treatments** (IVIG/SCIG) and **pill-based medications**, with batch tracking, supply inventory, automated scheduling, and low-stock warnings.

---
*Developed with care for the CIDP community.*
