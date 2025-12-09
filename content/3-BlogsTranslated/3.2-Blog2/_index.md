---
title: "Blog 2"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 3.2. </b> "
---
# Introducing default instance categories for AWS Batch

#### By Angel Pizarro on August 18, 2025 in [AWS Batch](https://aws.amazon.com/blogs/hpc/category/compute/aws-batch/), [High Performance Computing (HPC)](https://aws.amazon.com/blogs/hpc/category/high-performance-computing/) | [Permalink](https://aws.amazon.com/blogs/hpc/introducing-default-instance-categories-for-aws-batch/)

Today we are launching a new set of **instance family classifications** for **AWS Batch**, including **"default_x86_64"** and **"default_arm64"**. These new categories are both a **clarification** and **improvement** over the existing "optimal" instance type category. This post provides some context about the new feature and how you can **configure Batch environments** to take advantage of these improvements.

## Choosing instance types for AWS Batch Compute Environments to launch

You can specify the **set of [Amazon EC2](https://aws.amazon.com/ec2/) instance types** that a **compute environment** is allowed to launch to run the jobs in your **job queues**. For example, if you know that your jobs achieve the best **price/performance** on g6.16xlarge, you can set the [computeResources.instanceTypes parameter](https://docs.aws.amazon.com/batch/latest/APIReference/API_ComputeResource.html#Batch-Type-ComputeResource-instanceTypes) of the compute environment to ["g6.16xlarge"], and that environment will only launch **exactly** this instance type and size for jobs in the associated queue(s).

To take full advantage of **Batch's scheduling and scaling** capabilities, you should define **a diverse set** of instances and let Batch decide which type to launch based on the CPU, memory, and GPU resource requirements of your jobs. While you can specify a **list of instance types** (e.g., ["c5.24xlarge", "m6.48xlarge"]), you can also define a **set of instance families** (e.g., ["c5","c7a","c7i","m7i"]) for Batch to launch on your behalf. Previously, you also had the option to use the **"optimal"** category, which Batch would map to ["c4","m4","r4"] when those instances were available in **your AWS Region**. If a Region did not have those instance types, Batch would map *optimal* to the **lowest-cost generation** in the Region, typically ["c5","m5","r5"].

While *optimal* is a convenient shorthand setting, we have found that it **does not align** with customer expectations. Batch **does not** select instances for the **best performance** of your job or the **best price** for your application. The *optimal* category is just **a simple mapping** and nothing more. Newer instance generations are likely to deliver **better price/performance** for most workloads. In all cases I have examined, **4th generation** instances are both **slower** and **more expensive** than **5th generation**, so *optimal* is actually **not "optimal"** at all!

Finally, *optimal* **does not include** instances using **AWS Graviton** processors, which are purpose-built to deliver **superior price/performance** for many types of workloads.

## Upgrading from the "optimal" configuration

Today, we have launched a new set of **instance type categories** to improve your experience with Batch's instance selection feature. You can now choose default_x86_64 for a set of **instance families** using **x86** CPUs, and default_arm64 for a set of **instances** using **AWS Graviton** CPUs. The list of **instance types** will **not be static** and will change over time as we introduce new **instance families**. You can find the mapping between each **category** and the set of **instance families** by **Region** in the [**Instance type compute table**](https://docs.aws.amazon.com/batch/latest/userguide/instance-type-compute-table.html) documentation page; for example, the default_arm64 mapping at the time of feature launch will be as follows:

| Regions | Instance families |
| :---- | :---- |
| All AWS Regions supporting AWS Batch | m6g, c6g, r6g c7g |

*Table 1. Mapping of the* default_arm64 *instance type category to specific instance families in Regions supporting AWS Batch.*

The default mappings **do not** include accelerated instances by design. We **strongly recommend** you specify instance types explicitly if your workload benefits from accelerated instances. Additionally, we recommend **defining a separate** **job queue** and **compute environment** from your clusters of **non-accelerated** instances. When resources are separated, Batch can make **better** scaling decisions for your workload and **prevent** scheduling non-accelerated jobs onto accelerated instances, which could lead to **unnecessary costs**.

Similar to previously with *optimal*, you can still **define additional** **instance types** alongside the default_* categories. Batch will consider the **entire list** you have declared when selecting **instance types** to run jobs.

## Transitioning from *optimal*

We recommend that you update your Batch environments to adopt the new categories. However, you are **not required** to update. AWS Batch compute environments currently using *optimal* remain **valid**. The [**CreateComputeEnvironment**](https://docs.aws.amazon.com/batch/latest/APIReference/API_CreateComputeEnvironment.html) and [**UpdateComputeEnvironment**](https://docs.aws.amazon.com/batch/latest/APIReference/API_UpdateComputeEnvironment.html) API operations still accept *optimal* as a valid value. The behavior of *optimal* will **remain unchanged** until **early November 2025**. After that time, *optimal* will **behave identically** to the default_x86_64 instance type category.

Once again, after **early November 2025**, *optimal* will **no longer** be a static mapping to **4th generation** instances (if available) and will **change over time** as AWS introduces new instance families. If you want to **maintain** the current instance set for *optimal*, you should update your compute environment(s) to **explicitly specify** those **instance types**.

We recommend that all **new compute environments** you create use the new default_* categories. Personally, I also recommend you test whether your application can benefit from **Graviton** by building an **Arm container** and defining a **compute environment** and **job queue** using default_arm64. Most likely you will get a **desirable** result!

## Conclusion

We encourage you to try the new default_* instance type categories. We believe that gradually adopting newer instance generations over time will help your workload operate efficiently and cost-effectively. To start using the new categories, log in to the **AWS Batch management console**, or refer to the guide for creating a **managed EC2 compute environment** in our **User Guide**.

---

**Angel Pizarro** is a Principal Developer Advocate for HPC (High-Performance Computing) and computational science. He has a background in developing bioinformatics applications and building system architectures for scalable computing in genomics and other high-throughput life science domains.
