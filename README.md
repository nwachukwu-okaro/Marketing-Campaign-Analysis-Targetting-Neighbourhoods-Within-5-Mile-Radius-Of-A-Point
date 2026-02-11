# Marketing-Campaign-Analysis-Targetting-Neighbourhoods-Within-5-Mile-Radius-Of-A-Point
This project was commissioned to identify and map all residential subdivisions located within a 5-mile radius of the I-71 & KY-393 interchange in Buckner, Kentucky.

The project did not require individual parcel or property-level addresses, only one geospatial reference point per neighborhood.

This project demonstrates applied geospatial analysis, data sourcing, geocoding, spatial filtering, cartographic design, and project packaging using ArcGIS Pro.

# 🧠 Business Case

Understanding neighborhoods within a defined radius of a transportation interchange supports:

Market analysis

Sales territory planning

Infrastructure planning

Real estate strategy

Targeted outreach campaigns

Logistics and accessibility studies

Rather than mapping thousands of addresses, the solution focused on subdivision-level geographic representation, reducing data complexity while preserving decision-making value.

# 🛠 Tools & Technologies Used

ArcGIS Pro

Geocoding services

Spatial analysis tools (Buffer, Select by Location, Near)

Data management tools

Layout & cartographic tools

Project packaging (.ppkx)

CSV export

# 📊 Data Acquisition Challenges

One of the core technical challenges was the absence of a single authoritative dataset listing all subdivisions in Oldham County.

Multiple datasets were reviewed, including:

Public GIS repositories

Real estate subdivision listings

Open spatial datasets

County GIS layers

No single dataset fully captured all subdivision names. As a result:

Data validation and cross-referencing were required

Name inconsistencies were resolved (e.g., Lake Pointe vs Lake Point)

Missing subdivisions were manually geocoded

This reflects real-world GIS data integration work.

# 🗺 Step-by-Step Methodology
**1. Geocoding the Target Intersection**

The intersection of I-71 & KY-393 was geocoded in ArcGIS Pro.

The coordinate system was projected to ensure accurate distance calculations (State Plane / UTM projection recommended).

This point served as the spatial anchor for the analysis.

**2️. Creating the 5-Mile Radius Buffer**

A 5-mile buffer was generated around the intersection using the Buffer tool.

Units were verified to ensure true ground distance (not degrees).

The buffer polygon defined the study area.

**3️. Subdivision Data Compilation**

Because no single authoritative layer existed:

Subdivision names were compiled from multiple sources.

Datasets were reviewed for subdivision-related fields (e.g., SUBDIV_NAME, PLAT_NAME).

Names were standardized to resolve spelling variations.

Example normalization:

Lake Pointe → Lake Point

Farmhouse Estate → Farmhouse Estates

North Ridge → North Ridge Farms (where applicable)

This step ensured consistency in reporting.

**4️. Geocoding Subdivision Locations**

Each subdivision was represented by one point (centroid-style representation).

Process:

Subdivision names were geocoded.

Where automated geocoding failed, representative addresses were used.

Coordinates were validated against aerial basemaps.

This produced a clean subdivision point layer.

**5️. Spatial Filtering (Proximity Analysis)**

To identify subdivisions within the required radius:

“Select By Location” was used.

Criteria: Points within 5 miles of the intersection.

Only qualifying subdivisions were exported.

Alternative validation:

Near analysis was run to compute exact distances.

Distances were converted to miles and verified.

This ensured spatial accuracy.

**6️. Attribute Enhancement**

Each subdivision was assigned:

Unique Map ID

Standardized Name

Latitude

Longitude

Distance from intersection (optional field for QA)

Lat/Long were calculated using the “Add XY Coordinates” tool.

**7️. Cartographic Design & Labeling**

Professional map layout included:

5-mile radius boundary

Subdivision points

Unique numeric labels

Clear legend

Scale bar

North arrow

Clean symbology

Map index table listing Map ID + Name + Coordinates

Map readability was enhanced using:

Halo labeling

Maplex Label Engine

Offset labeling for dense areas

This ensured print-ready clarity.
