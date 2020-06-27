## Alexa Workshop Smart Home - Device Binding UI

This is the source code of [Step 1: Build Device Binding UI](https://alexaworkshop.com/smart-home/1.build-device-ui/).
If you are looking for the lab content, please visit the above link.

If you are looking for the whole lab, please visit [AWS & Alexa Workshop - Smart Home Skills](https://alexaworkshop.com/smart-home/).

If you have any issues, please create issues in [aws-samples/aws-alexa-workshop](https://github.com/aws-samples/aws-alexa-workshop/issues) repository.

![](aws_alexa.png)

## Notes

There are some info missed in this sample especially for newbie like me. Here are the info:
  1. Create a policy like the follow which is a working version for testing. You might limit `*` to the actual access right according to the build logs.
  ```json
  {
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "VisualEditor0",
            "Effect": "Allow",
            "Action": [
                "appsync:*",
                "amplify:*",
                "cloudformation:*",
                "s3:*",
                "cognito-idp:*",
                "cognito-identity:*",
                "dynamodb:*",
                "lambda:*",
                "iam:CreateRole",
                "iam:GetRole",
                "iam:DeleteRole",
                "iam:DeleteRolePolicy",
                "iam:PutRolePolicy",
                "iam:PassRole"
            ],
            "Resource": "*"
        }
    ]
}
```
  2. Create a role and attach the policy on it.
  3. Attach the role when you create the app on amplify.
  4. When you encount an error and before going to redeploy the app, check `CloudFormation` and `S3` and delete the related stack/bucket.
  5. When there is an error hard to guess, such as **Stack already exists**, but there are nothing in `CloudFormation`/`S3`, redeploy again. if it still didn't work, delete the current one and create a new one.
  
## License

This library is licensed under the MIT-0 License. See the LICENSE file.

