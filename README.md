<h1>Design and Secure a Personal Web Application</h1>


<h2>Description</h2>
This project consists of using Microsoft Azure to build and host a web application, secure it with an SSL certificate, and add security features to protect it. This incorporates topics such as: networking, network security, cryptography, terminal, cloud, and web development.
<br />


<h2>Languages and Utilities Used</h2>

- <b>Microsoft Azure</b> 

<h2>Activities:</h2>

<p align="left">
 <br/>
- Deploy web applications using Microsoft Azure Cloud.
Select "App Services" from the Azure search field:
<img src="https://imgur.com/oFJiQMD.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Under the "Basics" tab, make the following selections:
<br />
- Subscription/Resource Group: Azure subscription 1.
<br />
   - Name: Karlmsecurityreview
<br />
   - Publish: Select "Code."
<br />
   - Runtime Stack: Select "PHP 7.4."
<br />
   - Operating System: Select "Linux."
<br />
   - Region: Central US
  <br/>
<img src="https://imgur.com/jmf4Tt1.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
For the App Service Plan, complete the following steps:
<br />
   - Under "Linux Plan," select "Create New" and then enter "project1plan."
<br />
   - Under "Sku and size," select "Change size."
<br />
   - The spec picker will pop up on the right-hand side of your screen.
 <br />
          - Select "Dev/Test" and "Plan B1" (the green option), and then click "Apply," as the following image shows:
 <br/>
<img src="https://imgur.com/525WXMO.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Select "Custom domains" from the left-hand menu, then click "Add custom domain." In the "Custom domain" text box, enter the new domain, and then click "Validate." The following image shows these steps:  <br/>
<img src="https://imgur.com/noSuAim.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
 After selecting "Validate," the page will confirm whether the hostname is available.
<br />
   - Select the hostname record type "A Record," and notice the TXT and A data under "Domain ownership," as shown in the following image:
  <br/>
<img src="https://imgur.com/r4TYNYa.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Use a Docker container that has been added to Docker Hub. View the Docker container at the following location: [Cyber Blog Framework - Docker Container](https://hub.docker.com/r/cyberxsecurity/project1-apachewebserver).  <br/>
<img src="https://i.imgur.com/K71yaM2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Use the Azure Cloud Shell to deploy this container to your web application.
  <br/>
<img src="https://imgur.com/jHSUMlq.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
When using Shell, you may receive the following prompts:
<br />
       -  Select which shell to use (Bash or Powershell): Select "Bash."
<br />
       -  Create Storage: If a window appears, select "Create Storage."
<br />
Next, from the command line, you'll enter a command to configure your container.
  <br/>
<img src="https://imgur.com/i5z8DnB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
 <br/>
- After pressing enter, an output similar to the image below should appear:
<img src="https://imgur.com/IBd5oAg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
Customize the following elements of the webpage:
<br />
- Your name
<br />
- Your email
<br />
- Your LinkedIn profile link
<br />
- Your introduction
<br />
- Your picture
<br />
- Two custom blog posts on topics of your choice
<br />
You'll need to access the HTML pages of your new web application.
<br />
   - To access these pages, you need to SSH over to your container and access the HTML files.
<br />
   - Return to your web app in Azure, select "SSH" from the left-hand toolbar, and then select "GO," as shown in the following image:
 <br/>
<img src="https://imgur.com/lc31cEX.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://imgur.com/mlyc6wp.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
Create a Key Vault
<br />
Select "Key vaults" from the Azure search field at the top of the page
<br />
Select "+ Create" from the Key Vault page to create your key vault, as the following image shows:
 <br/>
<img src="https://imgur.com/noSuAim.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
On the "Create key vault" tab, make the following selections:
<br/>
   - Subscription/Resource Group: Select the same subscription and resource groups
<br/>
   - Key Vault Name: Choose a key vault name, such as `project1_KeyVault`
<br/>
   - Region: Select the same region that you selected
  <br/>
   - Pricing tier: Select the "Standard" tier.
  <br/>
   - Leave the default options for all of the other tabs (Access Policy, Networking, Tags).
  <br/>
<img src="https://imgur.com/HjuqenJ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
Create and Bind an App Service Managed Certificate complete the following steps:
 - Go to "TLS/SSL settings" under your web application.
<br />
 - Select "Private Key Certificates."
<br />
 - Select "+ Create App Service Managed Certificates."
<br />
 - When the pop-up appears on the right side of your screen, select your domain and click "Create," as the following image shows:
<br />
<img src="https://imgur.com/BFgpaII.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
 - Once your app service managed certificate has been created, return to the "Bindings" tab.
<br />
 - Select "+ Add TLS/SSL Binding."
<br />
 - When the pane appears on the right side of your screen, select your domain and the new certificate that you just created.
<br />
 - Select "SNI/SSL" for the TLS/SSL type, then click "Add Binding."
<br />
<img src="https://imgur.com/F1ZCxc9.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
Create a Front Door Instance by completing the following steps:
 - Access the app service resource under the web application.
<br />
 - From the menu on the left side of the screen, select "Networking."
<br />
 - select "Azure Front Door" under "More networking features," as the following image shows:
<br />
<img src="https://imgur.com/v9uliyL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
 - On the next page, select "Create new" under "Front Door instance."
<br />
- This will open a pane on the right side of your screen.
<br />
- In this pane, name your Front Door "project1-FrontDoor".
<br />
 - Leave the default settings to create a default **web application firewall (WAF)**.
<br />
 - Click the "Add" button at the bottom of the pane, as the following image shows:
<br />
<img src="https://imgur.com/ta3rHUJ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
- Click "OK" to update the Front Door instance to your application, as the following image shows:
<br />
<img src="https://imgur.com/TlYaZWy.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
- To verify that your Front Door instance has been set up correctly, select "Azure Front Door" again. The message "Azure Front Door is configured for your web app" should display as confirmation, as shown in the following image:
<br />
<img src="https://imgur.com/IINTX5H.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
Analyze and configure WAF Rule Sets by completing the following steps:
- Enter "web app" until "Web Application Firewall policies (WAF)" appears as one of the choices in the dropdown.
<br />
- Select that option. The WAF that you created during the previous step should display on the "Web Application Firewall policies (WAF)" page. 
<br />
- Select WAF
<br />
- Select "Managed rules" either from the left-hand toolbar or from the box at the bottom of the page.
<br />
- When the "Managed rules" page appears, scroll through the page to view the various rules.
<br />
- Select "Custom rules" from the toolbar on the left-hand side of the screen
<br />
- To create a custom rule, select "+ Add custom rule."
<br />
- Name the custom rule "Project1rule."
<br />
- Leave the status and rule type at the default options.
<br />
- Set the priority to 100.
<br />
- Set the following terms for the rule's condition:
<br />
- Match type: Geo location
<br />
- Operation: is not
<br />
- Select the three countries (USA, Canada, Australia)
<br />
- Then: Deny traffic
<br />
- Then, click "Add." 
<br />
- custom rule should now display on the page, as the following image shows:
<br />
<img src="https://imgur.com/u5eJIvh.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
Observe the completed web application:  <br/>
<img src="https://imgur.com/K6wfSeB.png" height="80%" width="80%" alt="Screenshot"/>
</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
