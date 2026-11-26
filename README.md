# storageazure

# Core Azure Storage Services
## Azure Blob Storage: A massively scalable object store for unstructured data like text, binary data, images, and logs, including support for big data analytics via Azure Data Lake Storage.
## Azure Files: Managed, enterprise-grade file shares accessible via standard SMB and NFS protocols for cloud or on-premises deployments.
## Azure Queue Storage: A reliable messaging store for asynchronous communication and decoupling between application components.
## Azure Table Storage: A NoSQL store for schemaless storage of structured or semi-structured data.
## Azure Managed Disks: High-performance, block-level storage volumes dedicated to Azure Virtual Machines. 

# Storage Classes (Access Tiers):
## Hot tier - An online tier optimized for storing data that is accessed or modified frequently. The hot tier has the highest storage costs, but the lowest access costs.
## Cool tier - An online tier optimized for storing data that is infrequently accessed or modified. Data in the cool tier should be stored for a minimum of 30 days. The cool tier has lower storage costs and higher access costs compared to the hot tier.
## Cold tier - An online tier optimized for storing data that is rarely accessed or modified, but still requires fast retrieval. Data in the cold tier should be stored for a minimum of 90 days. The cold tier has lower storage costs and higher access costs compared to the cool tier.
## Archive tier - An offline tier optimized for storing data that is rarely accessed, and that has flexible latency requirements, on the order of hours. Data in the archive tier should be stored for a minimum of 180 days.
## Smart tier - Smart tier automatically moves your data between the hot, cool, and cold access tiers based on usage patterns, optimizing your costs for these access tiers automatically. To learn more, see Optimize costs with smart tier.
## Turbo tier (Preview) adds SSD-backed performance for workloads that need low latency and high throughput, including AI, machine learning, and interactive analytics. Within a general-purpose storage account, Turbo accelerates reads and writes for performance-demanding data while less frequently accessed data remains in lower-cost access tiers. You can select the tier that best fits each blob’s performance and cost requirements, all within the same storage account and through standard Blob Storage APIs and tools. This feature lets you apply SSD performance where it matters most without managing a separate high-performance storage account or relocating the entire dataset.
# Blob Types (Data Classes)
## Block Blobs. Built for storing text and binary data like documents, images, and videos by splitting files into manageable blocks.
## Append Blobs. Optimized for append-only operations, making them ideal for logging data from virtual machines or applications without rewriting the whole file.
## Page Blobs. Designed for frequent random read/write operations in 512-byte pages, primarily used to back Azure Virtual Machine disks. 


# Prerequisites
##A Standard general-purpose v2 (GPv2) storage account. 
Smart tier doesn't support legacy Standard general-purpose v1 (GPv1) accounts or premium storage accounts. 
##Zone-redundant storage (ZRS, GZRS, or RA-GZRS). 
Smart tier works only on block blobs. Page blobs and append blobs aren't supported. 


# Lifecycle
By default, new data is stored in the hot tier. Any object that isn't accessed for 30 days is moved to the cool tier; after 90 days of inactivity, it transitions to the cold tier. If any of those objects are later accessed, they're transitioned back to the hot tier automatically and restart their tiering cycle.

# Static website hosting feature of Azure Blob Storage.
# Check Your Storage Account Type
If the option is completely missing even after searching, your storage account configuration might not support it.
## Hierarchical Namespace (ADLS Gen2): If you enabled Hierarchical Namespace (Azure Data Lake Storage Gen2) during creation, the static website feature is disabled by default. 
## Account Kind: Static websites require a standard General-purpose v2 storage account or a premium BlockBlobStorage account. Legacy v1 accounts do not support this feature.
