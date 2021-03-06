# Activate-users-in-bulk-using-Powershell-
Activate users in bulk

Activate Workplace users in bulk with a XSLX file in input
This PowerShell script allows to activate Workplace users in bulk.

Setup
Create a new Custom Integration in the Workplace Admin Panel: Create a custom Integration.
This requires at least "Manage Accounts" permissions. Take note of the Access Token.

Create a file named accessToken.js with the following content:

{
      "accessToken" : "YOUR-ACCESS-TOKEN"
}
Export the list of users you'd like to activate: As an admin, you can export deactivated users' details by going to the People Tab in the Admin Portal > Filter in the search bar "Account status" is "deactivated" > Click on the three dots button on the right > Export employee information of {X} people. A mail message with the XLSX file with the requested information will be sent to your email address.

Note: Reactivating a user will reset their manager field.

Run
Run the script by passing the XLSX file and accessToken.js file as input:

./activateInBulk.ps1 -WPExportedUsers workplace_users.xlsx -WPAccessToken accessToken.js -Interactive
Here are the details of the passed params:

Parameter	Description	Type	Required
WPExportedUsers	The path for the XLSX file with the exported user data	String	Yes
WPAccessToken	The path for the JSON file with the access token	String	Yes
Interactive	If the script should display a message for each operation	Switch	No
