# infrastructure-as-voice-serverless
Sample application that combines Alexa skills with AWS Systems Manager to automate instances management

![alt text](https://github.com/yanaisama/infrastructure-as-voice-serverless/blob/master/architecture.png)


Alexa Skill Development
```
#npm install -g ask-cli
#ask init
```

A browser will be open for you to log in with your Alexa account.
You optionally can create a profile for your AWS account access.

```
#ask clone
#ask new --skill-name 'CloudControl'
```

You are already able to deploy your skill using the following commands:

```
#cd CloudControl
ask deploy

Your skill is now deployed and enabled in the development stage. Try simulate your Alexa skill skill using "ask dialog" command.
```

You can now edit your skill either locally using any Editor or directly on Alexa developer console.

To see the differences between your local version and what you have on Alexa service, use the following command:
```
ask diff
```

Snippet for create an instance via AWS Systems Manager inside Lambda function

```
var params = {
      DocumentName: 'AWS-CreateManagedLinuxInstance', /* required */
      Parameters: {
        'AmiId': [
          'ami-00dc79254d0461090'
        ],
        'KeyPairName': ['yanaikp']
      }
    };
    ssm.startAutomationExecution(params, function(err, data) {
      if (err) console.log(err, err.stack); // an error occurred
      else     console.log(data);           // successful response
    });
 ```

To deploy only the Lambda function use the following command

```
ask deploy -t lambda
```
