# Alzheimer’s Brain‑Scan Dashboard — From Pixels to Powerful Insights

Turning brain‑scan features into visual insights with **Power BI**. A data‑driven look at Alzheimer’s progression through entropy, brightness and structural change.

---

## Table of Contents

1. [Why This Project](#why-this-project)
2. [About the Dataset](#about-the-dataset)
3. [Methodology](#methodology-how-i-transformed-image-data-into-insights)
4. [What I Found](#what-i-found)
5. [Dashboard Highlights](#dashboard-highlights)
6. [Dashboard Preview](#dashboard-preview)
7. [Final Takeaways](#final-takeaways)
8. [Tools Used](#tools-used)
9. [Links](#links)

---

## Why This Project

Alzheimer’s is often diagnosed after symptoms appear, yet subtle brain changes start much earlier. I set out to test whether **raw MRI‑image features**—brightness, entropy, edge density—could surface those early signals.

My driving question: *Can a data analyst (not a radiologist) translate pixels into actionable Alzheimer’s insights with Power BI?*

---

## About the Dataset

   | Detail       | Description                                                                                                    |                 
   | ------------ | -------------------------------------------------------------------------------------------------------------- | 
   | **Source**   | Pre‑processed MRI feature CSV (from [this YouTube tutorial](https://youtu.be/LBWEPKwunnI?si=qXWMrXs-SMKhsKqO)) |                  
   | **Rows**     | 43 303 scans (Real 39 687, Augmented 3 616)                                                                    |                               
   | **Features** | Entropy • Edge Density • Center Brightness • Mean / Std Pixel Intensity                                        |                  
   | **Labels**   | NonDemented • VeryMildDemented • MildDemented • ModerateDemented                                               |                  
   | **Other**    | `is_augmented` flag distinguishes synthetic images                                                             |                  

---

## Methodology: How I Transformed Image Data Into Insights

| Step                   | What I Did                                                  | Why It Matters                            |
| ---------------------- | ----------------------------------------------------------- | ----------------------------------------- |
| **Severity Score**     | Encoded stages 0 – 3                                        | Enables numeric trending of disease level |
| **Composite Severity** | 0.4 × Entropy + 0.3 × Edge + 0.3 × Center Brightness        | One glance measure of visual brain health |
| **Custom DAX**         | KPIs for severity, entropy, brightness, scan type, coverage | Drives all metrics                        |
| **UX Design**          | Image carousel, searchable table, card visuals              | Makes insights clinician‑friendly         |

---

## What I Found

### 1. “Invisible” Alzheimer’s Patterns Made Visible

* **Disease Coverage** 44.6 % of scans show degeneration.
* **Average Severity** 1.50
* **Entropy Avg** 2.92

> Nearly 1 in 2 scans is affected; entropy drops as severity rises.

### 2. Brightness & Contrast as Early Markers

* **Healthy Brightness** ≈ 82  •  **Contrast** ≈ 79
* **Mild/Moderate Brightness** < 70

> Scans darken and flatten as disease progresses.

### 3. Balanced Dataset for Model Training

Even 25 % share across all four stages → minimal class bias.

### 4. Visual vs Statistical Health Align

CompositeSeverity tracks labels; high score = structurally degraded scan.

### 5. Sharpness Loss Mirrors Cognitive Decline

| Stage       | Avg Edge Detail |
| ----------- | --------------- |
| NonDemented | 1 067           |
| VeryMild    | 926             |
| Mild        | 782             |
| Moderate    | 739             |

---

## Dashboard Highlights

* **KPI Strip** – Total scans • % Real • Avg Entropy • Brightness • Disease Coverage
* **Image Carousel** – Top 5 healthiest vs diseased (CompositeSeverity rank)
* **Visual Breakdown** – Line & bar charts for entropy, brightness, edge decline
* **Searchable Table** – Filter any filename, metric, stage
* **Label Comparison** – Stacked chart of synthetic vs real pixel‑intensity stats

---

## Dashboard Preview
                                                                                          
<p align="center">
  <img src="https://github.com/Olowookere-Abidemi/Alzheimer-s-Brain-Scan-Analysis/blob/main/OVERVIEW.jpg" width="45%" alt="Dashboard Overview" />
  <img src="https://github.com/Olowookere-Abidemi/Alzheimer-s-Brain-Scan-Analysis/blob/main/SPREADSHEET.jpg" width="45%" alt="Spreadsheet View" />
</p>

🔗 **[Download the Power BI DAX Code](https://github.com/Olowookere-Abidemi/Alzheimer-s-Brain-Scan-Analysis/blob/main/DAX_Measures_Alzheimers.txt)**

---

## Final Takeaways

* Raw MRI features can flag Alzheimer’s long before clinical symptoms.
* Brightness, contrast and entropy are early, reliable markers.
* CompositeSeverity is a practical visual‑health score.
* Translating pixels to numbers brings clarity for clinicians and AI teams alike.

---

## Tools Used

* **Power BI** – visuals & DAX logic
* **CSV** – pre‑processed scan features
* **GitHub** – documentation & versioning

---

## Links

* 📄 **[Power BI DAX Measures](https://github.com/Olowookere-Abidemi/Alzheimer-s-Brain-Scan-Analysis/blob/main/DAX_Measures_Alzheimers.txt)**
* 🎥 **[Tutorial Video](https://youtu.be/LBWEPKwunnI?si=qXWMrXs-SMKhsKqO)**

## Try the Interactive Dashboard

🔗 [View the Alzheimer’s Brain Scan Dashboard in Power BI](https://app.powerbi.com/reportEmbed?reportId=46ca28fc-d26f-4d7f-961a-d3f07df06a16&autoAuth=true&ctid=66b3f0c2-8bc6-451e-9603-986f618ae682)

Explore the full dashboard online — scroll through key metrics, disease severity trends, and visual breakdowns of over 43,000 brain scans. Use filters, and see insights come alive.

---

*Not a radiologist. Just a data analyst learning to make pixels speak.*
