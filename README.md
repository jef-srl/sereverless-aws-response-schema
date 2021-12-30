# Serverless Aws Response Schema Plugin

Plugin for Serverless Framework to add response model to AWS Rest API,
this will allow you to build documentation from API Gateway, complete with possible API Responses.

This plugin was build for our internal need. It could not work in every configuration.

This plugin has been generated using the `plugin` template from the [Serverless Framework](https://www.serverless.com/).

## Getting Started

Install the plugin via `npm i --save-dev serverless-aws-response-schema-plugin`
and add to the plugins section of your `serverless.yml`.

```yml
plugins:
  - serverless-aws-response-schema-plugin
```

Then you will be able to add configuration to your http events:

```yml
testSchema:
  handler: src/handler.default
  events:
    - http:
        path: /test
        method: ANY
        responseSchemas:
          200: 
            application/json: ${file(api-schemas/index.response.json)}
          500: 
            application/json: ${file(api-schemas/error.response.json)}
```
