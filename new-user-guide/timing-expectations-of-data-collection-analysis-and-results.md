# Timing Expectations of Data Collection, Analysis, and Results

**Q. When is data added to Densify?**

A.  Data is sent to Densify hourly. &#x20;

**Q. When is new data analyzed and when can I expect to see results?**

A. Analytics run nightly and results will appear typically before 9am of your local time zone where your instance is hosted

**Q. If we have workloads that run for less than a day at a time, but are repeated somehow (eg. batch workloads), are the recommendations useful?**

A. Yes, for example if you have a workload that runs for an hour today and shuts down and then runs again for a couple of hours and runs only for an hour tomorrow and so on, as long as the pod name is the same and there is a minimum of 2 hours of data, recommendations are generated, and can even be automatically applied. As mentioned above, with more historical data, the recommendations are better.

**Q. VPA will look at metrics-server data and apply a basic recommendation within a couple of minutes. Have you made a conscious choice with Kubex to apply recommendations more slowly?**&#x20;

A. That is correct, with Kubex, we consider historical data up to 90 days which accounts for any seasonality in the business and provides more robust recommendations. VPA considers only very recent historical data.
