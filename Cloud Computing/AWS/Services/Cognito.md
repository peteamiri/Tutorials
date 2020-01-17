# AWS Cognito 

* Cognito is an Identity Provider (Idp). 
* it is used to provide authorization and authantication of a user for mobile and web-aps 
* It is Also is an Identity Broker, it means that it generates a temporary access credentials to a user after the user is authanticated by a third party Idp. 
* it uses predefined IAM roles, for authorization, allowing users to access various AWS resources. 
* It is a development tool

# Identity provider (Idp)

* it is a registry / repository of authorized users. 
* it can catagorise users into groups. 

# Identity Broken 

* allow use of thrird party Idp
	* Active Directory 
	* Social Media 

# Cognito as a development tool

* Provides programming access  (API's) to interact with the Cognito services. 

* It provides the following development kits,
	* JavaScript (Web apps)
	* iOS (iPhone)
	* Andriod SDK (Andriod devices)

* Cognito is serverless service, 
	* use API to add or remove users
	* Fully maintained and managed by AWS
	* it uses AWS API using Json. 
	* need to write client code to interact with Cognito

# Workflow offered by Cognito

* Signup / Signin with MFA (and challenges like adding security questions or send code to user mobile phone)
* User profile management allows api to access user information and add custom attributes. 
* Forgot password/ password reset. 
* Email and Mobile Phone number varification
* Allows lifecycle hocks using Lambda functions. These are refered to as lifecycles trigers. 
* Allows gust (unAuthanticated) users. 
* Uses Secure Remote Password protocl. All password are encrypted and never in clear text in transition. 

# High level workflow Steps and states to add users

You need to fully understand these flows to write a proper interface. 

1. signup : trigers the Cognito API to control the flow. (registered state)
1. Confirmation : confirms email or mobile (state : confirmed) at this stage user can login 
	1. you can auto confirm the users (by-pass the confirmation stage)

* For Admin users and bulk registry you can by-pass the above steps. 
* Admin will add the user and they are in registered state. They get a on-time use password. 
* they are forced to chaneg password. they are changed to Confirmed state. 

* you still have to write code for the GUI to allow users to perform the above

* users can be enabled or disables (state disabled) and then deleted. 

## LifeCycle Trigers

There are three categories of trigers;

1. Registeration lambda triggers
	* pre-signup triger
	* custom message 
	* post confirmation trigger
1. Authantication lambda triggers
	* Pre-auth 
	* custom message 
	* post-auth trigger
1. Custom auth lambda triggers 
	* Define auth challenge
	* Create auth challenge 
	* Verify auth challenge resposne

### For more information see

* [Intro to Cognito](https://www.youtube.com/watch?v=cLfmS4j8u0w)






