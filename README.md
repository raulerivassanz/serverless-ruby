# Serverless Ruby!

A Serverless Framework example using an AWS lambda which runs a Ruby function. Inspired by [serverless-php](https://github.com/ZeroSharp/serverless-php). 

This project demonstrates a few cool technlogies. Foremost is the amazing AWS Lambda. It's pretty exciting to serverless architectures gaining adoption! Adding to the fun we have [serverless](https://serverless.com/), a framework for packaging and deploying across different providers including AWS, Google and IBM. Also worth mentioning is the inclusion of Ruby. AWS Lambda supports a number of different languages natively, but Ruby is not one of them. Therefore we specially bundle the Ruby interpreter (courtesy of [Traveling Ruby](http://phusion.github.io/traveling-ruby/)) and wrap it in a Node.js script which executes it as a binary.

## Prerequsites

1. `npm install -g serverless`
2. Create a new user `serverless` in AWS Console, download the `credentials.csv` file and setup provider: [https://www.youtube.com/watch?v=HSd9uYj2LJA]()

## Install

```
serverless install --url https://github.com/stewartlord/serverless-ruby
./build-ruby.sh
```

## Deploy Function
```
$ serverless deploy
Serverless: Packaging service...
Serverless: Creating Stack...
Serverless: Checking Stack create progress...
.....
Serverless: Stack create finished...
Serverless: Uploading CloudFormation file to S3...
Serverless: Uploading artifacts...
Serverless: Uploading service .zip file to S3 (7.21 MB)...
Serverless: Updating Stack...
Serverless: Checking Stack update progress...
........................
Serverless: Stack update finished...
Service Information
service: serverless-ruby
stage: dev
region: us-east-1
api keys:
  None
endpoints:
  GET - https://xxxxxxxxxx.execute-api.us-east-1.amazonaws.com/dev/hello
functions:
  hello: serverless-ruby-dev-hello
```

## Try It Out!
```
$ serverless invoke --function=hello --log
{
    "statusCode": 200,
    "body": "hello"
}
```