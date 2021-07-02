[Oregon Special Education Students Face Widely Varying Programs](https://www.notion.so/Oregon-Special-Education-Students-Face-Widely-Varying-Programs-7cbddbd0a9864d9aada9d051712a8adb)

## Methodology:

1. Defined question:

    Are there wide differences between special education programs in Oregon?

    To lead to broader question:

    If there are wide differences, are those differences based on the best interest of the students?

2. Defined constraints:

    Data is from the Oregon Department of Education, with metrics defined by the federal government

    Decided to use data from the 2018-19 school year, even though there is data for the 2019-20 school year. Because of covid, the most recent data has a number of external factors altering the numbers

3. Downloaded the data for both school years as numbers docs, then exported to csv's
4. Imported 2018-2019 csv, with columns that show differences between districts. I omitted metrics that focused on outcomes and student outcomes rather than the overall schools:

    LRE Students >80%

    Percent of students with IEPs who are in the regular classroom for 80% or more of the school day

    LRE Students <40%

    Percent of students with IEPs who are in the regular classroom less than 40% of the day

5. Assumed that the non-null values had a statistically-significant sample size
6. Changed '*' values to NaN
7. removed '%' character and converted 'LRE Students >80%', 'LRE Students <40%', 'IEP Dropout 17-18' to float
8. Calculated the spread and average of each metric with [metric].describe()
9. Plotted histogram of 'LRE Students >80%' and found that very small districts (< 30 students in special education) were outliers

    Filtered dataframe to just include districts with > 50 students in special education

10. Plotted histogram of 'LRE Students <40%' and adjusted maxbins to make the size of the bin equal to the size of the bin for the first histogram (1%)
11. Went back to original dataset to find what the state of Oregon's target numbers were for the 2 metrics, and if the goals were being met
12. Re-calculated the spread, mean, and standard deviation for the dataframe that excludes districts with <30 students in special education
13. Calculated the number and percent of districts not meeting the goals for the 2 metrics
14. Made bar chart showing >80% metric

    showed top 5 and bottom 5 districts