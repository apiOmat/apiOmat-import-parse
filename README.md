<a href="https://github.com/apiOmat/apiOmat-import-parse">apiOmat-import-parse</a>
============

Import your exported data from Parse into the apiOmat backend.

This script will import your data and schemes from Parse into the backend of <a href="http://www.apiomat.com">apiOmat</a>.
See below for an example and a step-by-step guide how you do this

After the script is finished you can start with programming against apiOmat backend. For tutorials see <a href="http://www.apiomat.com/docs/">our documentation</a>

# Install

1. Goto <a href="https://apiomat.org/?locale=en&fromDashboard=false">SignUp</a> to create a new account on apiOmat.
 If you have an account already <a href="https://apiomat.org/?locale=en&free=true&fromDashboard=false#login">login</a> and create a new app.
2. Deploy your app to our cloud by pressing the deploy icon
3. Copy your 'ApiKey' from the App-Setup side in our dashboard. Take also note of the selected system in the left panel
4. Install <a href="http://www.pip-installer.org/en/latest/installing.html">pip</a> if not there already
5. Type 'pip install import-parse-to-apiOmat' on the command line to install the python script into your system
6. Goto your Parse dashboard and export your data as zip. For details see <a href="http://blog.parse.com/2012/03/09/one-click-export/">this link</a>
7. After you received the mail with your data, save them on your harddisk
8. See below for usage details

# Usage

```js
import-parse-to-apiOmat --ifile <path_to_zipfile> --appName <appName> --apiKey <apiKey> --userName <userName> --password <password> --system <usedSystem>
```
Explanation of parameters:
* --ifile <path_to_zipfile> Insert here filesystem path to the downloaded zip-file
* --appName <appName> The name of your app in apiOmat system
* --apiKey <apiKey> The apiKey copied in step 3 above
* --userName <userName> Your apiOmat username which you use to login in our dashboard
* --password <password> Your password which you use to login in our dashboard
* --system <usedSystem> The system (LIVE|STAGING|TEST) where you will import your data in the apiOmat cloud. (If you have selected the basic plan you can only import into LIVE system)
	
#Example
```js
import-parse-to-apiOmat  -i 9339.zip -a ParseImport -k 0000000 -s LIVE -u login@apiomat.org -p 12345
```

#Furthermore

See our tutorial about <a href="http://www.apiomat.com/docs/android-parse-comparison/">migrating</a> form Parse to apiOmat

# Known issues

* Can't import binary files, this Parse data format will be converted to a String and saves only the URL to the data
* No support for arrays with mixed types


# Contributing

This is open source. Feel free to modify and enhance this script