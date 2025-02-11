# Timing Expectations of Data Collection, Analysis, and Results

**Q. When is data added to Densify?**

A.  Data is sent to Densify hourly. &#x20;

**Q. When is new data analyzed and when can I expect to see results?**

A. Analytics run nightly and results will appear typically before 9am of your local time zone.

**Q.  Data collection is setup but why do I only see a subset of accounts or objects in the Densify UI?**

A.   This can be caused by a few things:

·        If cloud accounts are not configured with minimum permissions required by Densify, configuration and/or workload metrics may not be collected during audits, resulting in No Configuration Data and/or Missing Benchmarks

·        Object of interest is offline / terminated

·        Densify requires 7 days of data (where each day has at least 1 hour of usage) to be collected and loaded to the database before a system will be analyzed

·        Analysis processing may not have run yet and is scheduled to run as part of the weekend batch process

·        When working with ASGs, note that ASGs configured with maximum group size = 1 are only included on the EC2 tab

·        ASG reports include the number of EC2s per group, based on average number of nodes running per day

·        ASGs configured with a maximum group size > 1, are included in the Auto Scaling Groups tab. See [Working with Auto Scaling Groups](https://www.densify.com/docs/WebHelp_Densify_Cloud/Content/Densify_Com/Working_with_ASGs.htm)

·        EC2 objects that are part of an ASG will not appear in the EC2 view unless the ASG has a max group size =1

·        ASGs with different types of EC2 members (heterogenous) are not supported by Densify

·        When a system configuration change has taken place, it will then invalidate the previous workload history and Densify will begin relearning the workload patterns to potentially provide a new recommendation based on the new system configuration.   [More info is available on this topic in our documentation](https://www.densify.com/docs/WebHelp_Densify_Cloud/Content/Densify_Com/Reviewing_Cloud_Recommendations.htm)

·        Not all types of public cloud objects are supported by Densify analysis. Refer to [Managing Your Public Cloud](https://www.densify.com/docs/WebHelp_Densify_Cloud/Content/Densify_Com/Managing_Your_Public_Cloud.htm) for details on the types of objects that are supported for collection and analysis
