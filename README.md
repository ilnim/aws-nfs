Network File System (NFS) file shares are used frequently to conduct day-to-day business. However, the data in most on-premises NFS file server is often not adequately backed up or protected from a disaster at the primary data center. DataSync addresses many of these shortfalls. The service:

- Copies existing data from an on-premises NFS file server to Amazon Simple Storage Service (Amazon S3) for secure, redundant storage
- Comes with a built-in scheduling mechanism enabling you to periodically execute a data transfer task to detect and copy changes from your source storage system to the destination.
- Ensures that your data arrives intact. For each transfer, the service performs integrity checks both in-transit and at-rest. These checks ensure that the data written to your destination matches the data read from your source, validating consistency.
- Is priced per gigabyte of data moved, making it cost-effective and predictable
- Can be deployed in minutes

A Storage Gateway file gateway provides the ongoing data transfer to and from Amazon S3. The file gateway acts as a file system mount on an S3 bucket. The file gateway NFS file share will replace the existing on-premises NFS file server, allowing for that server to be retired. Doing this frees up local resources and reduces maintenance time.

The project will attempt to deploy the below architecture. One instance acting as the on-premises client host and one instance acting as the on-premises Linux NFS file server. DataSync agent instance is deployed into the same subnet as the on-premises NFS file server. The instance is configured to copy sample data to an S3 bucket. File gateway appliance is then deployed into the same subnet as the on-premises NFS file server. An NFS file share is created on the file gateway appliance and  the Linux client host is reconfigured to connect to the new share.


![image](https://github.com/ilnim/aws-nfs/assets/115760354/574fe6b3-49b6-4e64-bcb8-5ae254493e3e)
