# Examples Deploynig .NET Core  With AWS CodePipeline


This repo is an example of how to setup a AWS CodePipeline that builds a GitHub repository containing an ASP.NET Core 2.1
application using CodeBuild and then deploying to Elastic Beanstalk.

The file [beanstalk-cloudformation.template](./CodePipelineSetup/beanstalk-cloudformation.template) takes in a GitHub repo
information and existing Elastic Beanstalk environment and sets up the CodeBuild project and CodePipeline.

The [buildspec.yml](./buildspec.yml) builds the project. It uses the [Amazon.ElasticBeanstalk.Tools](https://github.com/aws/aws-extensions-for-dotnet-cli)
.NET Core Global Tool to package up the application and required the required JSON manifest 
[aws-windows-deployment-manifest.json](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/dotnet-core-tutorial.html) file.

