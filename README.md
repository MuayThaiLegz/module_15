# module_15

We want to increase their client portfolio—especially by engaging young people. Because machine learning and NLP are disrupting finance to improve the customer experience, you decide to create a robo advisor. Both existing and potentially new customers will be able to use this robo advisor to get investment portfolio recommendations for retirement.


You’ll be asked to accomplish the following main tasks:

Configure the initial robo advisor: Define an Amazon Lex bot with a single intent that establishes a conversation about requirements to suggest an investment portfolio for retirement.

Build and test the robo advisor: Make sure that your bot works and accurately responds during the conversation with the user.

Enhance the robo advisor with an Amazon Lambda function: Create an Amazon Lambda function that validates the user's input and returns the investment portfolio recommendation. This includes testing the Amazon Lambda function and integrating it with the bot.

# Overview
This is a sample [Amazon Lex](https://aws.amazon.com/lex/)
web interface. It provides a chatbot UI component that can be integrated
in your website. The interface allows a user to interact with a Lex bot directly
from a browser using text or voice.

#### Features include:
- Mobile ready responsive UI with full page or embeddable widget modes
- Support for voice and text with the ability to seamless switch from
one mode to the other
- Voice support provides automatic silence detection, transcriptions
and ability to interrupt responses and replay recordings
- Display of Lex response cards
- Ability to programmatically configure and interact with the chatbot
UI using JavaScript

------

![aws lambda intro image](https://static01.m-square.com.au/wp-content/uploads/2017/04/media.amazonwebservices.comAWS-Lex-Lambda-Chatbot-Ch-c5bbfce23bb59aa51bf92c10e637a0ed2b183bf2.png)

# Learn Aws Lambda


Learn to use AWS Lambda to create scalable micro-services in less time
and cost *far* less to run than "*traditional*" server-based apps.

[![Codeship](https://img.shields.io/codeship/dc9ad800-a8a7-0133-6c3b-2a9c037ce78e/master.svg?style=flat-square)](https://github.com/codeship/documentation/issues/335)
[![codecov.io](https://codecov.io/github/dwyl/learn-aws-lambda/coverage.svg?branch=master)](https://codecov.io/github/dwyl/learn-aws-lambda?branch=master)
[![dependencies Status](https://david-dm.org/dwyl/learn-aws-lambda/status.svg)](https://david-dm.org/dwyl/learn-aws-lambda)
[![devDependencies Status](https://david-dm.org/dwyl/learn-aws-lambda/dev-status.svg)](https://david-dm.org/dwyl/learn-aws-lambda?type=dev)
[![contributions welcome](https://img.shields.io/badge/contributions-welcome-brightgreen.svg?style=flat)](https://github.com/dwyl/learn-aws-lambda/issues)


## Contents

* [What is Lambda?](#what-is-lambda)
* [How does it work?](#how)
* [Create and Test Your Own AWS Lambda Function](#create-and-test-your-own-aws-lambda-function)
* [Further Reading](#further-reading)
* [Glossary](#glossary)
* [Concerns](#concerns)
* [Pricing](#lambda-pricing)
* [FAQ](#faq)

## What is Lambda?

Amazon Web Services (AWS) Lambda lets you run JavaScript (Node.js), Java & Python
scripts/apps in Amazon's (virtually) infinitely-scalable cloud environment
without having provision VM instances or other "*orchestration*";
Everything is dynamically auto-scaled so if you have 1 user or 1 billion
you pay for *usage*.

### *Self*-Disruption

AWS are effectively [*disrupting*](https://en.wikipedia.org/wiki/Disruptive_innovation)
their (*own*) *existing* business with Lambda.
Instead of forcing us to pay for EC2 instances in fixed increments and
have complex application monitoring/scaling, AWS have
built a *much simpler* way of building & running *micro-services*.

Lambda also disrupts other Platform-as-a-Service ("**PaaS**") providers
such as Heroku, Google App Engine, Azure or Modulus where you pay for a
*specific* amount of compute power & RAM but have a ***scaling delay*** and
scale in a ***fixed increment*** (instances).

### Lambda Features

#### Ephemeral Storage

No access to a filesystem or memory persistence (e.g. on-instance Redis)
so you cannot store data or the `result` of an operation *locally*.

#### Use an AWS Datastore Service

The lack of *local* persistence on Lambda is resolved by having
low-latency access to AWS S3 and *other* AWS Datastores e.g:
[ElastiCache](https://aws.amazon.com/elasticache/) (in-memory cache),
[DynamoDB](http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Introduction.html) (NoSQL ssd-based database),
[RDS](https://aws.amazon.com/rds/) (*relational database*),
however there's an
important (and potentially *expensive*) catch: PUT/POST/GET requests to all
AWS data stores are **NOT** Free! While per-run costs on Lambda are tiny, if you GET and PUT
something to S3 on each execution cycle you could rack up the bill!
