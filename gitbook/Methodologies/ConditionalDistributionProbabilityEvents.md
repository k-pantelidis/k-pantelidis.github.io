---
icon: markdown
---

# CDP - Events

The "Conditional Distribution Probability (CDP) - Events" is a systematic approach to identifying significant events in time series data.

The first step in the CDP - Events methodology involves detecting outliers in the time series data by utilizing a selected algorithm. A $$w$$-day sliding window is employed to continuously assess the data for anomalies. When an outlier is identified at time $$t$$, it is classified as an event.

Events are categorized based on the asset's price returns following detection:

* **Positive Event**: If the asset's price return is positive after the outlier detection.
* **Negative Event**: If the asset's price return is negative after the outlier detection.

Once events are classified, a frequency table is constructed to track how many days have elapsed since the last event. The structure of this table includes:

* **Days Elapsed**: Number of days since the last event.
* **Number of Events**: Count of events that occurred after $$d$$ days.

To analyze the frequency of events, various statistical distributions are fitted to the data. The best-fitting distribution is determined using methods such as the sum of squared errors.



At the moment an event is detected, the probability resets to zero.

$$
P(E | d = 0) = 0
$$

The conditional probability that an event $$E$$ will occur after $$d$$ days have elapsed is calculated using the cumulative probability formula for a conditional distribution $$C$$:

$$
P(E \leq d)_{t,C} = \int_{0}^{d} f(e)_{t,C} \, de
$$



After the detection of an event, the conditional distribution is recalculated.

See [here ](https://k-pantelidis.github.io/methodologies/ConditionalDistributionProbabilityEvents/interactive_plot.html)an interactive example.



Author: [**Konstantinos Pantelidis**](../about-us/meet-our-team.md#konstantinos-pantelidis)
