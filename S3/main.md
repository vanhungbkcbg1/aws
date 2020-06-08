**Store class**

***Amazon S3 Standard***:
>offers high durability, high availability, low latency, and high
performance object storage for general purpose use ****dat nhat****

***Amazon S3 Standard – Infrequent Access***:
>offers the same durability, low
latency, and high throughput as Amazon S3 Standard, but is designed for long-lived, less
frequently accessed data ***dat thu 2***

***Amazon S3 Reduced Redundancy Storage (RRS)***
>dung cho data it truy cap, data co the tai tao duoc

***Amazon Glacier storage class***
>offers secure, durable, and extremely low-cost
cloud storage for data that does not require real-time access, such as archives and long-term
backups. To keep costs low, Amazon Glacier is optimized for infrequently accessed data
where a retrieval time of several hours is suitable ***dung cho data it truy cap,cho muc dich luu tru la chinh, re nhat***

***Object Lifecycle Management***
>Using Amazon S3 lifecycle configuration rules, you can significantly reduce your storage costs
by automatically transitioning data from one storage class to another or even automatically
deleting data after a period of time

***Multipart Upload***
>support upload file dung luong lon len aws bang cach chia nho file thanh cac phan nho,upload dong thoi 
nen su dung voi truong hop file lon hon 100MB
bat buoc su dung voi file lon hon 5G

***Range GETs***
lay mot phan cua file 

can setting Object lifecycle trong S3

***ta co the setting permission cho bucket,cho tung file trong bucket, va toan object trong 1 account***

***Store Class([Reference](https://docs.aws.amazon.com/AmazonS3/latest/dev/storage-class-intro.html))***
1. S3 Standard
   >The default storage class. If you don't specify the storage class when you upload an object, Amazon S3 assigns the S3 Standard storage class
2. Reduced Redundancy
   >The Reduced Redundancy Storage (RRS) storage class is designed for noncritical, reproducible data that can be stored with less redundancy than the S3 Standard storage class
3. S3 Intelligent-Tiering
   >The S3 Intelligent-Tiering storage class is designed to optimize storage costs by automatically 
   >moving data to the most cost-effective storage access tier, 
   >without performance impact or operational overhead. S3 Intelligent-Tiering delivers 
   >automatic cost savings by moving data on a granular object level between two access tiers, a frequent access tier and a lower-cost infrequent access tier, when access patterns change. The Intelligent-Tiering storage class is ideal if you want to optimize storage costs automatically for long-lived data when access patterns are unknown or unpredictable
   
   >The S3 Intelligent-Tiering storage class stores objects in two access tiers: one tier that is optimized for frequent access and another lower-cost tier that is optimized for infrequently accessed data. For a small monthly monitoring and automation fee per object, Amazon S3 monitors access patterns of the objects in the S3 Intelligent-Tiering storage class and moves objects that have not been accessed for 30 consecutive days to the infrequent access tier                          


***link nen doc***

[Access Policy and Bucket Policy](https://docs.aws.amazon.com/AmazonS3/latest/dev/access-policy-language-overview.html)

[Optimize S3 performance](https://docs.aws.amazon.com/AmazonS3/latest/dev/optimizing-performance.html)
>ta co the setting permission cho bucket
>cho tung file trong bucket, va toan object trong 1 account
