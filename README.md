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

## Statistical report example

```
HeadTailBreaks Classification
================================
Class Intervals:
3.32, 7.46, 14.24, 26.18, 44.22, 72.92, 102.81, 137.50, 175.00, 193.00, 209.00

Counts in Each Class:
35526, 9207, 2494, 634, 192, 45, 16, 7, 1, 1, 1

Statistical indicators for power law:

Alpha: 3.309509932226023
xmin: 11.0
p-value: 0.02965726847632788
Log-likelihood ratio (R): 235.27082552021437
p-value for comparison: 1.59652417146201e-14
```

## Example Plot

![Example Plot](figure_Yogyakarta.png)
![Example Plot](histogram_0.png)
![Example Plot](power_Bandung.png)

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Contribution

Feel free to submit issues or pull requests if you find bugs or want to add new features.

## Credits

Tutorial from Momepy package website at http://docs.momepy.org/en/stable/user_guide/graph/coins.html based on paper by Tripathy et al. (2020)

OpenAI. (2024). ChatGPT (version 4) [Large language model]. OpenAI. https://openai.com/chatgpt

Tripathy, P., Rao, P., Balakrishnan, K., & Malladi, T. (2020). An open-source tool to extract natural continuity and hierarchy of urban street networks. Environment and Planning B: Urban Analytics and City Science. http://dx.doi.org/10.1177/2399808320967680

Guo, Z. (n.d.). Tutorial for generating natural streets and analyzing their scaling structure. Faculty of Engineering and Sustainable Development, Division of GIScience, University of Gävle. Retrieved from https://livablecitylab.hkust-gz.edu.cn/binjiang/Axwoman/TutorialNaturalStreets14.pdf
---

