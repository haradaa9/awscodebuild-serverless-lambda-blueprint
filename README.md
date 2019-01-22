## Summary

### How to use it

1. build serverless framework environment with AWS Codebuild.
https://github.com/haradaa9/sls_codebuild_docker
2. clone this repository and modify your code.
3. make AWS Codebuild project and build it.

### File Structure
```
├── README.md
├── buildspecs
│   ├── buildspec_ci.yml
│   └── buildspec_sls.yml
└── lambda
    ├── handler.py
    ├── requirements.txt
    └── serverless.yml
```

### Stack

- serverlss framework
- Python3.6
- serverless-python-requirements (serverlss framework plugin)

### Infrastracture

- AWS Codebuild
- AWS Lambda

### Local test
```
sls invoke local -f {function_name}
```

### AWS Codebuild Variable
```
codebuild_variable = {
  "AWS_ID": <CREDENTIAL_ID>, 
  "AWS_SECRET": <SECRET_KEY>, 
  "FUNCTION": <FUNCTION_NAME>
  }
```

### AWS Credential Setting with AWS SSM

```
aws ssm put-parameter --name key_name --type String --value <token>
```