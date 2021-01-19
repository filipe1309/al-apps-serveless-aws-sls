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

###