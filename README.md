
# 🏔️ Snow Cover and Glacier Change Mapping — Kolahoi Glacier, Kashmir
### Satellite-Based Cryosphere Monitoring for Water Security, Glacial Lake Hazard Assessment, and Upstream Flood Risk

---

## 🔍 Why This Matters

Kolahoi Glacier — the largest glacier in the Kashmir Valley and the primary perennial source of the Jhelum River — is retreating. It is not retreating slowly. Studies over the past four decades document a **significant reduction in both area and volume**, with retreat accelerating measurably since the 1990s. For the Kashmir Valley, this is not an abstract environmental concern. Kolahoi feeds the Lidder River, which sustains agriculture, drinking water supply, and hydropower for millions of people across a region already under severe climatic and political stress.

The cryosphere — glaciers, seasonal snow, and permafrost — functions as a **natural water tower** across the Hindu Kush Himalaya (HKH), storing winter precipitation and releasing it as meltwater during the dry summer months when river flows would otherwise collapse. As this storage is depleted by warming, the consequences cascade across sectors: **irrigation systems fail, hydropower output declines, downstream flood peaks shift seasonally, and glacial lake outburst flood (GLOF) risk rises** as meltwater accumulates in unstable proglacial lakes.

This project uses multi-temporal satellite imagery to map snow cover extent and glacier boundary changes at Kolahoi — producing a quantified record of cryosphere change with direct implications for water resource planning, GLOF early warning, and upstream flood risk assessment in the Jhelum basin.

---

## 📌 Key Outputs

| Output | Description |
|---|---|
| **Snow cover extent maps** | Seasonal and inter-annual mapping of snow-covered area (SCA) using NDSI |
| **Glacier boundary delineation** | Multi-date glacier outlines showing area change over the study period |
| **Area change quantification** | Net glacier area loss in km² and % over study period |
| **Snow line altitude (SLA) estimation** | Elevation of the transient snow line as a proxy for equilibrium line altitude (ELA) |
| **Change detection map** | Visual overlay of glacier retreat zones — stable, retreating, and newly exposed rock |

> **Headline finding:** *[Insert your key result here — e.g. "Kolahoi Glacier retreated by X km² (Y%) over the study period YYYY–YYYY, with the most rapid retreat recorded on the southern and southwestern margins. Snow cover area declined by Z% in peak summer extent compared to the baseline period."]*

---

## 🛰️ Methodology

### Why Remote Sensing for Glaciers?

Ground-based glacier monitoring in high-altitude Himalayan terrain is expensive, logistically extreme, and geographically sparse. Satellite remote sensing provides the only **systematic, repeatable, and spatially continuous** method for monitoring glacier change across the HKH at the scale and frequency needed for meaningful trend analysis.

### Two Core Indices

**1. Normalised Difference Snow Index (NDSI)**
Used to separate snow and ice from rock, soil, and cloud:

```
NDSI = (Green − SWIR) / (Green + SWIR)
```

- NDSI > 0.4 typically indicates snow/ice presence
- Applied to cloud-free late-summer (August–September) imagery to capture minimum snow extent
- Minimum snow extent scenes separate glacier ice from seasonal snowpack — isolating the perennial glacier body

**2. Normalised Difference Vegetation Index (NDVI)**
Used as a complementary mask to exclude vegetated pixels misclassified as snow-free glacier in shadow areas.

### Processing Workflow

```
Multi-temporal Landsat / Sentinel-2 archive
            ↓
Scene selection: cloud-free, late-summer (Aug–Sep)
            ↓
NDSI computation → snow/ice binary mask (threshold > 0.4)
            ↓
Shadow correction using DEM hillshade mask
            ↓
Glacier boundary extraction (manual refinement of debris-covered margins)
            ↓
Multi-date boundary overlay → change detection
            ↓
Area statistics: total area, retreat zones, newly exposed terrain
            ↓
Snow line altitude (SLA) estimation using DEM intersection
            ↓
Validation against field records / published inventories (ICIMOD, SAC)
```

### The Debris-Cover Challenge

A critical methodological challenge in Kolahoi and all Himalayan glacier mapping is **supraglacial debris cover** — rock material that insulates underlying ice and renders it spectrally indistinguishable from bare rock in optical imagery. Debris-covered glacier tongues are systematically underestimated by automated NDSI approaches. This project applies manual boundary refinement at debris-covered margins, cross-referenced with DEM-derived slope and thermal anomaly data where available — a standard practice recommended by the Global Land Ice Measurements from Space (GLIMS) protocol.

