# Avocado NDVI Study: Implementation Checklist

## 🟢 1. Precision Masking (Excluding Bare Soil)
To ensure your NDVI comparison isn't "polluted" by non-vegetated areas:
- **Visit geojson.io**: Go to https://geojson.io/ to create your vector boundaries.
- **Toggle Satellite View**: Switch the basemap to "Satellite" to see tree canopies clearly.
- **Trace Your AOI**: Use the Polygon tool to draw tight boundaries around the tree crowns, specifically excluding the bare dirt in the inter-row spaces.
- **Save the File**: Select Save > GeoJSON and name it (e.g., 'treated_water_mask.geojson').
- **Invoke in Python**: Load the file using 'geopandas.read_file()' and clip using 'rasterio.mask.mask()'.

## 🥑 2. Adapting for the Water Source Study
Compare Group 1 (Treated Groundwater) vs. Group 2 (Existing Clean Water):
- **Utility**: The notebook automates the multispectral math, allowing focus on biological results.
- **Dual-Masking**: Load two separate GeoJSON files to calculate Mean NDVI for each group independently for a fair "apples-to-apples" comparison.
- **Temporal Comparison**: Organize flights by 'Week #' and use a Python loop to run calculations across all flights in your folder.

## 🐍 3. The Python Advantage
- **Precision Filtering**: Programmatically ignore pixels with NDVI < 0.3 to "turn off" soil data automatically.
- **Automation**: Process an entire season of drone flights in seconds compared to manual GIS work.
- **Statistical Integration**: Directly link NDVI results to water logs (Flow, Chloride, etc.) for regression analysis.

## 📊 4. Advanced Analysis & Next Steps
Implement the regression model from the study:
- **Formula**: NDVI = β₀ + β₁(Flow) + β₂(Cl⁻) + β₃(week) + β₄(Et_o) + β₅(E_c)
- **Data Merging**: Combine weekly NDVI averages with independent variables (Flow, Chloride, Week, Et_o, and E_c).
- **Hypothesis Testing**: Use a T-test to determine if the difference between the two water sources is statistically significant.
