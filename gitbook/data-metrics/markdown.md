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

The conditional probability that an event will occur after $$x$$ days have elapsed is calculated using:

$$
P(E | D = d) = \frac{f(d)}{\sum_{i=0}^{n} f(i)}
$$

Where:

$$P(E | D = d):$$ The CDP of event $$E$$ given $$d$$ days have elapsed.

$$f (d)$$ : Frequency of events after _d_ days.

$$n$$ : Total number of days considered.

$${\sum_{i=0}^{n} f(i)}$$ : Total number of frequencies across all days.

At the moment an event is detected, the probability resets to zero.

$$
P(E | D = 0) = 0
$$

After the detection of an event, the conditional distribution is recalculated.

See here an example notebook plot:

{% embed url="https://k-pantelidis.github.io/cases/probabilities/public.html" %}

Author: [**Konstantinos Pantelidis**](../about-us/meet-our-team.md#konstantinos-pantelidis)
