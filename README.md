# API_source

Obtaining API Keys
------------------

To use any of the included APIs or OAuth authentication methods, you will need
to obtain appropriate credentials: Client ID, Client Secret, API Key, or
Username & Password. You will need to go through each provider to generate new
credentials.

<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/2/2f/Google_2015_logo.svg/1000px-Google_2015_logo.svg.png" width="200">

- Visit <a href="https://cloud.google.com/console/project" target="_blank">Google Cloud Console</a>
- Click on the **Create Project** button
- Enter *Project Name*, then click on **Create** button
- Then click on *APIs & auth* in the sidebar and select *API* tab
- Click on **Google+ API** under *Social APIs*, then click **Enable API**
- Click on **Google Drive API** under *G Suite*, then click **Enable API**
- Click on **Google Sheets API** under *G Suite*, then click **Enable API**
- Next, under *APIs & auth* in the sidebar click on *Credentials* tab
- Click on **Create new Client ID** button
- Select *Web Application* and click on **Configure Consent Screen**
- Fill out the required fields then click on **Save**
- In the *Create Client ID* modal dialog:
 - **Application Type**: Web Application
 - **Authorized Javascript origins**: http://localhost:8080
 - **Authorized redirect URI**: http://localhost:8080/auth/google/callback
- Click on **Create Client ID** button
- Copy and paste *Client ID* and *Client secret* keys into `.env`

**Note:** When you ready to deploy to production don't forget to
add your new URL to *Authorized Javascript origins* and *Authorized redirect URI*,
e.g. `http://my-awesome-app.herokuapp.com` and
`http://my-awesome-app.herokuapp.com/auth/google/callback` respectively.
The same goes for other providers.

<hr>

<img src="https://seeklogo.com/images/S/snapchat-logo-F20CDB1199-seeklogo.com.png" height="90">

- Visit <a href="https://kit.snapchat.com/portal" target="_blank">Snap Kit Developer Portal</a>
- Click on the **+** button to create an app
- Enter a name for your app
- Enable the scopes that you will want to use in your app
- Click on the **Continue** button
- Find the **Kits** section and make sure that **Login Kit** is enabled
- Find the **Redirect URLs** section, click the **+ Add** button, and enter `http://localhost:8080/auth/snapchat/callback`
- Find the **Development Environment** section. Click the **Generate** button next to the *Confidential OAuth2 Client* heading within it.
- Copy and paste the generated *Private Key* and *OAuth2 Client ID* keys into `.env`
- **Note:** *OAuth2 Client ID* is **SNAPCHAT_ID**, *Private Key* is **SNAPCHAT_SECRET** in `.env`
- To prepare the app for submission, fill out the rest of the required fields: *Category*, *Description*, *Privacy Policy Url*, and *App Icon*

**Note:** For production use, don't forget to:

- generate a *Confidential OAuth2 Client* in the **Production Environment** and use the production *Private Key* and *OAuth2 Client ID*
- add the production URL to **Redirect URLs** section, e.g. `http://my-awesome-app.herokuapp.com/auth/snapchat/callback`
- submit the app for review and wait for approval

<hr>

<img src="https://en.facebookbrand.com/wp-content/uploads/2019/04/f_logo_RGB-Hex-Blue_512.png" width="90">

- Visit <a href="https://developers.facebook.com/" target="_blank">Facebook Developers</a>
- Click **My Apps**, then select **Add a New App* from the dropdown menu
- Enter a new name for your app
- Click on the **Create App ID** button
- Find the Facebook Login Product and click on **Facebook Login**
- Instead of going through their Quickstart, click on **Settings** for your app in the top left corner
- Copy and paste *App ID* and *App Secret* keys into `.env`
- **Note:** *App ID* is **FACEBOOK_ID**, *App Secret* is **FACEBOOK_SECRET** in `.env`
- Enter `localhost` under *App Domains*
- Choose a **Category** that best describes your app
- Click on **+ Add Platform** and select **Website**
- Enter `http://localhost:8080` under *Site URL*
- Click on the *Settings* tab in the left nav under Facebook Login
- Enter `http://localhost:8080/auth/facebook/callback` under Valid OAuth redirect URIs

