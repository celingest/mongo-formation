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

**Benchmark's Results** are available at our blog [MongoDB, réplicas en AWS](http://blog.celingest.com/2013/01/15/mongodb-replicas-en-aws/) and templates are commented at [Creando réplicas de MongoDB con CloudFormation](http://blog.celingest.com/2013/01/25/mongodb-replicas-cloudformation/). (Next week these posts will be available in English too)

To use the templates
--------------------

The easiest way is to download **MongoStackCLNGS-2.cftemplate** then go to [AWS:CloudFormation](https://console.aws.amazon.com/cloudformation/home) -> **Create New Stack** -> Upload a Template File, choose the file you just downloaded. Now You can fill the form and launch the CloudFormation.

You can also use directly the RAW version of this file and use its url: [https://raw.github.com/celingest/mongo-formation/master/MongoStackCLNGS-2.cftemplate](https://raw.github.com/celingest/mongo-formation/master/MongoStackCLNGS-2.cftemplate) in **Create New Stack** -> Provide a Template URL.

Our template uses an external template file located in our S3 bucket: [https://s3-eu-west-1.amazonaws.com/mongodb-clngs/MongoNodeCLNGS-2.cftemplate](https://s3-eu-west-1.amazonaws.com/mongodb-clngs/MongoNodeCLNGS-2.cftemplate), you can download the [https://raw.github.com/celingest/mongo-formation/master/MongoNodeCLNGS-2.cftemplate](https://raw.github.com/celingest/mongo-formation/master/MongoNodeCLNGS-2.cftemplate) file and upload it to your own URL, then modify the main template.




