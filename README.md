```shell
$ curl -s -N --compressed https://d1uauaxba7bl26.cloudfront.net/latest/gzip/CloudFormationResourceSpecification.json | pcregrep -o1 '          "(.*?)"' | sort | uniq -c | sort -nr
# missing a few https://github.com/awsdocs/aws-cloudformation-user-guide/issues/4#issuecomment-503828259
5443 UpdateType
5443 Required
5443 Documentation
4283 PrimitiveType
1493 Type
 448 ItemType
 445 DuplicatesAllowed
 352 PrimitiveItemType

$ curl -s -N --compressed https://d1uauaxba7bl26.cloudfront.net/latest/gzip/CloudFormationResourceSpecification.json | pcregrep -o1 '("UpdateType": ".*?)"' | sort | uniq -c | sort -nr
4030 "UpdateType": "Mutable
1370 "UpdateType": "Immutable
  47 "UpdateType": "Conditional

$ curl -s -N --compressed https://d1uauaxba7bl26.cloudfront.net/latest/gzip/CloudFormationResourceSpecification.json | pcregrep -o1 '("Required": .*?),' | sort | uniq -c | sort -nr
3689 "Required": false
1758 "Required": true

$ curl -s -N --compressed https://d1uauaxba7bl26.cloudfront.net/latest/gzip/CloudFormationResourceSpecification.json | pcregrep -o1 '("DuplicatesAllowed": .*?),' | sort | uniq -c | sort -nr
 313 "DuplicatesAllowed": false
 132 "DuplicatesAllowed": true

$ curl -s -N --compressed https://d1uauaxba7bl26.cloudfront.net/latest/gzip/CloudFormationResourceSpecification.json | pcregrep -o1 '("PrimitiveType": .*?),' | sort | uniq -c | sort -nr
3046 "PrimitiveType": "String"
 382 "PrimitiveType": "Integer"
 368 "PrimitiveType": "Boolean"
  99 "PrimitiveType": "Json"
  63 "PrimitiveType": "Double"
   8 "PrimitiveType": "Long"
   4 "PrimitiveType": "Timestamp"
   1 "PrimitiveType": "Map"

$ curl -s -N --compressed https://d1uauaxba7bl26.cloudfront.net/latest/gzip/CloudFormationResourceSpecification.json | pcregrep -o1 '("PrimitiveItemType": .*?),' | sort | uniq -c | sort -nr
 349 "PrimitiveItemType": "String"
   2 "PrimitiveItemType": "Boolean"
   1 "PrimitiveItemType": "Json"

$ curl -s -N --compressed https://d1uauaxba7bl26.cloudfront.net/latest/gzip/CloudFormationResourceSpecification.json | pcregrep -o1 '("Type": .*?),' | sort | uniq -c | sort -nr
 735 "Type": "List"
  48 "Type": "Map"
  ..

$ curl -s -N --compressed https://d1uauaxba7bl26.cloudfront.net/latest/gzip/CloudFormationResourceSpecification.json | pcregrep -o1 '("ItemType": .*?),' | sort | uniq -c | sort -nr
 108 "ItemType": "Tag"
 ...

$ curl -s -N --compressed https://d1uauaxba7bl26.cloudfront.net/latest/gzip/CloudFormationResourceSpecification.json | pcregrep -o1 '::(.*)::' | sort | uniq -c | wc -l
      91 # services
      
$ curl -s -N --compressed https://d1uauaxba7bl26.cloudfront.net/latest/gzip/CloudFormationResourceSpecification.json | pcregrep -o1 '::(.*)::[^.]*"' | wc -l
$ curl -s -N --compressed https://d1uauaxba7bl26.cloudfront.net/latest/gzip/CloudFormationResourceSpecification.json | pcregrep -o1 '"(.*?)::[^.]*"' | sort | uniq -c | sort -nr
     423 # resource types
     422 AWS
       1 Alexa

$ curl -s -N --compressed https://d1uauaxba7bl26.cloudfront.net/latest/gzip/CloudFormationResourceSpecification.json | pcregrep -o1 '::(.*)::.*\..*' | wc -l
     970 # property types

$ curl -s -N --compressed https://d1uauaxba7bl26.cloudfront.net/latest/gzip/CloudFormationResourceSpecification.json | pcregrep -o1 '::(.*)::[^.]*"' | sort | uniq -c | sort -nr
  53 EC2 # resource types per service
  19 ApiGateway
  16 Greengrass
  15 Pinpoint
  13 ServiceCatalog
  11 WAFRegional
  11 Glue
  11 ApiGatewayV2
   9 RDS
   9 IAM
   7 WAF
   7 SSM
   7 OpsWorks
   7 Lambda
   7 Cognito
   7 AppStream
   6 SES
   6 RoboMaker
   6 IoT
   6 GuardDuty
   6 ElastiCache
   6 DMS
   6 AppSync
   5 ServiceDiscovery
   5 SageMaker
   5 Redshift
   5 Neptune
   5 Logs
   5 ElasticLoadBalancingV2
   5 EMR
   5 Config
   5 CloudFormation
   5 AutoScaling
   5 AppMesh
   4 SecretsManager
   4 Route53
   4 PinpointEmail
   4 KinesisAnalyticsV2
   4 IoTAnalytics
   4 ElasticBeanstalk
   4 DocDB
   3 SNS
   3 Route53Resolver
   3 KinesisAnalytics
   3 IoT1Click
   3 Inspector
   3 GameLift
   3 ECS
   3 DAX
   3 CodePipeline
   3 CodeDeploy
   3 CloudFront
   3 Batch
   3 Amplify
   3 AmazonMQ
   2 Transfer
   2 StepFunctions
   2 SQS
   2 S3
   2 Kinesis
   2 KMS
   2 Events
   2 EFS
   2 DirectoryService
   2 CloudWatch
   2 ApplicationAutoScaling
   1 WorkSpaces
   1 SDB
   1 RAM
   1 OpsWorksCM
   1 MediaStore
   1 MSK
   1 KinesisFirehose
   1 IoTThingsGraph
   1 FSx
   1 Elasticsearch
   1 ElasticLoadBalancing
   1 EKS
   1 ECR
   1 DynamoDB
   1 DataPipeline
   1 DLM
   1 CodeCommit
   1 CodeBuild
   1 CloudTrail
   1 Cloud9
   1 CertificateManager
   1 Budgets
   1 AutoScalingPlans
   1 Athena
   1 ASK
```
