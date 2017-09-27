How to create a HTML Extension on Microsoft Project Honolulu
===================

This project is a quick introduction of the posibilities of the new Microsoft Project Honolulu. We will create a new simple HTML module and add it into the Project.

----------

### Getting started
* First, please install Microsoft Project Honolulu from here > [http://aka.ms/honoluludownload](http://aka.ms/honoluludownload)
* Once installed, all the design files are locate here "C:\ProgramData\Server Management Experience\Ux\" 

* Let's open the manifest.json, then we will add our module to the top of the modules section, it should start the file like this:
```
{
  "name": "msft.sme.shell",
  "signature": "version 0.0.0",
  "modules": [
    {
      "$schema": "../node_modules/@msft-sme/core/dist/manifest/module-schema.json#",
      "name": "veeam.sme.vac-manager",
      "target": "/modules/veeam.sme.vac-manager",
      "entryPoints": [
          {
              "entryPointType": "tool",
              "name": "veeam.sme.vac-manager",
              "urlName": "veeam.sme.vac-manager",
              "displayName": "Veeam Backup & Replication",
              "icon": "https://go.veeam.com/rs/veeam/images/icon_v10_Management_VA_green.svg",
              "requirements": [
                  {
                      "solutionIds": [
                          "msft.sme.server-manager!servers"
                      ],
                      "connectionTypes": [
                          "msft.sme.connection-type.server"
                      ]
                  }
              ]
          }
      ],
      "version": "0.0.1"
    },
```
* Save it. It might be read-only, so you might want to copy to desktop and then copy/paste it manually.
* As you can see the HTML module we are creating is called veeam.sme.vac-manager and it's located on /modules/veeam.sme.vac-manager.
* So next step is to create the folder veeam.sme.vac-manager inside the modules folder
* Download the index.html and place it inside the veeam.sme.vac-manager folder
* Last but not least, restart the service called Project Honolulu 


----------

### Additional Information
* This is just the begining of something really big, I hope to see so many integrations for this project, which will help IT Administrators to reduce the troubleshooting tasks.
* If you do edit the index.php, bear in mind to don't touch the next  if (event.data.signature !== 'version 0.0.0') { or it will fail to check the module.
* Special thanks to Hongtao Chen, who has published the HTML module for Microsoft Project Honolulu