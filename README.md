Cape Town Airbnb Data Pipeline

From messy to meaningful: cleaning, transforming and visualising Cape Town Airbnb data with Python.

A group project for ICE262S Data Science (ICT Electives 2) at the Cape Peninsula University of Technology (CPUT), 2026. The notebook demonstrates three consecutive stages of the Data Science Pipeline on one real, messy dataset:

Data Cleaning: detecting and correcting (or removing) inaccurate, incomplete or irrelevant records
Data Transformation: feature engineering, encoding and scaling
Data Exploration & Visualisation: descriptive statistics and charts that reveal patterns, trends and outliers
Dataset

Inside Airbnb: Cape Town, Western Cape, South Africa, detailed listings (listings.csv.gz), scraped 25–27 September 2026. Licensed under Creative Commons Attribution 4.0 (CC BY 4.0).

The data file is not included in this repository. Download listings.csv.gz for Cape Town from the Inside Airbnb "Get the Data" page.

What the pipeline does
Stage	Highlights
Cleaning	27,760 listings × 90 columns → 24,888 clean listings × 25 columns. Dropped 14 empty columns, removed 47 properties listed twice, converted text prices ("$1,114.00", actually in rand) to numbers, handled missing values column by column, and removed 17 implausible prices using a price-per-guest rule instead of the IQR rule (which would have deleted 10.8% of genuine listings).
Transformation	New features (price per guest, multi-listing host, size band), one-hot encoding for room type, ordinal encoding for size band, and a comparison of MinMax, Standard and Robust scaling.
Visualisation	Price distribution before and after cleaning, price by room type, top 10 wards, a map from latitude and longitude, a correlation heatmap, and individual vs. multi-listing hosts.
Key findings (September 2026)
A typical night costs about R1,900 (median R1,908; the mean of R3,641 is pulled up by luxury villas).
Entire homes make up 84% of listings.
Ward 115 (City Centre / Green Point) alone has over a fifth of all listings.
Size drives price: bathrooms (r = 0.58), guest capacity (0.56) and bedrooms (0.52) correlate most with price.
64% of listings belong to hosts with more than one listing.
How to run
Install Python 3.10+ and the libraries:
pip install jupyterlab pandas numpy matplotlib seaborn scikit-learn
Put listings.csv.gz in the same folder as cape_town_airbnb_pipeline.ipynb.
Start JupyterLab in that folder:
jupyter lab
Open the notebook and choose Kernel → Restart Kernel and Run All Cells.

Running it creates a charts/ folder with all six charts as PNGs, plus cape_town_listings_clean.csv and cape_town_listings_transformed.csv.

No install? Open the notebook in Google Colab, upload listings.csv.gz in the files panel, then choose Runtime → Run all.

Repository structure
cape-town-airbnb-pipeline/
├── cape_town_airbnb_pipeline.ipynb   # the full pipeline, with outputs
├── charts/                           # chart images (created when the notebook runs)
├── .gitignore                        # keeps the data files out of the repo
└── README.md
Team
Role	Member
Python lead and coordinator -	Katlego Mokgofa
Theory and slides -	Mosa Lejaka
Storyboard and video editing - Musa Mbhalati
Introduction, reflection and quality checks  - Thozama Mgaqa

Acknowledgements
Data: Inside Airbnb, CC BY 4.0
Libraries: pandas, NumPy, Matplotlib, Seaborn, scikit-learn
Course material: CPUT ICE262S Data Science notes
AI use: this project was developed with assistance from Claude (Anthropic). All code and findings were reviewed by the group.
