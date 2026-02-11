CLOUD FORMATION TEMPLATE:
==========================

CFT stands for CloudFormation Template. AWS CloudFormation is an Infrastructure as Code (IaC) service that allows you to model, provision, and manage AWS resources using a text file (a template). 

How CloudFormation Works:
=========================

 It creating and configuring resources (like EC2 instances, S3 buckets, or databases) in the AWS Management Console, you use a template written in JSON or YAML format. This template acts as a blueprint, describing all the resources you need and their dependencies. 


 What is the difference between AWS CFT and Terraform?:
 ======================================================

    1.CloudFormation is AWS native IaC tool, Terraform is third-party and multi-cloud.

    2.CloudFormation supports only AWS services, Terraform supports AWS, Azure, GCP, Kubernetes, and many tools.

    3.CloudFormation templates are written in YAML/JSON, Terraform uses HCL which is easier to read.

    4.CloudFormation manages state inside AWS stacks, Terraform uses a separate state file.

    5.Terraform provides a clear plan before applying changes, CloudFormation works through stack updates.

    6.Terraform is preferred in many companies for multi-cloud and modular infrastructure.


Is CloudFormation JSON or YAML?:
================================

    “AWS CloudFormation supports both JSON and YAML, but YAML is more commonly used because it’s easier to read and maintain.”

why we ares use cft and cli in aws:
===================================

AWS CloudFormation (CFT) and the AWS Command Line Interface (CLI) are used for different purposes and scenarios in managing AWS resources. The AWS CLI is used for quick, immediate tasks and automation through scripting, while AWS CloudFormation is used for defining, deploying, and managing entire cloud infrastructures in a repeatable and automated manner using Infrastructure as Code (IaC). 


Template structure for JSON:
============================

    {
      "AWSTemplateFormatVersion" : "version date",

      "Description" : "JSON string",

      "Metadata" : {
        template metadata
      },

      "Parameters" : {
        set of parameters
      },
  
      "Rules" : {
        set of rules
      },

      "Mappings" : {
        set of mappings
      },

      "Conditions" : {
        set of conditions
      },

      "Transform" : {
        set of transforms
      },

      "Resources" : {
        set of resources
      },
  
      "Outputs" : {
        set of outputs
      }
    }


Template structure for YAML:
==============================

    AWSTemplateFormatVersion: version date

    Description:
      String

    Metadata:
      template metadata

    Parameters:
      set of parameters

    Rules:
      set of rules

    Mappings:
      set of mappings

    Conditions:
      set of conditions

    Transform:
      set of transforms

    Resources:
      set of resources

    Outputs:
      set of outputs

using the below link for the template creation

https://docs.aws.amazon.com/AWSCloudFormation/latest/TemplateReference/introduction.html

why we are using detch drift in cloud formation:
================================================

We use Detect Drift in CloudFormation to check whether the actual AWS resources are different from what we defined in the template.

Sometimes, someone manually changes the resource from the AWS console — for example, modifying an S3 bucket setting or security group rule. But CloudFormation does not automatically know about that change. So the template and actual infrastructure become different. This situation is called drift.