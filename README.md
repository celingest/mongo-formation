MongoFormation
==============

These are our **CloudFormation** templates to create a testbed to benchmark **MongoDB in AWS** using different AMIs types and Performance Optimized EBS with PIOPS.

We used the templates provided by 10gen at MongoDB website [Automating Deployment with CloudFormation](http://www.mongodb.org/display/DOCS/Automating+Deployment+with+CloudFormation) as a reference, modifying parts according to our needs:

* Limit the access to only one IP/Network;
* Deploy using the latest AMIs and two different Availability Zones;
* Permit the use of MongoDB's REST interface;
* Use an optimized setup;
* Spread Replicas over optimized EBS using LVM instead of Raid10 or Raid0;
* Add extra checks and configurations to fully automate the process;
* Extra tags on CloudFormation objects to facilitate their identification.

**Benchmark's Results** are available at our blog [Benchmarking MongoDB Replica Set in AWS](http://blog.celingest.com/en/2013/02/01/benchmarking-mongodb-replica-aws/) and templates are commented at [Creating MongoDB Replicas with CloudFormation](http://blog.celingest.com/en/2013/02/01/creating-mongodb-replicas-with-cloudformation/). )

To use the templates
--------------------

The easiest way is to download **MongoStackCLNGS-2.cftemplate** then go to [AWS:CloudFormation](https://console.aws.amazon.com/cloudformation/home) -> **Create New Stack** -> Upload a Template File, choose the file you just downloaded. Now You can fill the form and launch the CloudFormation.

You can also use directly the RAW version of this file and use its url: [https://raw.github.com/celingest/mongo-formation/master/MongoStackCLNGS-2.cftemplate](https://raw.github.com/celingest/mongo-formation/master/MongoStackCLNGS-2.cftemplate) in **Create New Stack** -> Provide a Template URL.

Our template uses an external template file located in our S3 bucket: [https://s3-eu-west-1.amazonaws.com/mongodb-clngs/MongoNodeCLNGS-2.cftemplate](https://s3-eu-west-1.amazonaws.com/mongodb-clngs/MongoNodeCLNGS-2.cftemplate), you can download the [https://raw.github.com/celingest/mongo-formation/master/MongoNodeCLNGS-2.cftemplate](https://raw.github.com/celingest/mongo-formation/master/MongoNodeCLNGS-2.cftemplate) file and upload it to your own URL, then modify the main template.

Update
------

Last template release works seamlessy also in EC2 Default VPC. You can find the more details in our Blog: [MongoDB 2.4 Replicas with CloudFormation in Default VPC](http://blog.celingest.com/en/2013/07/05/mongodb-2-4-replicas-cloudformation-default-vpc/)

Credits
-------

[Celingest](http://celingest.com/en)

[Blog Celingest](http://blog.celingest.com/en)




