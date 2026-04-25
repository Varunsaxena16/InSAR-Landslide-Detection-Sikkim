# InSAR-Based Landslide Detection — Gangtok & North Sikkim Corridor

Surface deformation monitoring and landslide detection over East Sikkim and the
Gangtok–North Sikkim corridor using multi-temporal Sentinel-1 SAR interferometry.
The SBAS-InSAR technique was applied to both ascending and descending Sentinel-1
frames (January 2020 – December 2025) and processed using MintPy, enabling
pixel-level time-series analysis of Line-of-Sight (LOS) displacement.

**Author:** Varun Saxena | NSUT  
**Study Area:** East Sikkim (Gangtok region) + Gangtok–Mangan corridor, North Sikkim  
**Data:** Sentinel-1 IW (Ascending + Descending) | Jan 2020 – Dec 2025  
**Method:** SBAS-InSAR | MintPy | OpenSAR Platform  
**Status:** Ongoing | Rainfall integration planned

---

## Study Area

The study area covers East Sikkim centred on Gangtok, extending northward along the
Gangtok–North Sikkim highway corridor into parts of Mangan district. The region is
characterised by:

- Steep Himalayan terrain with highly fractured geology
- Active tectonic setting with proximity to major fault systems
- Intense monsoon rainfall (one of the highest in India)
- Dense road network along narrow valley corridors highly vulnerable to slope failure
- History of repeated, large-scale landslide events causing road blockages,
  infrastructure damage, and fatalities

---

## Methodology

### SAR Data

| Parameter | Details |
|-----------|---------|
| Satellite | Sentinel-1A/B |
| Mode | Interferometric Wide (IW) Swath |
| Polarisation | VV |
| Orbits | Ascending + Descending |
| Time Period | January 2020 – December 2025 |
| Temporal Resolution | ~12 days |

### Processing Pipeline

**Technique:** Small Baseline Subset (SBAS-InSAR)  
**Software:** MintPy (Miami InSAR Time-series software in Python)  
**Platform:** Local processing + OpenSAR cloud platform

Key processing and correction steps implemented:

| Step | Description |
|------|-------------|
| Interferogram generation | Multi-looked, filtered interferometric stack |
| Atmospheric correction | Atmospheric Phase Screen (APS) mitigation |
| Phase unwrapping | Refined unwrapping with error correction |
| Reference point selection | Stable reference point on coherent bedrock |
| Temporal coherence masking | Low-coherence pixels masked before inversion |
| Time-series inversion | SBAS least-squares inversion for deformation history |

### Outputs
- Mean LOS velocity maps (ascending + descending)
- Pixel-level monthly displacement time-series
- Identification of high negative LOS velocity zones correlated with landslide sites

---

## Results

### LOS Velocity Range

Observed mean LOS velocities across the study area ranged from **−13 cm/year**
(strong subsidence / slope movement toward sensor) to **+11 cm/year** (uplift /
movement away from sensor).

High negative LOS velocity zones (< −5 cm/year) were identified at multiple locations
and cross-validated against documented landslide events.

### Validated Landslide Sites

High negative LOS velocities in both ascending and descending frames were detected
at the following documented landslide locations:

| Location | Documented Event | InSAR Signal |
|----------|-----------------|--------------|
| Tathangchen | Slow-moving landslide (2020–2025) | ~8–10 cm/year subsidence |
| Dikchu | Major landslide Mar 2023 | High negative LOS |
| Sangtok | Jun & Sep 2025 events | High negative LOS |
| Tumlong | Multiple events, N. Sikkim highway | High negative LOS |
| Nampong | Recurrent highway corridor failure | High negative LOS |
| Ramthang | Active deformation zone | High negative LOS |
| Tshalumthang | Jul 2022 event | High negative LOS |
| Upper Burtuk | Jun 2021 landslide | High negative LOS |
| Lower Burtuk / Raigaon | Sep 2024 event | High negative LOS |
| Tibuk | Jun 2024 & Jun 2025 major events | High negative LOS |

Full details, event documentation, and sources are in `Recent_Landslide_Table.docx`.

### Tathangchen Time-Series Analysis

Tathangchen was selected as the primary validation site for detailed time-series
analysis due to its well-documented slow-moving landslide behaviour and high
temporal coherence across the monitoring period.

Pixel-level monthly LOS displacement time-series revealed both gradual creep trends
and episodic displacement events. Yearly mean LOS velocities:

| Year | Mean LOS Velocity (cm/yr) | Median LOS Velocity (cm/yr) |
|------|--------------------------|------------------------------|
| 2020 | −7.92 | −8.41 |
| 2021 | −11.40 | −11.71 |
| 2022 | −9.29 | −8.13 |
| 2023 | −8.65 | −8.89 |
| 2024 | −6.27 | −6.36 |
| 2025 | −2.16 | −4.17 |

Peak subsidence of **−11.40 cm/year** was recorded in 2021, followed by a
progressive deceleration through 2025 (−2.16 cm/year), indicating evolving
slope dynamics over the monitoring period.

---

## Repository Files

| File | Description |
|------|-------------|
| `Recent_Landslide_Table.docx` | Documented landslide events at 10 validated sites with InSAR signal characterisation and sources |
| `tathangchen_yearly_velocity.csv` | Annual mean and median LOS velocity at Tathangchen (2020–2025) |
| `tathangchen_validation.png` | Tathangchen deformation analysis figure — time-series and spatial context |

---

## Future Work

- [ ] Rainfall time-series integration for trigger-based displacement correlation
- [ ] Early-warning signal detection based on deformation rate thresholds
- [ ] Extension to full Sikkim coverage
- [ ] 3D decomposition of LOS velocities (ascending + descending → vertical + horizontal)
- [ ] Deep learning-based automated deformation anomaly detection

---

## Tools & References

- **MintPy** — Miami InSAR Time-series software in Python
- **OpenSAR** — Cloud-based SAR processing platform
- **Sentinel-1** — ESA Copernicus SAR mission (IW mode, VV polarisation)
- **SBAS** — Small Baseline Subset technique for multi-temporal InSAR
- **SNAP** — ESA Sentinel Application Platform (preprocessing)

---

## Related Work

This InSAR deformation dataset is being used in conjunction with:
- **Landslide Susceptibility Mapping — Sikkim** (RF + XGBoost, accepted ICCDRH 2026)
- **Landslide Detection using Deep Learning on Multispectral and SAR Satellite Imagery**
  (Hybrid CNN-ResNet50, accepted 12th ISFMG, Springer Nature 2026)
