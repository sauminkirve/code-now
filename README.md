code-now-CodeChef
=================

A chrome/chromium plugin for CodeChef / SPOJ to instantly open your Favorite IDE

What it does !!
---------------

It is a simple chrome/chromium plugin for **Linux Users** which adds 3 button to every CodeChef / SPOJ Problem Page (one for each of C, C++ and Java).
Clicking on each button will open up your favorite IDE for that language instantly with a default template !! It is particularly useful during short contests.

You can choose different IDEs for different Languages. Templates can also be different for different Languages.


Prerequisites
-------------

Any Linux Distro /  MAC OS X, Google Chrome Browser, Python 2.7 or above and Your favorite IDEs

Google Chrome can be installed from here : https://www.google.com/chrome/browser/
Chromium Browser can be installed via Ubuntu Software or by typing following command :
```sh
sudo apt-get install chromium-browser
```


Installation
------------

Easy 2-step Installation. Download the latest release here -> [Release v4.0](https://github.com/ashish1294/code-now-CodeChef/releases/download/v4/code-now-CodeChef-v4.0.zip) and unzip it

1. **Install Plugin** - The chrome plugin is available for free installation on Chrome Web Store. Install it [here](https://chrome.google.com/webstore/detail/code-now-for-codechef-spo/eiifebdnfcadjhgenpanagdankjhkjeb)

2. **Install Host Program** - A simple script has been provided for installation of the host script on your machine which can communicate with the chrome plugin. Before installing, please edit the template files provided. These templates will be automatically added to all your solutions. After editing Templates you can first set the executable bit of the install.sh script and then execute it.

```sh
cd PATH_TO_INSTALL_FOLDER
chmod +x install.sh
./install.sh
```

You can configure your default IDEs for each of the 3 languages during installation. In case you need to re-configure your templates or IDEs please reinstall the host program by runnning the installation script again.

Development
-----------

This a small app. Most code is self explainatory. Three primary languages - js, shell-scripting and python. You might use IDE if you want. The flow of the system is :

1. JS script runs on all problem pages. Extracts the problem information and adds the button. Click Listenors sends the data to native host.
2. Native host is a python script on local system. It reads the data and makes a new file, add appropriate header and then starts a the IDE on a separate thread.
3. Shell Script is useful to install the system. It checks for dependencies and configures the values used in python script.

If you want to contribute / work with the code you have to check the "developer mode" on the top right corner of the chrome's extension page. After that use the chrome's **Load Unpacked Extension** feature for working with javascripts. Note that while using this method only the javascript will run but the native messaging will actually not work due to the a different extension **ID**. You have to pack the extension using the **Pack Extension** feature in developer mode and then install the packed extension for Native Host to work. The Private Key to pack the extension is included in the repository. To avoid packing extension everytime you make changes to plugin you can load the unpacked extension and then change the codenow.json file with the extension id generated by chrome when you load the unpacked extension.

```python
"allowed_origins": [
    "chrome-extension://eiifebdnfcadjhgenpanagdankjhkjeb/"
  ]
```

Refer the todo.md file for a list of features that you can add to this application

Contributors
------------

Following is a list of contributors:

1. Ashish Kedia ([@ashish1294](https://github.com/ashish1294))
2. Dementor ([@sam17](https://github.com/sam17))
3. Sahil Dua ([@sahildua2305](https://github.com/sahildua2305))