**Note:** After a successful sign in with Facebook, a user will be redirected back to the home page with appended hash `#_=_` in the URL. It is *not* a bug. See this [Stack Overflow](https://stackoverflow.com/questions/7131909/facebook-callback-appends-to-return-url) discussion for ways to handle it.

<hr>

<img src="https://github.githubassets.com/images/modules/logos_page/Octocat.png" width="110">

- Go to <a href="https://github.com/settings/profile" target="_blank">Account Settings</a>
- Select **Developer settings** from the sidebar
- Then click on **OAuth Apps** and then on **Register new application**
- Enter *Application Name* and *Homepage URL*
- For *Authorization Callback URL*: http://localhost:8080/auth/github/callback
- Click **Register application**
- Now copy and paste *Client ID* and *Client Secret* keys into `.env` file

<hr>

<img src="https://seeklogo.com/images/T/twitter-2012-positive-logo-916EDF1309-seeklogo.com.png" width="90">

- Sign in at <a href="https://apps.twitter.com/" target="_blank">https://apps.twitter.com</a>
- Click **Create a new application**
- Enter your application name, website and description
- For **Callback URL**: http://127.0.0.1:8080/auth/twitter/callback
- Go to **Settings** tab
- Under *Application Type* select **Read and Write** access
- Check the box **Allow this application to be used to Sign in with Twitter**
- Click **Update this Twitter's applications settings**
- Copy and paste *Consumer Key* and *Consumer Secret* keys into `.env` file

<hr>

<img src="https://content.linkedin.com/content/dam/me/business/en-us/amp/brand-site/v2/bg/LI-Logo.svg.original.svg" width="200">

- Sign in at <a href="https://developer.linkedin.com/" target="_blank">LinkedIn Developer Network</a>
- From the account name dropdown menu select **API Keys**
 - *It may ask you to sign in once again*
- Click **+ Add New Application** button
- Fill out all the *required* fields
 - **OAuth 2.0 Redirect URLs**: http://localhost:8080/auth/linkedin/callback
 - **JavaScript API Domains**: http://localhost:8080
- For **Default Application Permissions** make sure at least the following is checked:
 - `r_basicprofile`
- Finish by clicking **Add Application** button
- Copy and paste *API Key* and *Secret Key* keys into `.env` file
 - *API Key* is your **clientID**
 - *Secret Key* is your **clientSecret**

<hr>

<img src="https://stripe.com/img/about/logos/logos/black@2x.png" width="180">

- <a href="https://stripe.com/" target="_blank">Sign up</a> or log into your <a href="https://manage.stripe.com" target="_blank">dashboard</a>
- Click on your profile and click on Account Settings
- Then click on **API Keys**
- Copy the **Secret Key**. and add this into `.env` file

<hr>

<img src="https://www.paypalobjects.com/webstatic/mktg/logo/pp_cc_mark_111x69.jpg" width="150">

- Visit <a href="https://developer.paypal.com" target="_blank">PayPal Developer</a>
- Log in to your PayPal account
- Click **Applications > Create App** in the navigation bar
- Enter *Application Name*, then click **Create app**
- Copy and paste *Client ID* and *Secret* keys into `.env` file
- *App ID* is **client_id**, *App Secret* is **client_secret**
- Change **host** to api.paypal.com if you want to test against production and use the live credentials

<hr>

<img src="http://33.media.tumblr.com/ffaf0075be879b3ab0b87f0b8bcc6814/tumblr_inline_n965bkOymr1qzxhga.png" width="200">

- Go to <a href="https://developer.foursquare.com" target="_blank">Foursquare for Developers</a>
- Click on **My Apps** in the top menu
- Click the **Create A New App** button
- Enter *App Name*, *Welcome page url*,
- For **Redirect URI**: http://localhost:8080/auth/foursquare/callback
- Click **Save Changes**
- Copy and paste *Client ID* and *Client Secret* keys into `.env` file

<hr>

<img src="http://img4.wikia.nocookie.net/__cb20130520163346/logopedia/images/8/8d/Tumblr_logo_by_x_1337_x-d5ikwpp.png" width="200">

- Go to <a href="http://www.tumblr.com/oauth/apps" target="_blank">http://www.tumblr.com/oauth/apps</a>
- Once signed in, click **+Register application**
- Fill in all the details
- For **Default Callback URL**: `http://localhost:8080/auth/tumblr/callback`
- Click **✔Register**
- Copy and paste *OAuth consumer key* and *OAuth consumer secret* keys into `.env` file

<hr>

<img src="https://upload.wikimedia.org/wikipedia/commons/a/ae/Steam_logo.svg" width="200">

- Go to <a href="http://steamcommunity.com/dev/apikey" target="_blank">http://steamcommunity.com/dev/apikey</a>
- Sign in with your existing Steam account
- Enter your *Domain Name*, then and click **Register**
- Copy and paste *Key* into `.env` file

<hr>
<img src="https://www.freepnglogos.com/uploads/twitch-logo-image-hd-31.png" height="90">

- Visit the <a href="https://dev.twitch.tv/dashboard/apps" target="_blank">Twitch developer dashboard</a>
- If prompted, authorize the dashboard to access your twitch account
- In the Console, click on Register Your Application
- Enter the name of your application
- Use OAuth Redirect URLs enter `http://localhost:8080/auth/twitch/callback`
- Set Category to Website Integration and press the Create button
- After the applicaiton has been created, click on the Manage button
- Copy and paste *Client ID* into `.env`
- If there is no Client Secret displayed, click on New Secret button and then copy and paste the *Client secret* into `.env`

<hr>

<img src="https://sendgrid.com/brand/sg-logo-300.png" width="200">

- Go to <a href="https://sendgrid.com/user/signup" target="_blank">https://sendgrid.com/user/signup</a>
- Sign up and **confirm** your account via the *activation email*
- Then enter your SendGrid *Username* and *Password* into `.env` file

<hr>

<img src="https://raw.github.com/mailgun/media/master/Mailgun_Primary.png" width="200">

- Go to <a href="http://www.mailgun.com" target="_blank">http://www.mailgun.com</a>
- Sign up and add your *Domain Name*
- From the domain overview, copy and paste the default SMTP *Login* and *Password* into `.env` file

<hr>

<img src="https://upload.wikimedia.org/wikipedia/commons/c/c7/HERE_logo.svg" width="90">

- Go to <a href="https://developer.here.com" target="_blank">https://developer.here.com</a>
- Sign up and create a Freemium project
- Create JAVASCRIPT/REST credentials. Copy and paste the APP_ID and APP into `.env` file.
- Note that these credentials are available on the client side, and you need to create a domain whitelist for your app credentials when you are publicly launching the app.

<hr>

<img src="https://s3.amazonaws.com/ahoy-assets.twilio.com/global/images/wordmark.svg" width="200">

- Go to <a href="https://www.twilio.com/try-twilio" target="_blank">https://www.twilio.com/try-twilio</a>
- Sign up for an account.
- Once logged into the dashboard, expand the link 'show api credentials'
- Copy your Account Sid and Auth Token

<hr>

<img src="https://www.intuit.com/content/dam/intuit/intuitcom/company/images/logo-intuit-quickbooks-preferred.png" width="200">

- Go to <a href="https://developer.intuit.com/app/developer/qbo/docs/get-started" target="_blank">https://developer.intuit.com/app/developer/qbo/docs/get-started</a>
- Use the Sign Up option in the upper right corner of the screen (nav bar) to get a free developer account and a sandbox company.
- Create a new app by going to your Dashboard using the My Apps option in the top nav bar or by going to <a href="https://developer.intuit.com/app/developer/myapps" target="_blank">https://developer.intuit.com/app/developer/myapps</a>
- In your App, under Development, Keys & OAuth (right nav), find the Client ID and Client Secret for your `.env` file
