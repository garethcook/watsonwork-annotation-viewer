# watsonwork-annotation-viewer
## Getting Started
Installation Requirements
1. NodeJS https://nodejs.org
2. Bluemix CLI https://clis.ng.bluemix.net/ui/home.html
3. ngrok https://ngrok.com/

## Fork and Clone the source

1. [Fork it](https://github.com/watsonwork/watsonwork-annotation-viewer/fork)
2. Clone the project `git clone https://github.com/YOUR_GITHUB_USERNAME/watsonwork-annotation-viewer.git`

## Start ngrok proxy

1. Goto ngrok download dir
2. Run the command :
  ./ngrok http 3000
3. Copy the https path specified on screen for use later. e.g. https://452da8f0.ngrok.io/webhook


## Create your Watson Workspace app
Navigate to https://developer.watsonwork.ibm.com/apps

**App ID and Secret**
1. Click 'Create new app'
2. Give your application a name, such as Workspace App
3. Copy the App ID and the App secret. **Copy these and keep them safe!**
You have now created your Watson Workspace app and the associated metadata


**Webhook**
1. Goto your app and click 'listen for events'.
2. Click 'add an outbound webhook'
3. Give it a webhook name i.e. Webhook
4. Specify the Webhook URL from ngrok above
  i.e. https://452da8f0.ngrok.io/webhook
5. Select the following options
  Allow self signed certificate
  message-created
  space-members-added
  message-annotation-added 
6. Click Save
7. On the following page, copy the webhook secret. This will be used in the webhook.js file below.

**Modify the routes\webhook.js with your app information**
1. Locate the extracted reference application and the routes\webhook.js files
2. Look for the code starting with 'const APP_ID ..' 
3. Copy your App ID to the const APP_ID = "" line inside the quotes
4. Copy your App secret to the const APP_SECRET = "" inside the quotes
5. Copy your webhook secret key to const WEBHOOK_SECRET = "" inside the quotes

## Running your app

**Start npm***
1. Open a terminal in your source folder.
2. Run 'npm update'. This will create a node_modules directory in your source folder which is all the node libraries required by the app.
3. Run 'npm start' to start the app which will run on localhost on port 3000.

**Enable your webhook**
1. In your Watson Workspace app, enable your webhook.



**Reference**

- You can view your ngrok web interface url in the ngrok terminal shell. e.g. http://127.0.0.1:4040

