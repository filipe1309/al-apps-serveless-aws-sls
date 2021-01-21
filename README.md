# AWS Serveless with Serveless Framework
## Native AWS Lambda Workflow
```
mkdir my-lambda
cd my-lambda
npm init -y
touch index.js
```
### Dependency example moment
```
npm install moment
```

### Zip with index.js and dependencies
```
zip -r deploy.zip index.js node_modules
aws lambda update-function-code --function-name LAMBDA_NAME --zip-file fileb://deploy.zip
```

## Serveless Framework
## SLS Lambda Workflow
```
sls create --template aws-nodejs --path cadastro-pacientes
```

### Local invoke
```
sls invoke local -f hello
sls invoke local -f listarPacientes
```

### Local invoke with parameters
```
sls invoke local -f listarPacientes -d '{"teste": "teste"}'
```

### Deploy
```
sls deploy
sls deploy --stage qa
```

### Get AWS Cli Current identity
```
aws sts get-caller-identity
aws sts get-caller-identity --profile user1
```


## Api Gateway
Frontend -> API Gateway -> Lambdas

### SLS Get AWS logs (after soma executions)
```
sls logs -f obterPaciente --tail
```

### SLS deploy only on function
```
sls deploy  -f obterPaciente
```

### SLS get infos
```
sls info
```


### Plugins

#### SLS Offline
To test API Gateway + Lambda offline  
https://github.com/dherault/serverless-offline
```
npm init -y
npm install serverless-offline --save-dev
sls offline
```

#### DynamoDB Local
```
npm i serverless-dynamodb-local --save-dev && sls dynamodb install
```

## API Designs Guides
https://docs.microsoft.com/en-us/azure/architecture/best-practices/api-design  
https://cloud.google.com/apis/design


## DynamoDB
```
npm i aws-sdk
```

### Populate AWS DynamoDB with JSON
```
aws dynamodb batch-write-item --request-items file://pacientes.json

aws dynamodb list-tables
aws configure get region

npm i uuid
```

### Populate AWS DynamoDB with JSON Fixtures
```
npm run fixtures
```

sls offline start
http://localhost:3000/dev/pacientes?limit=10&next=d90cd737-74c6-4772-89c0-592546b0dea1



sls deploy --stage qa
