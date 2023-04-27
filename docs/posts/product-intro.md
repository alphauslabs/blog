---
date: 2023-04-24
authors:
- flowerinthenight
categories:
- Products
---

# Product introduction

At Alphaus, we have developed two products, [Ripple](https://alphaus.cloud/ripple/) and [WavePro](https://alphaus.cloud/en/wave/), both aimed at assisting users in managing their cloud costs effectively. These products focus on providing the necessary tools and insights to help users monitor and control their cloud expenses efficiently.

<!-- more -->

Ripple has been specifically tailored for Managed Service Providers (MSPs), providing a cohesive, user-friendly multi-cloud console that streamlines invoicing and cost management for their clients. WavePro, on the other hand, serves as a versatile multi-cloud cost visualization and reporting tool, often bundled with Ripple, primarily targeted at MSP clients, and includes the added benefit of white labeling options. Together, these tools create a comprehensive solution that caters to the unique needs of MSPs and their clients, enhancing overall cloud cost management and reporting efficiency.

## Ripple

Ripple is an invoicing software tool that facilitates efficient cost analysis, visualization, and optimization for MSPs. It centers around the concept of [billing groups](https://labs.alphaus.cloud/docs/concepts/#billing-group): grouping of cloud accounts. Most of the features in Ripple relate to billing groups. Once configured, it starts with the ingestion of billing data from AWS, Azure, and GCP.

* For AWS, [CUR](https://docs.aws.amazon.com/cur/latest/userguide/how-cur-works.html) csv files exported to [S3](https://docs.aws.amazon.com/cur/latest/userguide/cur-s3.html);
* For Azure, cost and usage data queried through their [Partner Center API](https://learn.microsoft.com/en-us/rest/api/partner-center/manage-billing);
* For GCP, billing data exported to [BigQuery](https://cloud.google.com/billing/docs/how-to/export-data-bigquery).

Once data is ingested into Ripple, it undergoes data processing. This involves various data transformations and aggregations to generate meaningful insights. One unique feature of Ripple, is the capability to perform corrective recalculations specifically for AWS billing data. We call this [TrueUnblended](https://labs.alphaus.cloud/docs/trueunblended/). TrueUnblended-based calculations are particularly valuable to MSPs since they allow for accurate and detailed visibility of account costs without worrying about [Reserved Instances](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-reserved-instances.html) and/or [Savings Plans](https://docs.aws.amazon.com/savingsplans/latest/userguide/what-is-savings-plans.html) discount sharing across different organizations.

Once data is ready for invoicing, Ripple can handle all invoicing requirements, including chargebacks, custom charges, premiums, custom pricing, customizable invoice PDF layout, and much more. Ripple supports multiple currencies for invoicing, making it convenient for MSPs who work with clients in different regions.

In addition to its invoicing capabilities, Ripple also offers valuable features such as recommendations for RI and SP purchases, as well as usage pattern insights. This enables MSPs to optimize their cloud usage, reduce costs, and maximize their return on investment. Overall, Ripple is a powerful tool that helps MSPs streamline their billing processes and make data-driven decisions to improve their cloud financial management.

## WavePro

WavePro is a powerful visualization and reporting tool that complements Ripple's invoicing capabilities. Designed for MSP clients, WavePro features are tied to billing groups. A client can have one or multiple billing groups, depending on their organizational structure. Think of WavePro as a multi-cloud version of AWS Cost Explorer, providing clients with valuable insights into their cloud usage and costs.

It's important to note that WavePro doesn't have direct access to the client's cloud environment. Instead, it relies on Ripple as its primary source of information. However, we are currently developing an option to allow WavePro users to set up API access to their cloud environments. With this feature, WavePro can provide additional value, such as RI/SP coverage and recommendations, forecasting, and more.

Overall, WavePro is a valuable tool that helps MSP clients gain better visibility into their cloud usage and costs, enabling them to optimize their cloud resources, reduce costs, and maximize their return on investment.

## Conclusion

Ripple/WavePro is a proven and trusted cloud financial management solution that has become a leading choice for MSPs in Japan. We are excited to announce our expansion into the Asia Pacific region, with notable MSPs in Singapore and Malaysia already on board.

If you're curious about how Ripple/WavePro can support your cloud financial management needs, we welcome you to contact us at [https://alphaus.cloud/contact-us-en/](https://alphaus.cloud/contact-us-en/). Our team is happy to answer any questions you may have and provide more information about our solution.
