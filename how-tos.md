<a name="toc"></a>
## Table of Contents 

- [Configure access to Prometeo](#access)
- [Creating an Ansible Command for Testing a  Configuration Set](#testing_cmd)
- [Creating SSH keys for remote host access](#ssh_keys)
- [Configure user with sudo access](#sudo_user)

<a name="access"></a>
### Configure Prometeo ([up](#toc))

Add Chrome extension to the browser:
 
https://chrome.google.com/webstore/detail/modheader/idgpnmonknjnojddfkpgkljpfnnfcklj
 
In the Chrome extension, set the following settings:
 
**Request header**
Authorization: Basic <Authorisation Token>
 
**Filter**
URL pattern: \*://<prometeo-hostname>/\*
 
When you browse to https://prometeo-hostname you should see a response of “OK” – this means that the request has hit the Prometeo Auth front-end correctly and gone through to Prometeo itself.

<a name="testing_cmd"></a>
### Creating an Ansible Command for Testing a  Configuration Set ([up](#toc))

To create an Ansible command that contains all environment variables formatted as a JSON string and passed in --extra-vars use [Prometeo](https://github.com/prometeo-cloud/prometeo)'s
**peek** http resource.

The resource can be accessed using Prometeo's [Swagger UI](https://github.com/prometeo-cloud/prometeo/blob/master/readme.md#web_api_doc).

An example payload for the peek resource can be found [here](https://github.com/prometeo-cloud/prometeo/blob/master/readme.md#executing-a-configuration-repository-up).
git pull origin
The HTTP response should contain the payload variables converted in a format that can be executed on the command line for testing in the local machine.

<a name="ssh_keys"></a>
### Creating SSH keys for remote host access ([up](#toc))

To connect to the host a key pair should be generated:

```bash
$ ssh-keygen -t rsa -C "email@example.com"
```

Optionally, add the generated key to the local ssh-agent file to enable SSH to find the key without the need to specify its location every time that you connect:

```bash
$ ssh-add ~/.ssh/id_rsa
```
Add the public key to the host as an authorized key using **ssh-copy-id**. Its purpose is to provision access without requiring a password for each login.

```bash
$ ssh-copy-id -i ~/.ssh/id_rsa user@host
```
To test the key do the following:

```bash
$ ssh -i ~/.ssh/id_rsa user@host
```
<a name="sudo_user"></a> 
### [Configure user with sudo access](https://access.redhat.com/documentation/en-US/Red_Hat_Enterprise_Linux_OpenStack_Platform/2/html/Getting_Started_Guide/ch02s03.html) ([up](#toc))