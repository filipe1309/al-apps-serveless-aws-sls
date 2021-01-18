## Native AWS Lambda Workflow
mkdir my-lambda
cd my-lambda
npm init -y
touch index.js

### Dependency example moment
npm install moment

### Zip with index.js and dependencies
zip -r deploy.zip index.js node_modules
aws lambda update-function-code --function-name LAMBDA_NAME --zip-file fileb://deploy.zip

## SLS Lambda Workflow
sls create --template aws-nodejs --path cadastro-pacientes

sls invoke local -f hello