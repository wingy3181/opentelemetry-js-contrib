# How to

## Run `packages` scripts

To run scripts for a specific package, use the following commands:

- For example, `packages/instrumentation-aws-lambda`
  In project root directory, run:
  ```
  npx nx run instrumentation-aws-lambda:lint
  npx nx run instrumentation-aws-lambda:compile
  npx nx run instrumentation-aws-lambda:compile:with-dependencies
  npx nx run instrumentation-aws-lambda:version:update
  ```

## Publish packages to npm under personal scope

To publish packages to npm under personal scope:

- For example, `packages/instrumentation-aws-lambda`
  - Ensure `package.json` has been updated with correct scope, repo name and version.
    ```diff
    diff --git a/packages/instrumentation-aws-lambda/package.json b/packages/instrumentation-aws-lambda/package.json
    index caba2375a5cf..2fddd3a6b7bc 100644
    --- a/packages/instrumentation-aws-lambda/package.json
    +++ b/packages/instrumentation-aws-lambda/package.json
    @@ -1,12 +1,12 @@
    {
    -  "name": "@opentelemetry/instrumentation-aws-lambda",
    -  "version": "0.54.0",
    +  "name": "@wingy3181/instrumentation-aws-lambda",
    +  "version": "0.54.0-sqs.context.propagation",
    "description": "OpenTelemetry instrumentation for AWS Lambda function invocations",
    "main": "build/src/index.js",
    "types": "build/src/index.d.ts",
    "repository": {
    "type": "git",
    -    "url": "https://github.com/open-telemetry/opentelemetry-js-contrib.git",
    +    "url": "https://github.com/wingy3181/opentelemetry-js-contrib.git",
    "directory": "packages/instrumentation-aws-lambda"
    },
    "scripts": {
    @@ -65,5 +65,5 @@
    "@opentelemetry/semantic-conventions": "^1.27.0",
    "@types/aws-lambda": "8.10.150"
    },
    -  "homepage": "https://github.com/open-telemetry/opentelemetry-js-contrib/tree/main/packages/instrumentation-aws-lambda#readme"
    +  "homepage": "https://github.com/wingy3181/opentelemetry-js-contrib/tree/main/packages/instrumentation-aws-lambda#readme"
    }
    ```
  In package directory (e.g. `packages/instrumentation-aws-lambda/`) run:
  - Login to npm: `npm login`
  - Publish packages: `npm publish --tag experimental`
