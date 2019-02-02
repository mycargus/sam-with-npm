# sam-with-npm

This repo is the companion to my article on [packaging Lambda functions with `npm pack`](https://hackernoon.com/package-lambda-functions-the-easy-way-with-npm-e38fc14613ba).

## Try it out

Clone this repository, then:

`cd sam-with-npm/hello_world`

`npm install`

`npm pack`

`cd ..`

`aws s3 mb s3://sam-with-npm`

`sam package --template-file template.yaml --output-template-file packaged.yaml --s3-bucket sam-with-npm`

`sam deploy --template-file packaged.yaml --stack-name sam-with-npm --capabilities CAPABILITY_IAM`

`aws cloudformation describe-stacks --stack-name sam-with-npm --query 'Stacks[].Outputs'`
