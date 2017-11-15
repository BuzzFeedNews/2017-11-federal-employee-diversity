# Analysis of Political Appointee Demographics

This repository contains data and analysis supporting the BuzzFeed News article, "[The Agriculture Department Hired More Than 50 Political Appointees. They All Say They're White.](https://www.buzzfeed.com/jsvine/agriculture-department-political-appointee-diversity)," published November 15, 2017. See below for more details.

# Data

The data in this repository comes from [the Office of Personnel Management's FedScope tool](https://www.fedscope.opm.gov/). The data on racial/ethnic diversity come from FedScope's "[Diversity Cubes](https://www.fedscope.opm.gov/diversity.asp)", and the data on gender come from the "[Employment Cubes](https://www.fedscope.opm.gov/employment.asp)".

## Raw data

The files in the [`data/raw`](data/raw) directory were obtained by using each of those "cubes" to cross-tabulate the employment counts for each "Type of Appointment" by demographic.

A few relevant links:

- [OPM's definitions of "Minority" and "Non-minority"](https://www.fedscope.opm.gov/rno/eri.asp)
- [OPM's list of the possible "Type of Appointment" classifications](https://dw.opm.gov/datastandards/referenceData/1585/current?index=T&d-5590585-p=5)
- [An explanation of the difference between permanent and temporary employees](https://www.usajobs.gov/Help/working-in-government/appointments/)

## Processed data

The files in the [`data/processed`](data/processed) calculate the proportions of employees who identified as minorities/female, for each fiscal quarter, for two aggregated groups:

- "Permanent" employees (see link above for definition)
- Mid-level political appointees (see below for definition)

The Python code used to make these calculations can be [found here](notebooks/data-processing.ipynb).

### Defining "mid-level political appointees"

According to correspondence with the Office of Personnel Management, there are two "type of appointment" categories that are composed entirely of political appointees:

- "Senior Executive Service - Non-Career," which is composed of employees who "[serve in the key positions just below the top Presidential appointees](https://www.opm.gov/policy-data-oversight/senior-executive-service/)"
- "Excepted Service - Schedule C," which is composed of policy advisers, confidential assistants, and other political staff.

When the analysis refers to mid-level political appointees, it refers to the combination of these two categories.

#### Note re. other political appointees

In addition, according to OPM, there are four other "type of appointment" categories that may, at times, include political appointees:

- Permanent "Excepted Service - Executive"
- Non-permanent "Excepted Service - Executive"
- "Senior Executive Service - Limited Term
- "Senior Executive Service - Limited Emergency"

Unfortunately, among these categories, it is not possible to distinguish between political appointees and non-appointees in the FedScope data.

# Reproducibility

To reproduce the calculations, you'll need to do the following:

- Ensure that you have installed [Python](https://www.python.org/) and the Python libraries listed in [`requirements.txt`](requirements.txt).
- Clear the [`data/processed`](data/processed) directory. (Shortcut: run `make clear`.)
- Re-run the `data-processing` notebook in the [`notebooks/`](notebooks/). (Shortcut: run `make reproduce`; requires Python 3.)

# Feedback / Questions?

Contact Jeremy Singer-Vine at [jeremy.singer-vine@buzzfeed.com](jeremy.singer-vine@buzzfeed.com).

Looking for more from BuzzFeed News? [Click here for a list of our open-sourced projects, data, and code](https://github.com/BuzzFeedNews/everything).
