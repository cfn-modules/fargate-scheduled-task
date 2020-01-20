[![Build Status](https://travis-ci.org/cfn-modules/fargate-scheduled-task.svg?branch=master)](https://travis-ci.org/cfn-modules/fargate-scheduled-task)
[![NPM version](https://img.shields.io/npm/v/@cfn-modules/fargate-scheduled-task.svg)](https://www.npmjs.com/package/@cfn-modules/fargate-scheduled-task)

# cfn-modules: Fargate scheduled task

Executing an AWS Fargate task based on a schedule (comparable to a `cronjob` on Linux). Uses AWS Step Functions to control and monitor the task execution.

> :books: Check out our new book [Rapid Docker on AWS](https://cloudonaut.io/rapid-docker-on-aws/?utm_source=aws-velocity&utm_medium=doc&utm_campaign=readme)
> * Written for DevOps engineers and web developers who want to run dockerized web applications on AWS.
> * Prior knowledge of Docker and AWS is not required.
> * Continuous Deployment of your Web Application and Infrastructure as Code.

## Install

> Install [Node.js and npm](https://nodejs.org/) first!

```
npm i @cfn-modules/fargate-scheduled-task
```

## Usage

```
---
AWSTemplateFormatVersion: '2010-09-09'
Description: 'cfn-modules example'
Resources:
  ScheduledTask:
    Type: 'AWS::CloudFormation::Stack'
    Properties:
      Parameters:
        ClusterModule: !GetAtt 'Cluster.Outputs.StackName' # required
        VpcModule: !GetAtt 'Vpc.Outputs.StackName' # required
        AlertingModule: '' # optional
        ClientSgModule1: '' # optional
        ManagedPolicyArns: '' # optional
        AppImage: '' # optional
        AppEntryPoint: '' # optional
        AppCommand: '' # optional
        AppEnvironment1Key: '' # optional
        AppEnvironment1Value: '' # optional
        AppEnvironment1SecretModule: '' # optional
        AppEnvironment2Key: '' # optional
        AppEnvironment2Value: '' # optional
        AppEnvironment2SecretModule: '' # optional
        AppEnvironment3Key: '' # optional
        AppEnvironment3Value: '' # optional
        AppEnvironment3SecretModule: '' # optional
        AppEnvironment4Key: '' # optional
        AppEnvironment4Value: '' # optional
        AppEnvironment5Key: '' # optional
        AppEnvironment5Value: '' # optional
        AppEnvironment6Key: '' # optional
        AppEnvironment6Value: '' # optional
        SidecarImage: '' # optional
        SidecarPort: '' # optional
        SidecarEnvironment1Key: '' # optional
        SidecarEnvironment1Value: '' # optional
        SidecarEnvironment1SecretModule: '' # optional
        SidecarEnvironment2Key: '' # optional
        SidecarEnvironment2Value: '' # optional
        SidecarEnvironment2SecretModule: '' # optional
        SidecarEnvironment3Key: '' # optional
        SidecarEnvironment3Value: '' # optional
        SidecarEnvironment3SecretModule: '' # optional
        Cpu: '' # optional
        Memory: '' # optional
        LogsRetentionInDays: '' # optional
        SubnetsReach: '' # optional
        ScheduleExpression: 'rate(15 minutes)' # optional
        Timeout: '' # optional
      TemplateURL: './node_modules/@cfn-modules/fargate-scheduled-task/module.yml'
```

## Examples

none

## Related modules

none

## Parameters

<table>
  <thead>
    <tr>
      <th>Name</th>
      <th>Description</th>
      <th>Default</th>
      <th>Required?</th>
      <th>Allowed values</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>ClusterModule</td>
      <td>Stack name of <a href="https://www.npmjs.com/package/@cfn-modules/ecs-cluster">ecs-cluster module</a></td>
      <td></td>
      <td>yes</td>
      <td></td>
    </tr>
    <tr>
      <td>VpcModule</td>
      <td>Stack name of <a href="https://www.npmjs.com/package/@cfn-modules/vpc">vpc module</a></td>
      <td></td>
      <td>yes</td>
      <td></td>
    </tr>
    <tr>
      <td>AlertingModule</td>
      <td>Stack name of <a href="https://www.npmjs.com/package/@cfn-modules/alerting">alerting module</a></td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>ClientSgModule1</td>
      <td>Stack name of <a href="https://www.npmjs.com/package/@cfn-modules/client-sg">client-sg module</a> module to mark traffic from EC2 instance</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>ManagedPolicyArns</td>
      <td>Comma-delimited list of IAM managed policy ARNs to attach to the task's IAM role</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>    
    <tr>
      <td>AppImage</td>
      <td>The Docker image to use for the app container. You can use images in the Docker Hub registry or specify other repositories (repository-url/image:tag)</td>
      <td>widdix/hello:v1</td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>AppEntryPoint</td>
      <td>Optional entry point for app container.</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>AppCommand</td>
      <td>Optional command for app container.</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>AppEnvironment1Key</td>
      <td>Environment variable 1 key for app container</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>AppEnvironment1Value</td>
      <td>Environment variable 1 plain-text value for app container (if AppEnvironment1Key is set, set either AppEnvironment1Value or AppEnvironment1SecretModule)</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>AppEnvironment1SecretModule</td>
      <td>Environment variable 1 stack name of <a href="https://www.npmjs.com/package/@cfn-modules/secret">secret module</a> for app container (if AppEnvironment1Key is set, set either AppEnvironment1Value or AppEnvironment1SecretModule)</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>AppEnvironment2Key</td>
      <td>Environment variable 2 key for app container</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>AppEnvironment2Value</td>
      <td>Environment variable 2 plain-text value for app container (if AppEnvironment2Key is set, set either AppEnvironment2Value or AppEnvironment2SecretModule)</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>AppEnvironment2SecretModule</td>
      <td>Environment variable 2 stack name of <a href="https://www.npmjs.com/package/@cfn-modules/secret">secret module</a> for app container (if AppEnvironment2Key is set, set either AppEnvironment2Value or AppEnvironment2SecretModule)</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>AppEnvironment3Key</td>
      <td>Environment variable 3 key for app container</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>AppEnvironment3Value</td>
      <td>Environment variable 3 plain-text value for app container (if AppEnvironment3Key is set, set either AppEnvironment3Value or AppEnvironment3SecretModule)</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>AppEnvironment3SecretModule</td>
      <td>Environment variable 3 stack name of <a href="https://www.npmjs.com/package/@cfn-modules/secret">secret module</a> for app container (if AppEnvironment3Key is set, set either AppEnvironment3Value or AppEnvironment3SecretModule)</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>AppEnvironment4Key</td>
      <td>Environment variable 4 key for app container</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>AppEnvironment4Value</td>
      <td>Environment variable 4 plain-text value for app container</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>AppEnvironment5Key</td>
      <td>Environment variable 5 key for app container</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>AppEnvironment5Value</td>
      <td>Environment variable 5 plain-text value for app container</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>AppEnvironment6Key</td>
      <td>Environment variable 6 key for app container</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>AppEnvironment6Value</td>
      <td>Environment variable 6 plain-text value for app container</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>SidecarImage</td>
      <td>Docker image to use for the sidecar container. You can use images in the Docker Hub registry or specify other repositories (repository-url/image:tag)</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>SidecarPort</td>
      <td>The port exposed by the sidecar container reachable from the app container on host localhost (SidecarPort != ProxyPort != AppPort)</td>
      <td>9000</td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>SidecarEnvironment1Key</td>
      <td>Environment variable 1 key for sidecar container</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>SidecarEnvironment1Value</td>
      <td>Environment variable 1 plain-text value for sidecar container (if SidecarEnvironment1Key is set, set either SidecarEnvironment1Value or SidecarEnvironment1SecretModule)</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>SidecarEnvironment1SecretModule</td>
      <td>Environment variable 1 stack name of <a href="https://www.npmjs.com/package/@cfn-modules/secret">secret module</a> for sidecar container (if SidecarEnvironment1Key is set, set either SidecarEnvironment1Value or SidecarEnvironment1SecretModule)</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>SidecarEnvironment2Key</td>
      <td>Environment variable 2 key for sidecar container</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>SidecarEnvironment2Value</td>
      <td>Environment variable 2 plain-text value for sidecar container (if SidecarEnvironment2Key is set, set either SidecarEnvironment2Value or SidecarEnvironment2SecretModule)</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>SidecarEnvironment2SecretModule</td>
      <td>Environment variable 2 stack name of <a href="https://www.npmjs.com/package/@cfn-modules/secret">secret module</a> for sidecar container (if SidecarEnvironment2Key is set, set either SidecarEnvironment2Value or SidecarEnvironment2SecretModule)</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>SidecarEnvironment3Key</td>
      <td>Environment variable 3 key for sidecar container</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>SidecarEnvironment3Value</td>
      <td>Environment variable 3 plain-text value for sidecar container (if SidecarEnvironment3Key is set, set either SidecarEnvironment3Value or SidecarEnvironment3SecretModule)</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>SidecarEnvironment3SecretModule</td>
      <td>Environment variable 3 stack name of <a href="https://www.npmjs.com/package/@cfn-modules/secret">secret module</a> for sidecar container (if SidecarEnvironment3Key is set, set either SidecarEnvironment3Value or SidecarEnvironment3SecretModule)</td>
      <td></td>
      <td>no</td>
      <td></td>
    </tr>
    <tr>
      <td>Cpu</td>
      <td>The minimum number of vCPUs to reserve for the container</td>
      <td>0.25</td>
      <td>no</td>
      <td>[0.25, 0.5, 1, 2, 4]</td>
    </tr>
    <tr>
      <td>Memory</td>
      <td>The amount (in GB) of memory used by the task</td>
      <td>0.5</td>
      <td>no</td>
      <td>[0.5, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30]</td>
    </tr>
    <tr>
      <td>LogsRetentionInDays</td>
      <td>Specifies the number of days you want to retain log events in the specified log group</td>
      <td>14</td>
      <td>no</td>
      <td>[1, 3, 5, 7, 14, 30, 60, 90, 120, 150, 180, 365, 400, 545, 731, 1827, 3653]</td>
    </tr>
    <tr>
      <td>SubnetsReach</td>
      <td>Should the service have direct access to the Internet or do you prefer private subnets with NAT?</td>
      <td>Public</td>
      <td>no</td>
      <td>[Public, Private]</td>
    </tr>
    <tr>
      <td>ScheduleExpression</td>
      <td>The schedule or rate (frequency) that determines when CloudWatch Events runs the rule (for valid values, see http://docs.aws.amazon.com/AmazonCloudWatch/latest/events/ScheduledEvents.html)</td>
      <td>rate(1 hour)</td>
      <td>yes</td>
      <td></td>
    </tr>
    <tr>
      <td>Timeout</td>
      <td>The timeout for a task execution in seconds.</td>
      <td>600</td>
      <td>yes</td>
      <td></td>
    </tr>
  </tbody>
</table>
