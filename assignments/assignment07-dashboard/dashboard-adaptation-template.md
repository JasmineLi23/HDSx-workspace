# Dashboard Adaptation Note

## Audience

A public-health analyst preparing a short briefing on BMI patterns in the NHANES Health Equity classroom dataset.

## Dashboard Question

Among adults aged 20–80 in the classroom dataset, how does unweighted mean BMI vary across NHANES survey cycles for the selected income group?

## Control And Visualization

- Control or interaction:Edit selected_income in dashboard.qmd and render the file again.
- Visualization affected:The line chart of unweighted mean BMI by NHANES survey cycle.
- What changes when the control changes: The plot title names the selected income group, the plotted means update, and the summary table shows the counts and mean BMI for that group.

## Before And After

| Original text | Revised text | Why the revision helps |
| none (missing the table counting missing values|missing_by_column <- nhanes |>
  summarise(across(everything(), ~ sum(is.na(.x)))) |>
  pivot_longer(
    cols = everything(),
    names_to = "column",
    values_to = "n_missing"
  )

knitr::kable(
  missing_by_column,
  caption = "Missing values by column before dashboard filtering"
) | this tells us how many missing values are dropped in each column |
| Descriptive, unweighted classroom summary. Missing BMI, income group, cycle, and out-of-cohort ages are excluded. | Each point shows the unweighted mean BMI for adults aged 20-80 in the selected income group in one NHANES classroom survey cycle. Records with missing age, BMI, income group, or cycle, and records outside the age range, were excluded. | The caption tells the analyst what each point represents, which age range the chart covers, and which records were excluded. |

## Test Result

I tried Low Income (<1.3) and High Income (>3.5). Both plots showed 11 survey cycles. Switching to the high-income group changed the plotted values and the plot title. The low-income group’s displayed mean BMI was higher in every cycle shown.

## Limitation

The dashboard shows unweighted mean BMI by income group and survey cycle in the NHANES classroom dataset and cannot establish a causal effect of income on BMI.

## Privacy Check

The preview shows only aggregate mean BMI values by survey cycle. The interpretation stays at the group level and avoids claims based on small cells. The comparison describes patterns in the classroom dataset.
