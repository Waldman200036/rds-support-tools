# [Query your AWS database from your serverless application](https://aws.amazon.com/blogs/database/query-your-aws-database-from-your-serverless-application/#Set)

by Deana Holmer | on 19 MAR 2018 | in Database, Serverless | Permalink |  Comments |  Share
AWS database customers want to save money, scale seamlessly, and enjoy high availability by not having to launch Amazon Elastic Compute Cloud (Amazon EC2) hosts in their virtual private cloud (VPC) to use as database clients. An application that you run without provisioning or managing an EC2 host is known as a serverless application.

In this post, I show you how to query an AWS database from a URL, even if the database is not publicly accessible. You can even run it against an Amazon Aurora Serverless database for a serverless-to-serverless query! I provide a selection of Python scripts that work for Amazon Neptune, Amazon Relational Database Service (Amazon RDS) for MySQL, or Amazon RDS for PostgreSQL, respectively. I also walk you through setting up and creating the following two components:

The AWS Lambda function that executes your query against your backend database
The API Gateway REST API that invokes the Lambda function when you access the URL
I provide an AWS CloudFormation template that makes creating these components a snap. And I include substantial Tips and Troubleshooting sections specifically for querying databases in an Amazon VPC that are not strictly key-value stores.

The Python code samples apply best practices that can easily be adapted for other database engines. For Neptune, the SPARQL example can be adapted for Gremlin.

You can download the Python code and the AWS CloudFormation template from the awslabs/rds-support-tools GitHub repository.

This post is intended for AWS database users who have no experience with AWS Lambda, Amazon API Gateway, or AWS CloudFormation, and limited experience with Python. The time to complete the steps is about 30 minutes.
