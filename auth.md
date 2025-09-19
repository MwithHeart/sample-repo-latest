---
title: Authentication
---
TO GET STARTED, CREATE A developer account.


When creating a developer account:
1. Clik the [link](https://dribbble.com/account/applications/new)
2. Create an account on dribble or login
3. Select Applications from the side menu

4. In the Developers section, select Register a New Application
5. Fill the form on the page with your app details and add the callback URL yourself.

    
    The callback URL is the URL to which Dribbble will redirect users after they authorize your app.
    For example
    Website URL: https://myportfolio.com

    Callback URL: https://myportfolio.com/auth/dribbble/callback

    For me, I used

    Callback URL: https://substack.com/@mwithheart/auth/dribbble/callback

6. click Create Your Appliaction

At the bottom of the page, you get your: Client ID and Client Secret. 

These are valuable details that uou should keep safe for later.   

**Recommendation:** The Client ID & Client Secret should be created as a field with a copy button.



### Base URL
api.dribbble.com/v2/


## Get an access token
**Step 1: Authorize**
1. Log into your Dribbble account
2. In a new window, go to the following url: https://dribbble.com/oauth/authorize?client_id=CLIENT_ID (Replace CLIENT_ID with the Client ID number provided when you registered your application)
3. An Authorization Screen will appear with the name of the application you registered
4. Choose **Authorize**  

**Step 2: After Authorizing**
1. After authorizing, you will be redirected to a URL that looks similar to this:
http://callback_url?code=9892aebffbb8c82d93e3f2c63a1dab160cefcb1ae269df3a4315924b87246a67

**Note:** The http://callback_url will be the callback URL you entered when registering your application. 

2. Copy the code at the end of this URL. It should come after the *?code=* 
In the example above the code is: 9892aebffbb8c82d93e3f2c63a1dab160cefcb1ae269df3a4315924b87246a67
Save it as you will need it later.


My own is C47cV7A_uf6-yyXYCFEPerTp3IfmSO-3A-MkjGaNCwg


**Step 3: Get the token using postman**
The access token allows you to make requests to the API on a behalf of a user.
1. On Postman, create a new request.
2. Change the HTTP Method to **POST**. 
3. Paste the URL *https://dribbble.com/oauth/token*
4. In the Parameters table: add 3 keys named:  
    - client_id,
    - client_secret
    - Code  
    And their values in the values columns respectively. The code is the code you copied in step 2

---
