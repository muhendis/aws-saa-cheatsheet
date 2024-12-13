## **Amazon S3 Advance**

| **Topic**                     | **Details**                                                                                                                                              | **Examples/Notes**                                                                                       |
| ----------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------- |
| **Storage Class Transitions** | Use **Lifecycle Rules** to transition objects between storage classes.                                                                                   | Example: Move to Standard IA after 60 days, Glacier Deep Archive after 6 months.                         |
| **Lifecycle Rules**           | Automate transitions and expiration of objects. Supports prefix or tag-based rules.                                                                      | **Scenario**: Thumbnails (One-Zone IA) deleted after 60 days; Source images (Standard) moved to Glacier. |
| **Analytics & Optimization**  | **Storage Class Analysis** suggests optimal storage classes based on usage.                                                                              | **Note**: Works for Standard and Standard IA only. Daily reports.                                        |
| **Requester Pays**            | Shifts data transfer and request costs to the requester instead of the bucket owner.                                                                     | **Use Case**: Sharing large datasets with other accounts.                                                |
| **Event Notifications**       | Triggers actions (e.g., Lambda, SNS, SQS) based on S3 events (e.g., object upload).                                                                      | Example: Generate thumbnails for images uploaded to S3.                                                  |
| **Performance Optimization**  | - Multi-Part Upload: Parallelize uploads for large files (>5GB). <br> - Transfer Acceleration: Speeds up cross-region data transfers via edge locations. | Example: Upload a 10GB video to a bucket in another region using multi-part upload.                      |
| **Batch Operations**          | Bulk operations on existing objects: modify metadata, restore from Glacier, etc.                                                                         | **Use Case**: Re-encrypt objects or copy to another bucket.                                              |
| **Storage Lens**              | Provides analytics and insights for storage usage, cost efficiency, and data protection across accounts and regions.                                     | **Metrics**: Data Protection, Activity, Performance, Cost Optimization.                                  |
| **Versioning**                | Enables rollback and recovery of objects. "Delete markers" help recover deleted files.                                                                   | **Tip**: Use with Glacier for long-term backups.                                                         |
| **Replication**               | Cross-Region and Same-Region replication for compliance, latency, or backup purposes.                                                                    | Example: CRR for compliance; SRR for log aggregation.                                                    |
| **Performance Limits**        | Baseline: 3,500 PUT/POST/DELETE or 5,500 GET/HEAD requests per prefix per second.                                                                        | Use multiple prefixes for high throughput.                                                               |
| **Byte-Range Fetches**        | Speeds up downloads by fetching specific byte ranges in parallel.                                                                                        | Example: Fetching headers or partial data from large files.                                              |
| **Static Website Hosting**    | Host static content with public read access via bucket policy.                                                                                           | URL: `http://bucket-name.s3-website-region.amazonaws.com`.                                               |

---

### Additional Features and Use Cases:

1.  **Lifecycle Rule Scenarios**:

    - Transitioning and expiring objects based on tags or prefixes for cost and storage management.
    - **Scenario 1**: Deleting temporary thumbnails and archiving original images.
    - **Scenario 2**: Keeping deleted objects recoverable for 30 days in Standard IA, then transitioning to Glacier Deep Archive.

2.  **S3 EventBridge**:

    - Allows advanced filtering and integration with AWS services (e.g., Kinesis, Step Functions).

      - **Events include:** ObjectCreated (e.g., PUT, POST, COPY), ObjectRemoved (e.g., DELETE), ObjectRestore, Replication events.

    - Useful for custom workflows and event management. ex:
      - Step Functions: Resize and store image metadata.
      - Lambda: Generate and store thumbnails in another S3 bucket.
      - Kinesis Firehose: Stream data to analytics services.

3.  **S3 Storage Lens Metrics**:
    - Includes free and paid metrics for storage trends, data protection, and performance.
