# Subscription Experiment: A/B Conversion Comparison

## Context

*In our mobile app, users are offered a weekly subscription for $4.99 after onboarding, giving access to premium features.*

*Currently, **17%** of users who see the offer purchase the subscription.*

*We decided to test an alternative subscription screen design. It also offers the $4.99 subscription but mentions a **50% discount**.*

*About **2,000** users install the app daily, and **34%** of them reach the subscription screen.*

## Hypotheses
- **Alternative hypothesis:** users in group B who see the 50% discount message buy the subscription more often than those who do not see it.
- **Null hypothesis:** the 50% discount message does not change the purchase rate; the subscription conversion in group B is the same as in group A.

## Test Population
- All users who completed onboarding and reached the subscription offer screen.

## Metric
- Conversion = number of users who purchased the subscription / total number of users who saw the subscription offer.

## Sample Size and Test Duration
- **4,694** users are needed per group.
- With ~**2,000** installs per day and **34%** reaching the subscription screen → 2000*34/100 = **680 users per day**.
- Required users can be reached in 9388/680 = **~13.6 days**.

## Dataset
- user_id
- timestamp
- test_group
- conversion

**Size:** 19,998 rows

## Technologies Used

- Python
- Pandas
- Seaborn
- Matplotlib
- SciPy
- Jupyter Notebook

## Data Processing

- **Missing values:** none
- **Date conversion:** timestamp converted to datetime format
- **New column:** added date column (without time)
- **Grouping:**
    - by test group – to calculate conversion
    - by date – to analyze daily trends
- **Aggregation:**
     - average conversion and number of users per group
- **Statistical analysis:**
     - Chi-Square test to check significance of conversion differences
     - Permutation test for additional verification of significance

## Visualizations

### Charts created:

- **Bar plots:**
   - number of users per group
   - average conversion A vs B
   - conversion with 95% confidence intervals

- **Line chart:**
   - daily conversion by group

## Analysis Summary

- Groups are balanced by number of users
- Group B shows significantly higher conversion than group A
- Daily chart confirms stable advantage of group B
- All statistical tests reject the null hypothesis

## Conclusions

- Changes in variant B led to a significant increase in conversion (+2.8%)
- Statistical significance confirmed at α = 0.05

**Recommendation:** implement variant B in production
