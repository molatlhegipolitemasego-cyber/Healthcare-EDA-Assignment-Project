# Healthcare Admissions: Exploratory Data Analysis Assignment-Project

## **Project Introduction**

- **Purpose:** Explore a hospital admissions dataset to understand who is admitted, what admissions cost, how long patients stay and how admissions change over time, and turn this into findings a hospital manager can use.
- **Dataset:** 55,500 admission records and 15 columns, covering May 2019 to May 2024. Each row is one admission, with patient, clinical, admission and billing details.
- **Data preparation:**
  - Removed 534 exact duplicates (0.96%), leaving 54,966 admissions.
  - Standardised patient names to proper case (for example "pOLIte aLf" becomes "Polite Alf") and removed stray commas from about 4,800 hospital names.
  - Converted the admission and discharge dates from text to dates.
  - Set 106 negative bills to missing instead of deleting the rows or changing the sign, because the correct amounts are unknown. The average bill changes by only about 0.2% under the alternative approach.
  - Found no missing values in the original data.
- **Features created:** length of stay, admission year, month and weekday, plus age group, billing bucket and stay category bands.
- **Tools:** Python, pandas, NumPy and Matplotlib in a Jupyter notebook.

## **Discussion of Findings**

- **Admissions are spread very evenly.**
  - Conditions range from 9,095 admissions (Asthma) to 9,218 (Arthritis), a gap of about 1.3%.
  - Admission types range from 18,102 (Emergency) to 18,473 (Elective).
  - Insurance providers range from 10,822 (Aetna) to 11,139 (Cigna).
  - No single condition, admission type or insurer dominates the workload.

- **Patients span all adult ages.** Ages run from 13 to 89 (median 52). Only 116 patients are under 18, so results for that group rest on few records.

- **Cost per admission barely varies.**
  - The average bill is about 25,600 (the dataset does not state a currency).
  - By condition, averages run from 25,206 (Cancer) to 25,859 (Obesity), a gap of about 2.6%.
  - By admission type, the gap is only about 0.4%.

- **Most stays are long and similar across conditions.**
  - The average stay is about 15.5 days, ranging only from 15.43 (Diabetes) to 15.68 (Asthma).
  - 42,080 admissions (about 77%) last 8 days or more.

- **Test results and medications show no strong pattern.** Each condition splits into roughly thirds for Normal, Abnormal and Inconclusive results (32.5% to 34.3%). All five medications are used at similar rates within every condition.

- **Admissions are steady over time.**
  - From 2020 to 2023, admissions stayed between 10,816 and 11,172 a year. 2019 and 2024 look lower only because the data covers part of each year.
  - July (4,765) and August (4,785) are the busiest months. February (4,210) is the quietest, partly because it is shorter.

- **Hospital and doctor names are not reliable.** There are about 39,900 hospital names and 40,300 doctor names, so the busiest hospital name has only 44 admissions and the busiest doctor 27. The top names are common surnames, so they cannot show who is really busiest.

- **Limitations:**
  - The analysis shows patterns, not causes.
  - The groups are unusually similar on volume, cost, stay length and test results. Real hospital data usually varies more, so the dataset may be simplified or sampled and this should be confirmed.
  - There is no information on treatment type or case severity, which would be needed to explain cost differences.
  - Billing figures
