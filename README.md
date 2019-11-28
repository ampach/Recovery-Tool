# Recovery-Tool

**Recovery Tool** is a SIF extension which serves to help developers to quickly restore Sitecore instances after reinstalling OS.

**[Recovery-Tool.zip](https://github.com/ampach/Recovery-Tool/raw/master/Recovery-Tool.zip)** contains the list of files that represent a configuration for SIF to recovery App_Pools, Websites, Windows Services, Solr cores:

* xconnect-xp0.json
* xconnect-solr.json
* sitecore-XP0.json
* sitecore-solr.json
* RecoveryTool.ps1
* RecoveryTool.json
* IdentityServer.json
* createcert.json

Before using the tool, you need to ensure that you have all prerequisites installed:

1) Open PowerShell as an administrator and navigate to the folder where you have unzipped the package. 
2) Run the following cmdlet to set up prerequisites:
```powershell
Install-SitecoreConfiguration -Path .\Prerequisites.json 
```
When the installation is complete, you might be informed that a server reboot is required.  

Follow the steps below to recover your previous Sitecore instance:

1) Navigate to the folder where you have unzipped the package.
2) In the folder, edit the RecoveryTool.ps1 script and update each line with the settings that are appropriate for your environment.  
3) Open PowerShell as an administrator and navigate to the folder where you have unzipped the package.
4) Run the following cmdlet to recover you instance:
```powershell
	.\RecoveryTool.ps1
  ```
5) Choose **Install** when you are asked.

Ones the recovering is finished, you will have your Sitecore instance restored. Recovery Tool does the following:
* Creates IIS Application Pool;
* Creates IIS Site;
* Sets bindings;
* Updates the hosts file with selected bindings;
* Sets up and run windows services such as XConnect Search Indexer, Sitecore Marketing Automation Engine and Sitecore Processing Engine;
* Creates and populates Solr cores.

