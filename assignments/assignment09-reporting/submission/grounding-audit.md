## Grounding Audit

| Claim | Evidence type | Evidence location | Decision |
|---|---|---|---|
| Income information was missing more frequently than BMI among adults aged 20–80 in the prepared dataset. | Table/code | “Missingness check for key report variables” table and `missingness` calculation: 5,395 missing income values versus 1,009 missing BMI values among 57,137 records. | Keep. Do not infer why the values are missing. |
| The high-income group had a lower mean BMI than the low- and middle-income groups among adults aged 20–80 in the prepared dataset. | Table/figure | “Descriptive BMI summary by income group” table and “Mean BMI by income group” figure: high income 28.6, low income 29.4, and middle income 29.3. | Keep as an unweighted descriptive comparison; do not imply causation or statistical significance. |
| The low- and middle-income groups had very similar mean BMI values. | Table | “Descriptive BMI summary by income group” table: reported means of 29.4 and 29.3, respectively, differing by approximately 0.1 BMI units. | Keep, specifying that the comparison uses rounded sample means and does not establish equality of population means. |