# Get Started With AWSome

Glad you're interested in checking AWSome out. To start making the most of AWSome you will need to have your AWS credentials ready so if you don't have those setup, let's do that before moving on.

If you do have your credentials, that's great. Feel free to just [skip ahead then](#step-5-install-the-awsome-dependency)

Otherwise, please read on to setup your AWS account.

* [STEP 1: Get an AWS Account](#step-1-get-an-aws-account)
* [STEP 2: Login to your AWS Console](#step-2-login-to-your-aws-console)
* [STEP 3: Create a new AWS user](#step-3-create-a-new-aws-user)
  * [3.1 Choose a username](#31-choose-a-username)
  * [3.2 Select access type](#32-select-access-type)
  * [3.3 Move on to permissions](#33-move-on-to-permissions)
  * [3.4 Create a group](#34-create-a-group)
  * [3.5 Choose a group name](#35-choose-a-group-name)
  * [3.6 Confirm group creation](#36-confirm-group-creation)
  * [3.7 Verify that the group was created](#37-verify-that-the-group-was-created)
  * [3.8 Review the new user](#38-review-the-new-user)
  * [3.9 Confirm user creation](#39-confirm-user-creation)
  * [3.10 Store your user credentials somewhere safe](#310-store-your-user-credentials-somewhere-safe)
* [STEP 4: Create a group policy](#step-4-create-a-group-policy)
  * [4.1 Go to the group](#41-go-to-the-group)
  * [4.2 Create a custom policy](#42-create-a-custom-policy)
  * [4.3 Give it a name and add the content](#43-give-it-a-name-and-add-the-content)
  * [4.4 Apply the policy](#44-apply-the-policy)
  * [4.5 Verify that the policy was created](#45-verify-that-the-policy-was-created)
* [STEP 5: Install the awsome dependency](#step-5-install-the-awsome-dependency)
  * [5.1: Add the AWS environment variables](#51-add-the-aws-environment-variables)
  * [5.2 Browse the examples](#52-browse-the-examples)

## STEP 1: Get an AWS Account

Let's get your AWS account up and running. If you don't have an AWS account, not to worry, this guide will help you set one up, just continue reading.

If you do have an account, that's great. Just [skip ahead then](#step-5-install-the-awsome-dependency)

So you don't have an AWS Account yet. Not to worry, it takes 5 minutes or less to get one.

Just go ahead and [create your free AWS account now](https://portal.aws.amazon.com/billing/signup?nc2=h_ct&redirect_url=https%3A%2F%2Faws.amazon.com%2Fregistration-confirmation#/start) and let's continue once you've completed the sign up process.

[![](images/step-1.png)]()

## STEP 2: Login to your AWS Console

AWS has a nice online console that you can access whenever you want to manage your AWS resources.

So let's go now and [login to your AWS console](https://console.aws.amazon.com/) so we can create a new user. Just login with your **email** and **password** that you used to create your account.

[![](images/step-2.png)]()

## STEP 3: Create a new AWS user

We don't always want to access your AWS account with your email and password, because that's not secure, so instead, AWS allows you to create special users that are more secure to use.

We want to create such a user now, so let's go ahead and [start the New User Wizard](https://console.aws.amazon.com/iam/home?region=us-east-1#/users$new?step=details) and complete it step by step.

[![](images/step-3-start.png)]()

#### 3.1 Choose a username

First, give your user a name (call your user **awsome**).

[![](images/step-3-1.png)]()

#### 3.2 Select access type

Next, check both check boxes to specify that you want *Programmatic access* and *AWS Management Console access* as well. And let the *Autogenerated password* and the *Require password reset* boxes selected.

[![](images/step-3-2.png)]()

#### 3.3 Move on to permissions

Click the **Next: Permissions** button to go and set some permissions for the new user.

[![](images/step-3-3.png)]()

#### 3.4 Create a group

Click the **Create group** button to create a brand new group for your new user.

[![](images/step-3-4.png)]()

#### 3.5 Choose a group name

Type **awsome** as the name of the group (yeah let's keep it identical to the user name we created in [Step 3.1](#3-1-choose-a-username))

[![](images/step-3-5.png)]()

#### 3.6 Confirm group creation

Click the **Create group** button to finish the process, and don't worry about the policy stuff, just ignore that.

[![](images/step-3-6.png)]()

#### 3.7 Verify that the group was created

Almost there. Good job, you just created a brand new group. We are ready to move on and finish creating the user as well.

[![](images/step-3-7.png)]()

#### 3.8 Review the new user

Click the **Next: Review** button to review our new user.

[![](images/step-3-8.png)]()

#### 3.9 Confirm user creation

Looks good! Let's just go ahead and confirm that we want to finish the process now. Just click the **Create user** button to finish.

[![](images/step-3-9.png)]()

#### 3.10 Store your user credentials somewhere safe

Amazing! You've got yourself a brand new user. Congrats! You will notice the *Access key ID* and the *Secret access key* that come with your user. Those are very important and we need those to access your account. The *Secret access key* is especially sensitive that's why AWS hides that.

Now, just click the *Show* link next to the *Secret access key* and do the same for the *Password* and copy the values and store them somewhere safe.

Use a Password Manager like [1Password](https://1password.com/) or do whatever you do with all your sensitive information like passwords or credit card numbers. But whatever you do, make sure these are safe and treat them as you would any sensitive information - with utmost care for their security.

Congratulations, you now have your AWS user credentials handy and ready to be used with AWSome.

[![](images/step-3-10.png)]()

## STEP 4: Create a group policy

Policies are used in AWS to give users specific permissions to AWS resources. You can give a user permission to everything but in general that's a security concern.

So what we want to do is to give our **awsome** user we created, the permissions it needs and not a permission more.

##### 4.1 Go to the group

We want to [start out by going to the awsome group](https://console.aws.amazon.com/iam/home?region=us-east-1#/groups/awsome) actually, and not the user, so that we can control the permissions at the group level.

Click on the *Inline Policies* section to expand it and the lick the *click here* link to create a policy.

[![](images/step-4-start.png)]()

#### 4.2 Create a custom policy

Next, select the *Custom Policy* section and press the *Select* button.

[![](images/step-4-1.png)]()

#### 4.3 Give it a name and add the content

Just give your policy a name - **awsome** will work - and enter the following text for the policy:

<details>
<summary> Expand to see the policy text </summary>
```
{
  {
      "Version": "2012-10-17",
      "Statement": [
          {
              "Sid": "awsomepolicy1",
              "Action": [
                  "s3:headBucket",
                  "s3:createBucket",
                  "s3:listObjectsV2",
                  "s3:deleteBucket",
                  "s3:getBucketWebsite",
                  "s3:putBucketWebsite",
                  "s3:putBucketPolicy",
                  "s3:deleteBucketWebsite",
                  "s3:putObject",
                  "s3:deleteObject",
                  "route53:listHostedZones",
                  "route53:createHostedZone",
                  "route53:deleteHostedZone",
                  "route53:listResourceRecordSets",
                  "route53:changeResourceRecordSets"
              ],
              "Effect": "Allow",
              "Resource": "*"
          }
      ]
  }
```
</details>

[![](images/step-4-2.png)]()

#### 4.4 Apply the policy

Click the **Apply Policy** button to apply our new policy to the group.

[![](images/step-4-3.png)]()

#### 4.5 Verify that the policy was created

You did it! You have not only created a new user with its own group but you've attached a policy to your group.

This is great. Your AWS account is now ready to go.

[![](images/step-4-done.png)]()

## STEP 5: Install the ```awsome``` dependency

Great, you should have your AWS user credentials now (key and secret) so you can just install AWSome and start using it.

To install, just add ```awsome``` to your NPM module like so:

```
npm i -S awsome
```

Then you can import ```awsome``` in your code as follows:

```
const awsome = require('awsome')

```

#### 5.1 Add the AWS environment variables

AWSome expects your AWS user credentials to be available as environment variables, as documented in the [official AWS SDK Node.js documentation](https://docs.aws.amazon.com/sdk-for-javascript/v2/developer-guide/loading-node-credentials-environment.html).

The two environment variables we want are ```AWS_ACCESS_KEY_ID``` and ```AWS_SECRET_ACCESS_KEY```. These are the values you created in [Step 3.10](#3-10-store-your-user-credentials-somewhere-safe) and that you stored somewhere safe.

It does not matter how the variables end up in the environment, as long as the Node.js process can find them in the ```process.env``` object. You can set them at the command prompt or you can load them from a secure location at runtime and inject them in the ```process.env```.

***Whatever you do, make sure your credentials are safe and secure and are not exposed in your code***

If you do want to inject them at run time, here's how you can do that:

```
process.env.AWS_ACCESS_KEY_ID = <inject value>
process.env.AWS_SECRET_ACCESS_KEY = <inject value>
```

#### 5.2 Browse the examples

Good stuff! That's all there is to it. You are now ready to start using AWSome.

Please have a look at the [examples](https://github.com/fluidtrends/awsome/tree/master/examples) to see what you can do with AWSome.

Have a look at the list of examples available:

* [```Creating a bucket```](https://github.com/fluidtrends/awsome/blob/master/examples/create-bucket.js)
* [```Retrieving a bucket```](https://github.com/fluidtrends/awsome/blob/master/examples/retrieve-bucket.js)
* [```Updating a bucket```](https://github.com/fluidtrends/awsome/blob/master/examples/update-bucket.js)
* [```Deleting a bucket```](https://github.com/fluidtrends/awsome/blob/master/examples/delete-bucket.js)
* [```Hosting a domain```](https://github.com/fluidtrends/awsome/blob/master/examples/host-domain.js)
* [```Unhosting domain```](https://github.com/fluidtrends/awsome/blob/master/examples/unhost-domain.js)
* [```Linking bucket to a domain```](https://github.com/fluidtrends/awsome/blob/master/examples/link-bucket.js)
* [```Unliking a bucket from a domain```](https://github.com/fluidtrends/awsome/blob/master/examples/unlink-bucket.js)


Have fun!
