# Programming in R Final Project

Advise a bike-share operations manager preparing for the 2013 season, using two years of daily rental data.

**The scenario, the manager's questions, and the required evidence are in Blackboard.** This README contains the data guide. Write your report in **RFinalProject.Rmd**, which contains the report's section headings and the evidence map.

## Getting started

- Open the cloned repository in RStudio. Keep `data-raw/day.csv` in its provided location.
- Use the R Markdown tooling from earlier assignments and the `tidyverse` and `broom` packages. Install missing packages in the Console.
- Keep the Blackboard instructions and this data guide open while you work.

## Data guide

**Use the codes and conversions in this data guide.** The original dataset's documentation labels the seasons differently. Do not use those labels. Recode `season` using the table below.

Use **data-raw/day.csv**. Keep the original CSV unchanged and use relative paths.

Each row represents one day of Capital Bikeshare rentals in Washington, DC, from 2011-01-01 through 2012-12-31. The following fields are available for this project:

| Field | Meaning |
|:--|:--|
| `dteday` | Date |
| `season` | 1 = winter, 2 = spring, 3 = summer, 4 = fall (use these labels, not the original dataset's) |
| `yr` | Year: 0 = 2011, 1 = 2012 |
| `mnth` | Month: 1 = January, …, 12 = December |
| `weekday` | Day of the week: 0 = Sunday, 1 = Monday, …, 6 = Saturday |
| `holiday` | 1 = public holiday, 0 = not a holiday |
| `workingday` | 1 = working day (a weekday that is not a holiday); 0 = non-working day (a weekend day or a holiday) |
| `weathersit` | Weather: 1 = clear or partly cloudy, 2 = mist or cloudy, 3 = light rain or light snow, 4 = heavy rain or snow |
| `temp` | Scaled daily temperature. Create `temp_c` (°C) by multiplying `temp` by 41 |
| `hum` | Scaled humidity. Create `humidity_pct` (%) by multiplying `hum` by 100 |
| `windspeed` | Scaled wind speed. If you use it, create `wind_kmh` (km/h) by multiplying `windspeed` by 67 |
| `casual` | Daily rentals by casual users |
| `registered` | Daily rentals by registered users |
| `cnt` | Total daily rentals |

Fields not listed are not needed for this project.

- Recode `season` as a factor with the labels above. You choose its reference category; state it clearly wherever you interpret season comparisons.
- Use `temp_c`, `humidity_pct`, and `wind_kmh` in place of the scaled columns whenever you use temperature, humidity, or wind speed in a model. Keep the original scaled columns in your data.
- Use `cnt` as the response in your required regression models. Do not use `casual` or `registered` as predictors of `cnt`: they are the two parts that add up to it (`casual + registered = cnt`), so a model using them would "predict" the total from its own pieces.

Source: Hadi Fanaee-T, *Bike Sharing*, UCI Machine Learning Repository, [doi:10.24432/C5W894](https://doi.org/10.24432/C5W894).

## Submitting

- Complete every section of **RFinalProject.Rmd**, including the evidence map.
- Restart R and knit to HTML. Resolve errors and investigate warnings. Read the HTML report to check that all code, relevant output, plots, and answers appear correctly.
- Once all errors are resolved, restart R and knit one final time. Your report must run from top to bottom on its own, without relying on anything you ran separately in the Console.
- Commit and push both **RFinalProject.Rmd** and **RFinalProject.html**. Keep `data-raw/day.csv` in its original location.
- Verify both files on GitHub, then submit your repository URL in Blackboard.

See Blackboard for the deadline and grading rubric.
