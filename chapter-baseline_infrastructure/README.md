## Google Cloud

### Bucket

> Google Cloud Storage

- Bucket naming rules:

  - Do not include sensitive information in the bucket name, because the bucket namespace is global and publicly visible.

  - Bucket names must contain only lowercase letters, numbers, dashes (-), underscores (\_), and dots (.). Names containing dots require verification.

  - Bucket names must start and end with a number or letter.

  - Bucket names must contain 3 to 63 characters. Names containing dots can contain up to 222 characters, but each dot-separated component can be no longer than 63 characters.

  - Bucket names cannot be represented as an IP address in dotted-decimal notation (for example, 192.168.5.4).

  - Bucket names cannot begin with the "goog" prefix. Bucket names cannot contain "google" or close misspellings of "google".\*

  - Also, for DNS compliance and future compatibility, you should not use underscores (\_) or have a period adjacent to another period or dash. For example, ".." or "-." or ".-" are not valid in DNS names.

- Bucket storage class :

  - Standard (short-term and frequently access)
  - Nearline (backup and data accessed < once a month)
  - Coldline (disaster recovery and data accessed < once a quarter)
  - Archive (long-term digital preservation and data accessed < once a year)</br>

- Bucket Access Control
  - Uniform (only bucket-level permissions(IAM))
  - Fine-grained (object-level permissions(ACLs))

Access file when publicy access has a format url : `storage.googleapis.com/<BUCKET_NAME>/<FILE_NAME>`

### Cloud Shell Terminal

Syntax:</br>

- `gcloud <commands>`
- `gsutil <commands>`

Please read here for further information [gcloud CLI documentation](https://cloud.google.com/sdk/gcloud).

### Google Cloud's Identity and Access Management (IAM)

> Permissions for Google Cloud resources.</br>

Basic Role : </br>
| Role Name | Permissions |
| --- | ------------- |
|roles/viewer|Permissions for read-only actions that do not affect state, such as viewing (but not modifying) existing resources or data.|
|roles/editor|All viewer permissions, plus permissions for actions that modify state, such as changing existing resources.|
|roles/owner|All editor permissions and permissions for the following actions: Manage roles and permissions for a project and all resources within the project.Set up billing for a project.|
|roles/browser|Read access to browse the hierarchy for a project, including the folder, organization, and Cloud IAM policy. This role doesn't include permission to view resources in the project.|

- Grant Access
- Remove Access

### Cloud Monitoring

> Provides visibility into the performance, uptime, and overall health of cloud-powered applications. Collects metrics, events, and metadata from Google Cloud, AWS, and many others. Cloud Monitoring alerting helps to collaborate by integrating with many tools like slack, etc.

Cloud Monitoring have 2 aspect:

- Agent
- Dashboard

Please read this full [Cloud Monitoring Documentation](https://cloud.google.com/monitoring/docs#).

### Cloud Functions

> Cloud Functions is a serverless execution environment for building and connecting cloud services. It written in Javascript and executed in a Node.js environment on Google Cloud.

Events, things that happen in your cloud environment. These might be like change to data in a database, file added to a storage system, or a new virtual machine instance being created.

Triggers, a declaration that you are interested in a certain event or set of events.

Read documentation [Events and Triggers](https://cloud.google.com/functions/docs/concepts/events-triggers).

Use Case for cloud functions:

- Data Processing/ ETL
- Webhooks
- Lightweight APIs
- Mobile Backend
- IoT
