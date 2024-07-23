## Modelling the Progression of World Records in Athletics - Events over Middle Distances

### Introduction

This data analysis project focuses on modeling the progression of world record times in athletics for middle-distance sprint events for both men and women. By analyzing record times over the years, this study aims to provide insights into the variation and trends of world record times, which can serve as useful guidance for future athletes. The research seeks to explain the changes in world record times over time.

### Aim and Questions of Interest

- **What was the trend in the progression of world record times over the years for athletics over middle distances?**
- **Are the patterns of progress in the events different for men and women?**
- **Are the patterns of progress in each of the events different for men and women?**

### Libraries Used

- **tidyverse**: A collection of R packages designed for data science, used for data manipulation and visualization.
- **moderndive**: Tools for tidy data analysis and linear regression, used for building and interpreting regression models.
- **gapminder**: Provides data on global health and economics, used for additional context in analyses.
- **sjPlot**: Data visualization for statistics in social sciences, used for creating plots.
- **stats**: Base R package for statistical calculations, used for various statistical tests and models.
- **jtools**: Tools for summarizing and visualizing regression models, used for detailed regression output.
- **dplyr**: A grammar of data manipulation, used for data wrangling.
- **zoo**: Provides infrastructure for regularly and irregularly spaced time series, used for date manipulation.
- **kableExtra**: Provides a way to build complex HTML tables, used for creating summary tables.
- **scales**: Tools for scales and transformations, used for axis formatting in plots.
- **gridExtra**: Provides functions to arrange multiple grid-based figures on a page, used for arranging multiple plots.
- **janitor**: Simple tools for data cleaning, used for cleaning and examining data.
- **tinytex**: Lightweight and easy-to-maintain LaTeX distribution, used for creating PDF reports.
- **hrbrthemes**: Additional themes and theme components for ggplot2, used for enhancing plot aesthetics.
- **viridis**: Color scales for scientific visualization, used for creating colorblind-friendly plots.
- **ggrepel**: Provides geoms for ggplot2 to repel overlapping text labels, used for better labeling in plots.
- **lubridate**: Functions to work with date-times, used for handling and manipulating date data.
- **ggfortify**: Data visualization tools for statistical models, used for autoplot functions.
- **gtsummary**: Create publication-ready tables, used for summarizing data and models.
- **car**: Companion to applied regression, used for regression diagnostics.
- **mgcv**: Mixed GAM computation vehicle, used for fitting generalized additive models.
- **MASS**: Functions and datasets to support Venables and Ripley's MASS, used for statistical methods.
- **mgcViz**: Visualizations for GAM models, used for plotting results of GAMs.
- **gratia**: Tools for working with GAMs, used for diagnostic and visualization plots.

### Data Preparation and Cleaning

Data for men and women in three different middle-distance events (400m, 800m, and 1500m) were cleaned and transformed to ensure consistency and usability for analysis. Key steps included:
- Reading CSV files for each event.
- Selecting relevant columns and converting date formats.
- Creating summary statistics for record times.

### Exploratory Data Analysis

Exploratory analysis was conducted for each event:
- Scatter plots to visualize the progression of record times over the years.
- Bar graphs to show the number of athletes from different countries.
- Density plots to examine the distribution of athletes' ages when records were set.

### Regression Analysis

Linear models were fitted to understand the relationship between date and record times. Diagnostics were performed to assess the fit and assumptions of the models. Additionally, transformations such as log transformations and percentage transformations were applied to improve model fit.

### Generalized Additive Models (GAMs)

GAMs were used to model non-linear relationships between the date and record times. Different methods, including GCV, REML, and ML, were compared to select the best-fitting model. Visualizations of the fitted GAM models were created to interpret the results.

### Comparisons

Comparative analyses were performed:
- Between men and women for each event.
- Across different events to understand patterns of progression.
- Using both linear and non-linear models to identify the best approach for modeling the data.

### Conclusion

The study initially attempted to fit linear regression models which are parametric and not flexible
enough to depict the entire structure of the progression of record times over the years.
The research elaborated here on the world record data for athletics has shown that generalised
additive models have the flexibility to capture the entire nonlinear trend observed in the decline
of the response variable record time over the date covariate. The transformed explanatory
variable Elapsed has a negative smooth relation with the response variable Time for all the event
categories considered. The estimated effective degrees of freedom of the smooth terms across all
the categories have been significantly higher than 1 confirming the presence of the smooth term
for the covariate. Deviance explained values very close to 100 accentuate the robustness of the
models. Consistent values of estimated effective degrees of freedom for individual categories for
men and women have been observed using different methods of selecting smoothing parameter
of generalised additive model which strengthens the findings that gams provide good explanation
of the progress of the record times.
Among the record times for all categories for men, the highest effective degrees of freedom were
observed in the 400 metres category, closely followed by 1500 metres. The effective degrees of
freedom value for 800 metres category were found to be the lowest suggesting a nearly linear
trend with slight curvature in some regions. The plots of the models also align with the
inferences obtained numerically.
Comparing the models fitted for women for the different categories of events analysed, the
highest effective degrees of freedom was observed for 800 metres category. The effective
degrees of freedom of the model for 400 metres is marginally higher than the value for 1500.
Comparing the partial effect plots of 400 metres category for men and women separately, the
record times for men shows a continuous negative trend with increase in Elapsed covariate. In
the case of women, the trend shows a steep decline till the value of Elapsed of around 57 and a
slight increase for a short range up to a value corresponding to the value of Elapsed of around 60
and thereafter almost linear decline in the value of response is observed. Adaptive smoothing
applied to the model for women aided to capture the linear and nonlinear trends in the data.
Considering the partial effect plots for the category 800 metres for men and women separately,
the plot for men indicates a nearly linear trend with slight curvature along the range of the
covariate. The plot indicates a steady nonlinear decline of the response variable record time. The
partial effect of the plot for women obtained shows that the record time decreases till the value of
around 40 of the Elapsed covariate. After 40, the value of response increases till about 48 of
Elapsed and thereafter it decreases almost linearly further.
The partial effect plots for 1500 metres for men shows that the response time decreases till the
value of around 50 of the transformed explanatory variable Elapsed, where a shift in the curve is
observed and a nonlinear pattern is observed over a short range of Elapsed until the value of 60.
Beyond the value of 60 of Elapsed explanatory variable, the response shows a general linear
decline in values. This also necessitated the usage of adaptive smoothing to capture the varying
trend of linearity and non-linearity to be captured and the flexibility of generalised additive
models to be utilised completely. However, in the case of women, a general linear negative trend
was observed till Elapsed value of 80 after which the curve flattens out due to sparsity of points
in the region.
