# Alzheimer-s-Brain-Scan-Analysis
Turning brain scan features into visual insights using Power BI. A data-driven look at Alzheimer’s progression through entropy, brightness, and structural changes.

---

## Why This Project

Alzheimer's is often diagnosed after symptoms appear, but subtle brain changes start much earlier. I wanted to explore whether brain scan image data (converted into structured form) could tell a story about disease progression

My goal: Can I analyze brain scans with Power BI and extract meaningful insights from image features?

---

## About the Dataset

| Detail       | Description                                                                          |                   |
| ------------ | -----------------------------------------------------------------------------------  | ----------------- |
| **Source**   | Preprocessed brain scan dataset (from YouTube tutorial by \[@AnalysisWithEmmanuel])  |                   |
| **Rows**     | 43,303 scans total (Real: 39,687                                                     | Augmented: 3,616) |
| **Features** | Entropy, Edge Density, Center Brightness, Mean/Std Pixel Intensity                   |                   |
| **Labels**   | NonDemented, VeryMildDemented, MildDemented, ModerateDemented                        |                   |
| **Other**    | `is_augmented` boolean column to distinguish synthetic data                          |                   |

---

## Methodology: How I Transformed Image Data Into Insights

| Step                       | What I Did                                                                    | Why It Matters                                       |
| -------------------------- | ----------------------------------------------------------------------------- | ---------------------------------------------------- |
| **Severity Score**         | Encoded disease stages as 0—3                                                 | Created a numeric way to average and trend stages    |
| **Composite Severity**     | Combined entropy, edge detail, and brightness into one score                  | Provided a visual-health metric for each scan        |
| **Custom DAX Measures**    | Built KPIs for severity, entropy, brightness, scan type, and disease coverage | Powered the dashboard insights                       |
| **User Experience Design** | Added image carousels, searchable tables, and card visuals                    | Made the dashboard explorable and clinician-friendly |

---

## What I Found

### 1. “Invisible” Alzheimer’s Patterns Made Visible

* **Disease Coverage**: 44.6% of scans show some level of degeneration.
* **Average Severity Score**: 1.50
* **Scan Disorder Level (Entropy Avg)**: 2.92

> Nearly 1 in 2 scans is affected, and image entropy confirms structural complexity drops as disease severity increases.

---

### 2. Brightness & Contrast as Early Markers

* **Healthy scans** (NonDemented): Brightness avg = 82, Contrast = 79
* **Mild/Moderate scans**: Brightness falls below 70

> As the disease progresses, the scans become visually darker and flatter. These changes are quantifiable and could power early alert systems.

---

### 3. Balanced Dataset For Model Training

* **Stage Distribution**:

  * NonDemented: 25.35%
  * VeryMildDemented: 25.20%
  * MildDemented: 24.76%
  * ModerateDemented: 24.68%

> This even spread makes the dataset ideal for AI/ML benchmarking without biasing the model toward one stage.

---

### 4. Visual vs. Statistical Health Confirmed

* Most visually healthy scans had high brightness, edge clarity, and entropy
* Visually severe scans had structural collapse and low contrast

> CompositeSeverity matched the medical labels remarkably well—proving its value as a visual health score.

---

### 5. Sharpness Loss Mirrors Cognitive Decline

| Stage            | Avg Edge Detail |
| ---------------- | --------------- |
| NonDemented      | 1,067           |
| VeryMildDemented | 926             |
| MildDemented     | 782             |
| ModerateDemented | 739             |

> The sharper the brain edges, the healthier the structure. That detail fades as the disease worsens.

---

## Dashboard Highlights

* **KPI Strip**: Total scans, % real, avg entropy, brightness, and disease coverage
* **Image Carousel**: Top 5 healthy and diseased scans based on CompositeSeverity
* **Visual Breakdown**: Line + bar charts showing entropy, brightness, and edge decline across stages
* **Searchable Table**: Explore scan stats and filenames, filterable by any metric
* **Label Comparison**: Stack chart shows synthetic data use by mean and standard deviation pixel intensity 

---

## Final Takeaways

* Alzheimer’s patterns *can* be detected from brain scan data without seeing the images
* Brightness, contrast, and entropy are early and reliable predictors of severity
* CompositeSeverity is a trustworthy scoring model
* Visual data can *enhance* diagnostic understanding when translated into numbers

---

## Tools Used

* Power BI (for dashboard & DAX logic)
* CSV file (preprocessed scan features)
* GitHub (for documentation and versioning)

---

## Links

* [Power BI Dashboard File](#)
* [DAX Measures & Logic](./measures/DAX_Measures_Alzheimers.txt)
* Credit: Tutorial by \[@YouTuberHandle]


