# Dynatrace-API-Account.Management-Postman-Collection
Postman Collection for Dynatrace Account Management API.

# How to

## 1. Create an Oauth Client in Dynatrace

   - Open the User menu and select Account settings (in latest Dynatrace, Account Management).
   - On the top navigation bar, go to Identity & access management > OAuth clients.
   - Select Create client.
   - Provide an email of the user who owns the client.
   - Provide a description for the new client.
   - Select the required token scopes. These are the scopes that the client will be able to grant. Tokens generated by the client might have different scope sets.
     - Allow read access for identity resources (users and groups) **account-idm-read**
     - Allow write access for identity resources (users and groups) **account-idm-write**
     - Allow read access for environment resources **account-env-read**
     - Allow write access for environment resources **account-env-write**
     - Allow read access for usage and consumption resources **account-uac-read**
     - Allow write access for usage and consumption resources **account-uac-write**
     - Allow IAM policy configuration for environments. **iam-policies-management**; **iam:policies:read**; **iam:policies:write**; **iam:bindings:read**; **iam:bindings:write**; **iam:effective-permissions:read**.
   - Select Create client.
   - Copy the generated information to the clipboard. Store it in a password manager for future use.
  
     [Follow this Video for Reference](https://youtu.be/zrqtWOKz1CY?t=50)
  
## 2. Create an Environment for your Collection in Postman

![Environment](https://github.com/dstanizzo/Dynatrace-API-Account.Management-Postman-Collection/blob/main/images/Environment.png)

   - Select Environments.
   - Click the + sign.
   - Name your Environment.
   - The environment needs that you define these variables:
     - **DT_CLIENT_ID**         Provided when you create the Oauth2 client in step 1.
     - **DT_CLIENT_SECRET**     Provided when you create the Oauth2 client in step 1.
     - **DT_ACCOUNT_URN**       Provided when you create the Oauth2 client in step 1.
     - **DT_UUID**              Same value of DT_ACCOUNT_URN but stripping the urn:account:
     - **DT_SCOPE**             A list of required scopes separated by a whitespace.
     - **DT_TOKEN_URL**         :warning: **PLEASE DON'T CHANGE THIS VALUE** :warning: The URL _https://sso.dynatrace.com/sso/oauth2/token_ where you need to obtain your Bearer token after create the Oauth2 client.
     - **DT_TOKEN_NAME**        The name for your token.
     - **DT_TOKEN**             In this variable you will store your assigned dynamic token.
     - **DT_HOST**              :warning: **PLEASE DON'T CHANGE THIS VALUE** :warning: The URL _api.dynatrace.com_ of the Dynatrace API for Account Management.
   - Leave this Environment Selected. 
    
## 3. Import Dynatrace Account Management API Collection

   ![Import Collection](https://github.com/dstanizzo/Dynatrace-API-Account.Management-Postman-Collection/blob/main/images/Import.png)

   - Download the JSON from the repository.
   - Select Collections.
   - Click on Import and choose the previously downloaded JSON.
   - Your Dynatrace Account Management API v1 Collection has been added to your collection.

## 4. Get your Bearer Token

   ![Get Ready](https://github.com/dstanizzo/Dynatrace-API-Account.Management-Postman-Collection/blob/main/images/Get.Your.Bearer.Token.png)

   - :warning: **DON'T FORGET TO HAVE SELECTED THE ENVIRONMENT CREATED IN STEP 2** :warning:
   - Select your recently imported Dynatrace Account Management API v1 Collection.
   - Click on the Authorization tab.
   - Click on Get New Access Token.
   - Wait until the token has been collected.
   - Click on Use Token.
   - :warning: **BE SURE TO SELECT ALL YOUR TOKEN** :warning: And then select Set as variable.
   - Choose the **DT_TOKEN** variable to store your new Bearer Token.

## 5. Ready

   ![Get Ready](https://github.com/dstanizzo/Dynatrace-API-Account.Management-Postman-Collection/blob/main/images/Using.Collection.png)

   - :warning: **DON'T FORGET TO HAVE SELECTED THE ENVIRONMENT CREATED IN STEP 2** :warning:
   - Select Collections.
   - Then Select the Request you want to use and check the parameters.
   - Click on Send.
   - And if everything goes well you get your Response.