---

## 🗂️ Data Sources

| Dataset | Sensor | Source | Resolution |
|---|---|---|---|
| Landsat 5 TM / 7 ETM+ / 8-9 OLI | Optical multispectral | [USGS EarthExplorer](https://earthexplorer.usgs.gov) | 30m |
| Sentinel-2 MSI | Optical multispectral | [Copernicus Hub](https://scihub.copernicus.eu) | 10m |
| SRTM DEM / FABDEM | Elevation | [NASA / Univ. Bristol](https://data.bris.ac.uk/data/dataset/s5hqmjcdj8yo2ibzi9b4ew3sn) | 30m |
| ICIMOD Glacier Inventory | Reference boundaries | [ICIMOD HKH-HYCOS](https://www.icimod.org) | Vector |
| SAC Glacier Atlas of India | Validation | [Space Applications Centre, ISRO](https://www.sac.gov.in) | Vector |

All primary satellite data are **freely and publicly available**. The full workflow is reproducible using open-access imagery.

---

## 📂 Repository Contents

```
kolahoi-glacier-snow-cover-mapping/
│
├── SNOW COVER MAPPING OF KOLAHOI GLACIER.pdf    # Full project report — methodology,
│                                                 # maps, area statistics, and results
└── README.md                                     # This file
```

> **Note:** Analytical scripts developed in Google Earth Engine (GEE) will be added in the next release. Contact via LinkedIn or email if you need the processing code in the interim.

---

## 🌐 Relevance to Cryosphere, Water Security, and Upstream Flood Risk

### Water resource planning and basin hydrology

Kolahoi Glacier is not merely an environmental indicator — it is **critical infrastructure**. Its meltwater contribution to the Lidder and Jhelum Rivers sustains:
- Kharif and Rabi irrigation for the Kashmir Valley's agricultural sector
- Drinking water supply for Srinagar and surrounding urban areas
- Baseflow for hydropower projects on the Jhelum and its tributaries

Accelerating glacier retreat means that **meltwater contribution will increase in the short term as the glacier shrinks, then collapse** once the ice volume is insufficient to sustain summer flows — a pattern termed "peak water," projected to occur for many HKH glaciers before mid-century. Baseline area change data from this project feeds directly into the hydrological models needed to anticipate and manage this transition.

Organisations working on this problem: **World Bank (HKH Water Security Programme), ICIMOD, UNDP, ADB (South Asia Subregional Economic Cooperation), National Water Mission (India), Jal Shakti Ministry.**

### Glacial lake outburst flood (GLOF) risk

As glaciers retreat, meltwater accumulates in proglacial lakes held by unstable moraine dams. These lakes can fail catastrophically — releasing millions of cubic metres of water within hours. GLOFs are among the most destructive and difficult-to-forecast natural hazards in the Himalayas, with documented events causing hundreds of deaths and destroying entire downstream villages.

Accurate glacier boundary mapping is a **prerequisite for GLOF hazard assessment**:
- Identifies zones of active retreat where new proglacial lake formation is likely
- Provides the baseline glacier geometry needed to model ice dam stability
- Feeds into early warning system design for downstream communities

Organisations working on GLOF risk: **NDMA, J&K SDMA, ICIMOD, SERVIR-HKH, UN Environment Programme (UNEP), Swiss Agency for Development and Cooperation (SDC).**

### Upstream flood risk and seasonality shift

Himalayan river flood regimes are changing as the ratio of **glacier melt to snowmelt to rainfall runoff** shifts with warming. Key flood risk implications:

- **Earlier peak discharge:** snowmelt-driven spring floods arriving weeks earlier than historical norms, before downstream flood infrastructure is prepared
- **Extended melt season:** late-summer glacier melt sustaining high flows into October, overlapping with retreating monsoon rainfall — compounding peak discharge
- **Increased glacial outburst contribution:** GLOFs superimposed on already elevated monsoon flows, generating extreme compound flood events (as seen in Chamoli 2021, Kedarnath 2013)

Snow cover and glacier extent maps from this project provide the **observational foundation** for understanding how these upstream dynamics are shifting — essential input for flood forecasting models used by IMD, CWC, and RIMES.

### Climate adaptation and cryosphere policy

- **National Action Plan on Climate Change (NAPCC):** National Mission for Sustaining the Himalayan Ecosystem (NMSHE) specifically mandates glacier monitoring as a priority action
- **Sendai Framework:** reduced GLOF mortality and property loss is a direct Target A/B contribution
- **SDG 6 (Clean Water) and SDG 13 (Climate Action):** glacier-fed water security is a frontline SDG challenge for HKH nations
- **IPCC AR6 (Chapter 4 — Water):** HKH cryosphere change identified as a "key risk" for South Asia under all warming scenarios

---

## 🔬 Tools and Technologies

| Tool | Purpose |
|---|---|
| **Google Earth Engine (GEE)** | Cloud archive access, NDSI computation, multi-temporal stack analysis, zonal statistics |
| **ArcGIS / QGIS** | Glacier boundary digitisation, DEM integration, cartographic output |
| **SNAP (ESA)** | Sentinel-2 pre-processing and atmospheric correction |
| **Python** | pandas, geopandas, matplotlib — area change statistics and trend visualisation |
| **GLIMS Glacier Database** | Reference and validation of glacier outlines |

---

## 📐 Methodological Alignment

This project follows protocols established by leading cryosphere monitoring institutions:

| Protocol / Standard | Organisation | Relevance |
|---|---|---|
| GLIMS Glacier Mapping Guidelines | NSIDC / USGS | Boundary delineation and attribute standards |
| Randolph Glacier Inventory (RGI 7.0) | Global consortium | Inventory format and classification |
| SAC Glacier Atlas of India | ISRO Space Applications Centre | National reference for Indian Himalayan glaciers |
| ICIMOD HKH Cryosphere Assessment | ICIMOD | Regional benchmark for HKH glacier change |
| IPCC SROCC (2019) | IPCC | Methodological context for glacier retreat assessment |

---

## 🔗 Connection to Broader Climate Risk

Glacier retreat at Kolahoi is one node in a system of cascading climate risks across the Jhelum basin. This project's outputs connect upstream to downstream:

```
Kolahoi Glacier retreat (this project)
        ↓
Reduced summer baseflow → agricultural water stress
        ↓
Proglacial lake expansion → GLOF hazard increase
        ↓
Seasonal flood regime shift → downstream peak flow change
        ↓
Urban and agricultural flood risk (→ connects to MS-THESIS urban flood work)
```

This upstream–downstream linkage is the foundation of **integrated basin-scale climate risk assessment** — the approach increasingly required by multilateral development banks and climate adaptation funds for project appraisal in mountain river systems.

---

## 🚧 Planned Additions

- [ ] Reproducible GEE script for NDSI-based snow cover mapping (Landsat + Sentinel-2)
- [ ] Glacier area change time series — tabular dataset with annual estimates
- [ ] Jupyter notebook: area change trend analysis and visualisation
- [ ] Proglacial lake detection layer using SAR (Sentinel-1) and optical change detection
- [ ] DEM-based slope analysis for GLOF susceptibility screening

---

## 👤 Author

**Waquar Ul Islam**  
MS by Research — Disaster Management, IIT Guwahati (CGPA 9.45)  
PG Diploma in Remote Sensing & GIS — IIRS-ISRO  
GATE Geomatics AIR-185  
NASA ARSET: Earth Observations for Humanitarian Applications · Fundamentals of ML for Earth Science  

🔗 [LinkedIn](https://linkedin.com/in/waquar-ul-islam) · [GitHub](https://github.com/WaquarIslam)  
📧 waquarulislam@gmail.com

---

## 📎 Related Work — Multi-Hazard Remote Sensing Portfolio

| Repository | Hazard / Domain | Core Method |
|---|---|---|
| [MS-THESIS](https://github.com/WaquarIslam/MS-THESIS) | Urban Flood | Probabilistic risk assessment, SewerGEMS, CMIP6 |
| [Cyclone-Shaheen-Oman-2021](https://github.com/WaquarIslam/Cyclone-Shaheen-Oman-2021-ongoing-project-) | Tropical Cyclone | SAR inundation, IBFWS, MERRA-2 reanalysis |
| [drought-monitoring-rajasthan-vci](https://github.com/WaquarIslam/drought-monitoring-rajasthan-vci) | Agricultural Drought | MODIS VCI, district-level severity mapping |
| [coastal-inundation-erosion-rs](https://github.com/WaquarIslam/coastal-inundation-erosion-rs) | Coastal Hazard | Shoreline change detection, SAR inundation |

---

*Methodology consistent with GLIMS glacier mapping protocols, ICIMOD HKH cryosphere assessment standards, and IPCC SROCC (2019) guidance on mountain glacier change detection.*
