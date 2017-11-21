## Table of Contents

- [Configure access to Prometeo](#access)
- [Creating an Ansible Command for Testing a  Configuration Set](#testing_cmd)

<a name="access"></a>
### Configure Prometeo 

Add Chrome extension to the browser:
 
https://chrome.google.com/webstore/detail/modheader/idgpnmonknjnojddfkpgkljpfnnfcklj
 
In the Chrome extension, set the following settings:
 
**Request header**
Authorization: Basic <Authorisation Token>
 
**Filter**
URL pattern: \*://<prometeo-hostname>/\*
 
When you browse to https://prometeo-hostname you should see a response of “OK” – this means that the request has hit the Prometeo Auth front-end correctly and gone through to Prometeo itself.


<a name="testing_cmd"></a>
### Creating an Ansible Command for Testing a  Configuration Set

To create an Ansible command that contains all environment variables formatted as a JSON string and passed in --extra-vars use [Prometeo](https://github.com/prometeo-cloud/prometeo)'s
**peek** http resource.

The resource can be accessed using Prometeo's [Swagger UI](https://github.com/prometeo-cloud/prometeo/blob/master/readme.md#web_api_doc).

An example payload for the peek resource can be found [here](https://github.com/prometeo-cloud/prometeo/blob/master/readme.md#executing-a-configuration-repository-up).
git pull origin
The HTTP response should contain the payload variables converted in a format that can be executed on the command line for testing in the local machine.
