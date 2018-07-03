# Storage - S3

## Storages Option

* S3: Serverless
* Glacier: Long term archive data storage, lowest cost, take long time(3-4 hr) to restore back on S3
* EBS (Elastic Block Storage):basically like a disk drive
* Storage Gateway: High Speed link between on-premises storage of an enterprise to AWS
* EFS (Elastic File Server):similar to connect a NAS to your network
* AWS Import Export Snowball: like a portable hard drive, large physical device, then import data into it, send back to AWS, AWS will import that to your service

## Architecture

* EC2 <1-(many)> EBS, in each annotated VPC, like attach a hard drive at home.
* EC2 (#1) <1-many> EBS EC2 (#1)<many-1> EFS via mount point
* VPC Endpoint <1-1> S3 Bucket with object <-> Glacier Vault *N.B.* Amazon S3 is not allocated within VPC
* Hybrid Storage Example: AWS S3 <-> AWS Storage Gateway/import & export Snowball <-> Onsite Storage in corporate data centre, usually being used in disaster recovery solution.