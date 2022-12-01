# **Perform Foundational Infrastructure Tasks in Google Cloud: Challange Lab**

## **Challenge scenario**

You are just starting your junior cloud engineer role with Jooli inc. So far you have been helping teams create and manage Google Cloud resources.

You are expected to have the skills and knowledge for these tasks so don’t expect step-by-step guides.

### **Your Challenge**

You are now asked to help a newly formed development team with some of their initial work on a new project around storing and organizing photographs, called memories. You have been asked to assist the memories team with initial configuration for their application development environment; you receive the following request to complete the following tasks:

- Create a bucket for storing the photographs.
- Create a Pub/Sub topic that will be used by a Cloud Function you create.
- Create a Cloud Function.
- Remove the previous cloud engineer’s access from the memories project.

Some Jooli Inc. standards you should follow:

- Create all resources in the us-east1 region and us-east1-b zone, unless otherwise directed.
- Use the project VPCs.
- Naming is normally team-resource, e.g. an instance could be named kraken-webserver1
- Allocate cost effective resource sizes. Projects are monitored and excessive resource use will result in the containing project's termination (and possibly yours), so beware. This is the guidance the monitoring team is willing to share; unless directed, use f1-micro for small Linux VMs and n1-standard-1 for Windows or other applications such as Kubernetes nodes.

## **Guides**

---

### **Task 1: Create a bucket**

1. Navigation menu > **Cloud Storage** > Browser > Create Bucket
2. Name your bucket > Continue
3. Choose region and zone to store data > **Region**: us-east1 , **Zone**:us-east1-b > Continue
4. Let remaining settings to default
5. Create

Please wait for a couple of second for cloud storage being created.

### **Task 2: Create a Pub/Sub Topic**

1. Navigation menu > **Pub/Sub** > Topics
2. Create Topic > \*Name\*\*: create-thumbnail > Create Topic

### **Task 3: Create the thumbnail Cloud Function**

1. Navigation menu > **Cloud Functions**
2. Create Function > **Name**: `Cloud Function Name` > Continue
3. Choose Triggers > Set to **Cloud Storage** > Select Bucket in task 1 > **Event Type**: Finalize/Create Bucket > Continue
4. Let remaining settings to default
5. Set **Runtime**: Node.js 14
6. Set **Entry Point** (Function to execute) to `thumbnail` > Continue
7. In line 15 of index.js replace the text **REPLACE_WITH_YOUR_TOPIC_ID** with the `Topic Name` in task 2
8. Navigation menu > \*\*Cloud Storage > Select bucket > Upload Files in JPG or PNG format
9. Refresh Bucket

### \*\*Task 4: Remove the previous cloud engineer

1. Navigation menu > **IAM & Admin** > IAM
2. Click for the "Username 2" with access viewer > Remove Access
