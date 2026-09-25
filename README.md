# 🏖️ Automated Beach Sand Grain Mapping System

> **Smart India Hackathon 2025 | Problem Statement 25037 | Dune It Better**

**Duration:** Aug 2025 – Oct 2025  
**Category:** Hardware  
**Team:** Dune It Better

[SIH Project](https://tinyurl.com/sih25dune)

---

## 📌 Overview

Manual beach sediment sampling and laboratory grain-size analysis are time-consuming and difficult to scale across diverse coastal locations.

We proposed a **low-cost, portable, camera-based mapping system** that automates beach sand analysis using standardized image capture, computer vision, machine learning, and GNSS tagging.

The system targets three beach regions:

- **Berm**
- **Intertidal**
- **Dune**

### Key Highlights

- 📷 Standardized imaging at approximately **42 cm**
- 📍 GNSS/GPS geo-tagging
- 📐 1 × 1 ft standardized measurement area
- 🧠 Automated computer vision + ML pipeline
- 💾 Offline SD-card storage + cloud connectivity
- 💰 Prototype BOM of approximately **₹10.9K**
- 📊 Approximately **3,000 samples**
- 🎯 **0.72 Macro F1** on the presented test split

---

# 🎯 Problem

Traditional beach sediment analysis involves:

- Manual sample collection
- Physical transportation of samples
- Laboratory analysis
- Significant labour
- Slow measurement cycles
- Difficulty performing repeated large-scale monitoring

This limits rapid monitoring of sediment changes caused by **tides, storms, erosion, and seasonal variations**.

---

# 💡 Proposed Solution

A portable camera system mounted on a standardized tetrapod captures sand images at a fixed height.

The captured image is processed automatically to:

1. Reorient and calibrate the image.
2. Segment the sand region.
3. Detect individual grains.
4. Estimate grain-size distribution.
5. Extract image features.
6. Classify the beach region.
7. Attach GNSS coordinates to the measurement.

The result is a **geo-tagged digital beach measurement** instead of a manually processed physical sample.

# 🔧 Hardware Architecture

### Core Components

| Component | Purpose |
|---|---|
| Raspberry Pi 5 | Main processing platform |
| Raspberry Pi Camera | Image acquisition |
| GNSS/GPS | Geographic tagging |
| Wi-Fi | Cloud communication |
| SD Card | Offline storage |
| LED Strip | Controlled illumination |
| Power Source | Portable operation |
| Tetrapod | Standardized camera positioning |
| ArUco Markers | Orientation and scaling |

---

# 📐 Standardized Imaging

A fixed imaging geometry was used to make measurements repeatable across different beach locations.

### Capture Setup

- Camera height: **~42 cm**
- Field of view: **~75°**
- Measurement area: **1 × 1 ft**
- ArUco markers for orientation and scaling

### Why Standardization?

Different camera positions produce different pixel-to-physical-size relationships.

The standardized setup provides:

**Fixed Geometry → Marker Detection → Pixel Calibration → Comparable Measurements**

The tetrapod also incorporates LED strips to reduce shadows and improve illumination consistency.

---

# 🧠 Computer Vision Pipeline

### Image Processing

**Raw Image**  
→ ArUco Reorientation  
→ Pixel-to-Length Calibration  
→ Object / Background Masking  
→ Illumination & Haze Correction  
→ Grain Segmentation  
→ Grain Instance Detection  
→ Feature Extraction  
→ Grain Distribution Estimation

### Segmentation

The proposed approach considers:

- Watershed segmentation
- Convolution-based segmentation
- U-Net based segmentation

These methods are used to isolate individual grain structures from the captured sand image.

# 🤖 Machine Learning

The ML pipeline was developed using approximately **3,000 samples**.

### Models Compared

- Decision Tree
- Support Vector Machine (SVM)
- Logistic Regression

The **Decision Tree** approach was selected after comparing model performance.

### Class Imbalance

**SMOTE oversampling** was used to mitigate class imbalance and improve model generalization.

---

# 📊 Classification Results

| Class | Precision | Recall | F1 |
|---|---:|---:|---:|
| Berm | 0.87 | 0.80 | 0.83 |
| Intertidal | 0.72 | 0.76 | 0.74 |
| Dune | 0.50 | 0.67 | 0.57 |
| **Macro Average** | **0.70** | **0.74** | **0.72** |
| Weighted Average | 0.79 | 0.78 | 0.79 |

The presented test split achieved a **0.72 Macro F1**.

---

# 📍 Geo-Tagged Mapping

Each measurement is associated with a geographic position using GNSS/GPS.

### Mapping Flow

**Image Capture + GNSS Coordinates**  
→ Geo-tagged Measurement  
→ Spatial Dataset  
→ Coastal Monitoring

This enables repeatable, location-aware measurements across different beach regions.

The concept also considers **Sentinel-2 imagery** for identifying coastline changes and locations that may require renewed mapping.

# 💾 Offline + Cloud Workflow

Field locations may not always have reliable connectivity.

### Online Mode

**Camera → Raspberry Pi → Wi-Fi → Cloud Processing / Storage**

### Offline Mode

**Camera → Raspberry Pi → SD Card → Upload When Connectivity Returns**

This allows measurements to continue even when network connectivity is unavailable.

---

# 💰 Prototype Cost

| Component | Approx. Cost |
|---|---:|
| Raspberry Pi 5 | ₹6,240 |
| Camera Module | ₹2,800 |
| GPS Module | ₹230 |
| Power Bank | ₹799 |
| 32 GB SD Card | ₹479 |
| Push Button | ₹50 |
| LED Strip | ₹224 |
| **Total** | **₹10,864** |

The prototype was designed around a low-cost hardware architecture suitable for portable field deployment.

---

# 🧰 Technology Stack

### Hardware
- Raspberry Pi 5
- Raspberry Pi Camera
- GNSS/GPS
- Wi-Fi
- SD Card
- LED illumination

### Computer Vision
- Python
- OpenCV
- ArUco markers
- Watershed segmentation
- Image calibration
- Illumination and haze correction

### Machine Learning
- Decision Trees
- SVM
- Logistic Regression
- SMOTE
- Cross-validation
- Grid Search

### Development
- Google Colab
- Python
- Fusion 360

---

# 🎯 Product Perspective

The project was designed not only as an ML pipeline, but as a **field-deployable coastal monitoring product**.

### Potential Users

- Coastal researchers
- Environmental monitoring teams
- Government agencies
- Coastal management authorities
- Citizen-science programs

### User Workflow

**Place Device**  
→ **Capture Standardized Image**  
→ **Automatic Processing**  
→ **Beach Classification**  
→ **GNSS Tagging**  
→ **Store / Upload Result**

The goal is to minimize the expertise and manual effort required between field measurement and usable coastal data.

---

# ⚙️ Feasibility

### Technical

- Raspberry Pi 5 provides the processing platform.
- Image preprocessing can be performed locally.
- Lightweight ML models can support edge deployment.
- Standardized imaging improves repeatability.

### Economic

The approximately **₹10.9K prototype BOM** supports the low-cost deployment objective.

### Operational

The system supports:

- Offline data collection
- Local buffering
- GNSS tagging
- Automated processing
- Periodic model retraining

---

# ⚠️ Limitations

Current challenges include:

- Wet sand
- Shadows
- Variable lighting
- Haze
- Shells and debris
- Limited training-data diversity
- GPS positional errors
- Lack of a fully developed user GUI

Model performance is dependent on the diversity and quality of the traidepends
# 🚀 Future Improvements

### Touchscreen GUI

A Raspberry Pi touchscreen could provide:

- Live camera feed
- Real-time classification
- Measurement results
- System controls

### Citizen Science

Users could contribute standardised beach images using a defined capture protocol, continuously expanding the dataset.

### Improved Positioning

Multiple nearby measurements could be combined to reduce positional uncertainty.

### Continuous Model Improvement

**New Field Data**  
→ Ground Truth Validation  
→ Dataset Expansion  
→ Model Retraining  
→ Improved Generalisation

---

# 🌊 Impact

The system aims to make coastal monitoring:

- **Faster** through automated analysis
- **Repeatable** through standardized imaging
- **Non-destructive** through image-based analysis
- **Geo-tagged** through GNSS integration
- **Scalable** through portable deployment
- **Data-driven** through reusable image datasets

The project also considered the broader **Political, Economic, Social, Technological, Environmental and Legal (PESTEL)** impact of large-scale coastal monitoring.

---
