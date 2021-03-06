[![CloudSploit](https://cloudsploit.com/img/logo-new-big-text-100.png "CloudSploit")](https://cloudsploit.com)

# AWS / Kinesis / Kinesis Streams Encrypted

## Quick Info

| | |
|-|-|
| **Plugin Title** | Kinesis Streams Encrypted |
| **Cloud** | AWS |
| **Category** | Kinesis |
| **Description** | Ensures Kinesis Streams encryption is enabled |
| **More Info** | Data sent to Kinesis Streams can be encrypted using KMS server-side encryption. Existing streams can be modified to add encryption with minimal overhead. |
| **AWS Link** | https://docs.aws.amazon.com/streams/latest/dev/server-side-encryption.html |
| **Recommended Action** | Enable encryption using KMS for all Kinesis Streams. |

## Detailed Remediation Steps
1. Log into the AWS Management Console.
2. Select the "Services" option and search for "Kinesis". </br><img src="/resources/aws/kinesis/kinesis-streams-encryption/step2.png"/>
3. Under the "Amazon Kinesis dashboard" choose "Data Firehose" from the left navigation panel. </br><img src="/resources/aws/kinesis/kinesis-streams-encryption/step3.png"/>
4. Select the "Firehose Delivery System" that needs to be verified and click on the "Name" to access the delivery stream.</br><img src="/resources/aws/kinesis/kinesis-streams-encryption/step4.png"/>
5. Select the "Details" tab and scroll down to "Amazon S3 destination". Check the "Encryption" value and if it's set to "Disabled" then the selected "Firehose Delivery System" data is not encrypted. </br><img src="/resources/aws/kinesis/kinesis-streams-encryption/step5.png"/>
6. Repeat steps number 4 and 5 to verify another "Firehose Delivery System".</br>
7. To enable the "Encryption" on selected "Firehose Delivery System" click on the "Name" to access the delivery stream. Under the "Details" tab click on the "Edit" button to make the changes in "Amazon S3 destination". </br> <img src="/resources/aws/kinesis/kinesis-streams-encryption/step7.png"/>
8. Click on the "Enable" button next to the "S3 encryption" to enable the encryption. </br><img src="/resources/aws/kinesis/kinesis-streams-encryption/step8.png"/>
9. Choose the "KMS master key" from the dropdown list. Choose either the ("Default( aws/s3 )") KMS key or an AWS KMS Customer Master Key (CMK).</br><img src="/resources/aws/kinesis/kinesis-streams-encryption/step9.png"/>
10. Click on the "Save" button to make the necessary changes. On the successful configuration changes, one will get "Successfully updated delivery stream" message. </br> <img src="/resources/aws/kinesis/kinesis-streams-encryption/step10.png"/>
