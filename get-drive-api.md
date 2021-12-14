# Setup Google Drive API

Log in to your Google Account and go to this website:

https://console.developers.google.com/

## Getting your Client ID and Client Secret

Create a new project using the dropdown at the top.

<img width="463" alt="Create a new project" src="https://cloud.githubusercontent.com/assets/3598622/22397261/060eac9e-e56e-11e6-907c-717932605569.png">

After you enter a name, it takes a few seconds before the project is successfully created on the server.

Make sure you have the project selected at the top.

Then go to Library and click on "Drive API" under "Google Apps APIs".

<img width="1154" alt="Find Google Drive API" src="https://cloud.githubusercontent.com/assets/3598622/22397284/8765af7c-e56e-11e6-812c-608189e3b89c.png">

And then Enable it.

<img width="383" alt="Enable Google Drive API" src="https://cloud.githubusercontent.com/assets/3598622/22397290/a858c6d8-e56e-11e6-9154-0052d7ecd0eb.png">

Then, go to "Credentials" and click on the tab "OAuth Consent Screen". Fill in a "Product name shown to users" and Save it. Don't worry about the other fields.

<img width="896" alt="Consent Screen" src="https://cloud.githubusercontent.com/assets/3598622/22397326/549fb3c0-e56f-11e6-9b0a-8771b0ba72b4.png">

Then go back to Credentials, click the button that says "Create Credentials" and select "OAuth Client ID".

<img width="435" alt="Create Credentials" src="https://cloud.githubusercontent.com/assets/3598622/22397368/33f8bd0a-e570-11e6-859c-34d112c772e4.png">

Choose "Web Application" and give it a name.

Enter your "Authorized redirect URIs", preferably your test URL (http://mysite.dev) and your production URL (https://mysite.com) - or create a separate production key later. Also add https://developers.google.com/oauthplayground temporarily, because you will need to use that in the next step.

<img width="907" alt="Credentials" src="https://cloud.githubusercontent.com/assets/3598622/22397894/2924ed48-e57c-11e6-98a4-48910d99b6d2.png">

Click Create and take note of your **Client ID** and **Client Secret**.

## Getting your Refresh Token

Now head to https://developers.google.com/oauthplayground.

> Make sure you added this URL to your Authorized redirect URIs in the previous step.

In the top right corner, click the settings icon, check "Use your own OAuth credentials" and paste your Client ID and Client Secret.

<img width="463" alt="Use your own OAuth credentials" src="https://cloud.githubusercontent.com/assets/3598622/22397216/24fe7d88-e56d-11e6-82cf-2d75365d8800.png">

In step 1 on the left, scroll to "Drive API v3", expand it and check each of the scopes.

<img width="493" alt="Check Scopes" src="https://cloud.githubusercontent.com/assets/3598622/22397206/dbcd6106-e56c-11e6-8340-bca54ee8f2b6.png">

Click "Authorize APIs" and allow access to your account when prompted.

When you get to step 2, check "Auto-refresh the token before it expires" and click "Exchange authorization code for tokens".

<img width="493" alt="Exchange authorization code for tokens" src="https://cloud.githubusercontent.com/assets/3598622/22397183/8472095c-e56c-11e6-85be-83adf00837c7.png">

When you get to step 3, click on step 2 again and you should see your **refresh token**.

<img width="487" alt="Refresh Token" src="https://cloud.githubusercontent.com/assets/3598622/22397176/2cef7a98-e56c-11e6-83b9-b4653850dbca.png">

## Getting your Folder ID

If you want to store files in your Google Drive root directory, then the folder ID can be `null`.
Else go into your Drive and create a folder.

Because Google Drive allows for duplicate names, it identifies each file and folder with a unique ID.
If you open your folder, you will see the **Folder ID** in the URL.

<img width="807" alt="Folder ID" src="https://cloud.githubusercontent.com/assets/3598622/22397170/d79422ba-e56b-11e6-8ba6-01c622fdef42.png">
