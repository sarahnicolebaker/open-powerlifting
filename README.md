# open-powerlifting analysis

Exploratory data analysis and hypothesis testing on [OpenPowerlifting](https://www.openpowerlifting.org/) competition data. The snapshot is from 2024-01-06 and covers meets from 1964 to January 2024.

The question being explored is: how does equipment affects performance? More specifically, do women who compete in single-ply suits  total more than raw lifters? Do they bomb out more?

## Data cleaning

Full checks are in open-powerlifting-cleaning.ipynb. Each check asks a question about the data, tests it, and records a decision.

The data turned out to be mostly clean. The only change was removing 3,601 exact duplicate rows. Other checks found valid quirks and edge cases, not data quality issues. Summary below:

- Missing totals are all bomb-outs, no-shows, or doping disqualifications. Kept, and will filter out where an analysis needs a total.
- Missing bodyweight (about 1.3% of rows) is left blank, not filled from weight class, since a class is only an upper limit.
- Lifters over their weight class are all over by less than 0.1 kg, which is likely rounding from pound-based classes.
- Totals always equal best squat + bench + deadlift. About 0.6% of meets recorded totals only.
- Negative attempts are missed lifts, and **4th attempts** are record attempts that don't count toward the total.
