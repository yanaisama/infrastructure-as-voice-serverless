# infrastructure-as-voice-serverless
Sample application that combines Alexa skills with AWS Systems Manager to automate instances management

Alexa Skill Development

npm install -g ask-cli
ask init

A browser will be open for you to log in with your Alexa account.
You optionally can create a profile for your AWS account access.

ask clone

AccessDeniedException: User: arn:aws:iam::187707271747:user/dev01 is not authorized to perform: lambda:GetFunction on resource: arn:aws:lambda:us-east-1:187707271747:function:aws-serverless-repository-alexaskillskitnodejsfact-16MZ475GFLM0X

ask new --skill-name 'CloudControl'

cd CloudControl
ask deploy

Your skill is now deployed and enabled in the development stage. Try simulate your Alexa skill skill using "ask dialog" command.


ask diff


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
    


