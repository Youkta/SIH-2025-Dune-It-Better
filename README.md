# 🏖️ Automated Beach Sand Grain Mapping System

> **Smart India Hackathon 2025 | Problem Statement 25037 | Dune It Better**  
> *Low-cost, portable, camera-based automated mapping of beach sand grain characteristics*

**Duration:** Aug 2025 – Oct 2025  
**Competition:** Smart India Hackathon 2025  
**Team:** Dune It Better  
**Problem Statement:** Development of a low-cost camera-based automated beach sand grain size mapping system  
**Category:** Hardware

🔗 [SIH 2025](https://tinyurl.com/sih25dune)

---

## 📌 Overview

Manual beach sediment sampling typically requires collecting sand samples, transporting them to a laboratory, and performing physical grain-size analysis. This makes large-scale and frequent monitoring expensive, slow, and difficult to standardize.

We designed a **low-cost, portable beach sand mapping system** that combines:

- 📷 Standardized camera-based image capture
- 📍 GNSS/GPS-based geo-tagging
- 🧠 Automated image processing and ML classification
- 📐 Marker-based pixel-to-length calibration
- 💡 Illumination and haze correction
- 💾 Local + cloud-based data storage
- 🗺️ Spatially tagged beach classification

The system is designed to replace repetitive manual sampling and laboratory analysis with **rapid, repeatable, on-site digital measurements**.

The proposed solution targets three beach regions:

**Berm · Intertidal · Dune**

---

# 🎯 Problem Statement

Coastal environments are highly dynamic. Tides, storms, erosion, and seasonal changes can continuously alter sediment characteristics.

Traditional grain-size analysis creates several bottlenecks:

- Manual sample collection
- Laboratory-based analysis
- High labour requirements
- Slow turnaround
- Difficulty scaling measurements across multiple locations
- Lack of standardized spatially tagged measurements

The SIH problem statement specifically called for a **low-cost camera-based automated beach sand grain-size mapping system**.

---

# 💡 Our Solution

We proposed a portable imaging platform mounted on a **tetrapod structure** with standardized markers.

```text
                    ┌─────────────────────┐
                    │   Beach Sand Area   │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │ Standardized Image  │
                    │ Capture (~42 cm)    │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │ Image Preprocessing │
                    │                     │
                    │ • ArUco alignment  │
                    │ • Pixel calibration│
                    │ • Object masking   │
                    │ • Illumination     │
                    │ • Haze correction  │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │ Grain Analysis      │
                    │                     │
                    │ • Segmentation      │
                    │ • Grain detection   │
                    │ • Feature extraction│
                    │ • Distribution      │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │ ML Classification  │
                    │                     │
                    │ Berm / Intertidal   │
                    │ / Dune              │
                    └──────────┬──────────┘
                               │
                    ┌──────────┴──────────┐
                    ▼                     ▼
             📍 GNSS Tagged          ☁️ Cloud /
                Results                💾 SD Card
