# Cisco Duo: Setting up MFA for RDP access

<p align="center">
<img src="https://github.com/Manny-D/Cisco-Duo-MFA-for-RDP/assets/99146530/524ca371-b064-4f7e-ae0d-87d1fac7aa16" alt="Duo Logo"/>
</p>

<br>

## Description
In this project, we explore how to strengthen a server's defenses by adding Duo Security's Multi-Factor Authentication (MFA) to RDP (remote desktop protocol) connections. This extra layer of security ensures only authorized users can access our server, keeping our data safe.

<b>Note</b>: This project is using an already spun up Microsoft Azure Virtual Machine (VM) running Server 2019.

<br>

## Cisco Duo Account Creation

Sign Up for a Free trial account by signing up [here](https://signup.duo.com/).

![Duo Signup](https://github.com/Manny-D/Cisco-Duo-MFA-for-RDP/assets/99146530/8a6cc378-235e-4d14-bb50-ec1ee28b7ecd)


On the left pane, expand <b>Users</b> -> click <b>Add User</b> -> enter the required fields 

![Users](https://github.com/Manny-D/Cisco-Duo-MFA-for-RDP/assets/99146530/dbae158d-af1e-44ba-a038-9c49a28cccbc)

A confirmation email will be sent with an enrollment link. Click on the link.

![Confirmation email](https://github.com/Manny-D/Cisco-Duo-MFA-for-RDP/assets/99146530/48b76ddc-9a5e-458f-b91c-3fad5c2c54a4)

Install and launch the mobile application on your smartphone. <br>
[Android App](https://play.google.com/store/apps/details?id=com.duosecurity.duomobile&hl=en_US&gl=US) <br>
[Apple App](https://apps.apple.com/us/app/duo-mobile/id422663827) <br>

Scan the QR code. 

![Duo QR Code](https://github.com/Manny-D/Cisco-Duo-MFA-for-RDP/assets/99146530/a7720201-fa73-4097-936d-323c03defacd)

The application will guide you through the remaining steps.

<br>

## Duo installation on Microsoft Server 2019 (VM)

Login to the server, open a web browser and log in to the Duo Admin [UI](https://admin.duosecurity.com/login?next=%2F).

![Duo Admin login](https://github.com/Manny-D/Cisco-Duo-MFA-for-RDP/assets/99146530/5c48ed68-f121-402d-aa8d-7abfef7d264c)


On the left pane, expand <b>Applications</b> -> click on <b>Protect an Application</b> -> search for rdp -> click on <b>Protect</b>

<img src="https://i.imgur.com/ai8tLPh.png" height="70%" width="70%" alt="9"/><br />

On the next page, download the "Duo Authentication for Windows Login Installer" package and open the downloaded file when finished. 

<img src="https://i.imgur.com/HQYTeRN.png" height="70%" width="70%" alt="9"/><br />

Copy and paste the API hostname into the InstallShield Wizard.

![API hostname](https://github.com/Manny-D/Cisco-Duo-MFA-for-RDP/assets/99146530/8b7547d2-3172-4373-bcb9-85f39b8e5a45)

Do the same for the Integration Key and Secret Key then click <b>Next</b>.

![Int and Sec keys](https://github.com/Manny-D/Cisco-Duo-MFA-for-RDP/assets/99146530/d6d7b3d0-c394-4e00-a532-81703ebaf6e1)

For this project, in the settings that follow (like the ones pictured below) no changes are necessary - eg. keep them at their default. 

![Screenshot 2024-05-02 at 11 51 47 AM](https://github.com/Manny-D/Cisco-Duo-MFA-for-RDP/assets/99146530/60285558-7a51-4ae3-b5b0-ebf7d2b6a607)

Continue clicking <b>Next</b> till you get to the <b>Install Wizard Completed</b> part, then click <b>Finish</b> to start the installer. 

<img width="374" alt="Screenshot 2024-05-02 at 11 48 58 AM" src="https://github.com/Manny-D/Cisco-Duo-MFA-for-RDP/assets/99146530/0feb390f-0ebb-4c0e-9a36-00677c355130">

After the installation is completed, log out of the server. 

<br>

## Login to test MFA

Log back in to the server and you will now receive the following Duo pop up.

<img width="481" alt="Screenshot 2024-05-02 at 12 02 48 PM" src="https://github.com/Manny-D/Cisco-Duo-MFA-for-RDP/assets/99146530/30435662-c1c2-49d1-80ae-b5bf9b0c4a28"> <br>

The server now requires Multi-Factor Authentication (MFA) each time a user logs in using Remote Desktop Protocol (RDP).

<br>

## Conclusion

Adding Duo Security's MFA for RDP connections ensures only authorized users access your servers. It seamlessly integrates with Azure, offering easy setup and fortifying your defenses in today's dynamic cybersecurity landscape.
