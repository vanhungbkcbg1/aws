## Simple access point permission to grant roleA to access only file throught access point and on folder roleA only
- create roleA have permission like bellow, make sure in trust policy we allow switch role in the account
````

// trust role policy
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Principal": {
                "AWS": "arn:aws:iam::154713672373:root"
            },
            "Action": "sts:AssumeRole"
        }
    ]
}

// policy
{
	"Version": "2012-10-17",
	"Statement": [
		{
			"Sid": "Statement1",
			"Effect": "Allow",
			"Action": "s3:GetObject",
			"Resource": "arn:aws:s3:ap-northeast-1:154713672373:accesspoint/demo-public/object/roleA/*"
      // this policy to allow get Object in folder roleA only
		},
		{
			"Sid": "Statement2",
			"Effect": "Allow",
			"Action": "s3:ListBucket",
			"Resource": [
				"arn:aws:s3:ap-northeast-1:154713672373:accesspoint/demo-public"
			]
      // this policy is used to allow list all bucket object in access point
		},
		{
			"Sid": "Statement3",
			"Effect": "Allow",
			"Action": [
				"s3:ListAccessPoints", // **this policy is used to allow display all access point of current acccount**
				"s3:GetAccessPoint" // **this policy is used to allow get detail of an access point**
			],
			"Resource": "*"
      // this policy is used to allow list all access point
		}
	]
}
````
