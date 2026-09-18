# HarvestSense

**AI Pre-Sale Decision Layer for Smallholder Farmers, Integrated with Existing Agri-Logistics Aggregators**

Hack2Ignite 2026 — Problem Statement ID: **AG-05**
Team: **SRISAK** (Jayasri B, Sakthi S)
Institution: Sri Eshwar College of Engineering, Coimbatore

---

## 1. Problem

Post-harvest loss for perishable produce in India runs at an estimated **20–30%**, largely because smallholder farmers have no decision support at the point of harvest. Existing agri-logistics aggregators digitize *what happens after* a farmer decides to sell — collection, routing, retail distribution — but nobody helps with the decision itself: **sell now, hold, or route to which buyer**, before the produce spoils.

## 2. Proposed Solution

HarvestSense is a computer-vision-based decision layer that sits **before** a farmer's produce enters an existing aggregator's logistics pipeline:

1. Farmer photographs freshly harvested produce on their phone.
2. A CV model estimates **ripeness stage** and **spoilage risk window**.
3. A scoring engine cross-references nearby buyer price data and produces an explainable **sell / hold / route** recommendation.
4. If "sell now" is recommended, the graded listing (grade, urgency, location) is pushed via API into an aggregator's existing procurement queue — instead of waiting for manual on-site grading at a collection point.

### What makes this different
- **No new logistics network.** We don't compete with aggregators — we plug the one decision gap they don't address (pre-sale, farm-gate) into a queue they already run.
- **No IoT hardware required.** Spoilage/ripeness is estimated from a photo, not sensor hardware — keeping per-farmer cost near zero.
- **Explainable, not a black-box dashboard.** The recommendation shows its reasoning (spoilage curve, price trend, distance to buyer) in a form a non-technical user can trust — built for the farmer, not an enterprise analyst.

## 3. Technical Approach

| Layer | Technology |
|---|---|
| Produce grading / spoilage detection | YOLO / CNN-based image classification |
| Backend | Python, FastAPI (REST API) |
| Frontend (farmer-facing app) | React |
| Scoring / recommendation engine | Lightweight rule-based or optimization module |
| Aggregator integration | Sandbox layer simulating an aggregator's procurement API |

**Flow:** Photo capture → CV grading & spoilage-stage output → scoring engine → sell/hold/route recommendation → structured listing pushed via API to aggregator's procurement queue → aggregator's existing pickup/routing takes over.

## 4. Feasibility & Scope

- Demo scoped to **2–3 high-loss perishable crops** (tomato, banana, leafy greens) rather than all produce.
- CV model trained/fine-tuned on public produce-freshness datasets (e.g. PlantVillage-style image sets).
- Live buyer price data substituted with public mandi price data where real-time aggregator data isn't accessible.
- Aggregator integration demonstrated via a **documented mock API contract** — not a confirmed live partnership. The module is designed to be pluggable with any aggregator, not tied to one specific platform.

## 5. Impact

- **Economic:** Reduces spoilage loss before pickup, improving farmer payout and the quality of supply reaching aggregators.
- **Social:** Extends decision-support technology to smallholders — a segment enterprise agri-logistics platforms don't serve directly.
- **Environmental:** Less spoiled produce means less wasted water, land, and inputs already invested in that harvest.

## 6. References

- Post-harvest loss statistics for perishables in India (~20–30%) — NABARD / ICAR post-harvest loss studies
- Public produce-freshness / crop-image datasets (e.g. PlantVillage) used as CV model reference
- Comparative review of existing tech-enabled agri-logistics aggregator platforms

## 7. Team

| Name | Role |
|---|---|
| Jayasri B | Team member |
| Sakthi S | Team member |

---
