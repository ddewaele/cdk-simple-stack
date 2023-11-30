# cdk-simple-stack

To build and deploy your application for the first time, run the following in your shell:

```bash
sam build
sam deploy
```

To delete the stack

```bash
sam delete --no-prompts
```


To deploy the UI (manual for now)

```bash
BUCKET_NAME=cdk-simple-stack-websitebucket-11lh4idw5f1y7
aws s3 cp --recursive . s3://$BUCKET_NAME
```

Deleting items in the bucket

```bash
aws s3 rm s3://$BUCKET_NAME --recursive
```

## Verifying the API 

```bash
curl -v -H "Authorization: $TOKEN" https://143zx7upja.execute-api.eu-central-1.amazonaws.com/prod/api
curl -v -H "Authorization: $TOKEN" https://app2.ecommit-consulting.com/api/
```

curl -v https://api2.my-tst-playground.com/default/hello


## Use the SAM CLI to build and test locally

Build your application with the `sam build` command.

```bash
cdk-simple-stack$ sam build
```
Run functions locally and invoke them with the `sam local invoke` command.

```bash
cdk-simple-stack$ sam local invoke HelloWorldFunction --event events/event.json
```

The SAM CLI can also emulate your application's API. Use the `sam local start-api` to run the API locally on port 3000.

```bash
cdk-simple-stack$ sam local start-api
cdk-simple-stack$ curl http://localhost:3000/
```


## Unit tests

Tests are defined in the `hello-world/tests` folder in this project. Use NPM to install the [Jest test framework](https://jestjs.io/) and run unit tests.

```bash
cdk-simple-stack$ cd hello-world
hello-world$ npm install
hello-world$ npm run test
```

## Cleanup

To delete the sample application that you created, use the AWS CLI. Assuming you used your project name for the stack name, you can run the following:

```bash
sam delete --stack-name cdk-simple-stack
```

## Resources

See the [AWS SAM developer guide](https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/what-is-sam.html) for an introduction to SAM specification, the SAM CLI, and serverless application concepts.

Next, you can use AWS Serverless Application Repository to deploy ready to use Apps that go beyond hello world samples and learn how authors developed their applications: [AWS Serverless Application Repository main page](https://aws.amazon.com/serverless/serverlessrepo/)

- https://scriptingis.life/Cognito-AWS-SAM/
- https://www.rehanvdm.com/blog/cloudfront-reverse-proxy-api-gateway-to-prevent-cors
- https://rahullokurte.com/a-guide-to-using-aws-intrinsic-functions-in-your-sam-templates#heading-what-are-aws-intrinsic-functions-in-aws-sam-templates
- https://blog.bitsrc.io/passwordless-authentication-for-better-security-ba986df663b7
- https://www.npmjs.com/package/amazon-cognito-identity-js
- https://github.com/oauth2-proxy/oauth2-proxy
- https://asokkumarsusitharan.medium.com/how-to-protect-single-page-applications-spas-using-asgardeo-and-oauth2-proxy-13e02358d543
- https://docs.aws.amazon.com/cdk/api/v2/docs/aws-cdk-lib.aws_ecs_patterns-readme.html
