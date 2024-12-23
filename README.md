# Natural street analysis and power law fitting 


## Features

- uses polygon delineating city borders to extract OSM road data
- performs natural street analysis (segments are calculated with deflection angle) and number of connecting streets is determined for each segment
- calculates head/tail distribution of these streets
- fit the distribution to a power law

## Requirements

The following Python libraries are required to run the code:

- `geopandas`
- `matplotlib`
- `powerlaw`
- `shapely`
- `osmnx` (optional, depending on your data processing needs)

You can install these dependencies using:

```bash
pip install geopandas matplotlib powerlaw shapely osmnx
```

## Usage

1. **Load a Shapefile**
   Ensure your shapefile contains geometries (one polygon representing each city) and name of city for each geometry in the attribute table

2. **Run the Script**
   Update the script with the path to your shapefile and output folder. The key steps include:

   - Downloading OSM street data inside the shape file polygons
   - Calculating natural streets and their connectivity
   - Calculating head/tail distribution for the streets
   - Fitting a power-law distribution to the calculated degree values.
   - Saving the resulting plots to the specified folder.

3. **Output**
   - Processed GeoDataFrame with valid geometries and connection counts.
   - Power-law fit parameters (`alpha`, `xmin`) and comparison metrics.
   - Shape file for natural streets, png of the streets, pnf of the histogram, png of the power law fit

## Example Plot

![Example Plot](figure_0.png)
![Example Plot](histogram_0.png)

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Contribution

Feel free to submit issues or pull requests if you find bugs or want to add new features.

## Credits

Tutorial from Momepy package website at http://docs.momepy.org/en/stable/user_guide/graph/coins.html based on paper by Tripathy et al. (2020)

OpenAI. (2024). ChatGPT (version 4) [Large language model]. OpenAI. https://openai.com/chatgpt

Tripathy, P., Rao, P., Balakrishnan, K., & Malladi, T. (2020). An open-source tool to extract natural continuity and hierarchy of urban street networks. Environment and Planning B: Urban Analytics and City Science. http://dx.doi.org/10.1177/2399808320967680

---

