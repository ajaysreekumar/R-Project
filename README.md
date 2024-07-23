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

- **Initial Linear Models**: Not flexible enough to capture the progression of record times over the years.
- **Generalized Additive Models (GAMs)**: Effectively captured the nonlinear trends in record times across different events.
- **Elapsed Variable**: Showed a consistent negative smooth relationship with record times.
- **Effective Degrees of Freedom**: Higher than 1 across all categories, confirming the presence of smooth terms for the covariate.
- **Deviance Explained**: Values close to 100% indicated robust models.
- **Consistency**: Effective degrees of freedom values were consistent across different smoothing parameter selection methods.
- **Men’s Records**: Highest degrees of freedom in 400m, followed by 1500m, with 800m showing the lowest (nearly linear trend).
- **Women’s Records**: Highest degrees of freedom in 800m, followed by 400m and 1500m.
- **Partial Effect Plots for Men**:
  - **400m**: Continuous negative trend with Elapsed.
  - **800m**: Nearly linear with slight curvature.
  - **1500m**: Initial nonlinear decline, shift at Elapsed ~50, then general linear decline.
- **Partial Effect Plots for Women**:
  - **400m**: Steep decline till Elapsed ~57, slight increase till ~60, then almost linear decline.
  - **800m**: Decrease till Elapsed ~40, increase till ~48, then linear decline.
  - **1500m**: Linear decline till Elapsed ~80, then curve flattens out due to sparsity of data points.
