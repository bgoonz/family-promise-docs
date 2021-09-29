# Facebook Graph API



## Get Started <a id="get-started"></a>

This guide explains how to get started with receiving data from the Facebook Social Graph.

### Before You Start <a id="before-you-start"></a>

You will need:

* [Register as a Facebook Developer](https://developers.facebook.com/docs/development/register)
* A [Facebook App](https://developers.facebook.com/docs/development/create-an-app) – This app will be for testing so there is no need to involve your app code when creating this Facebook App.
* The [Graph Explorer tool](https://developers.facebook.com/tools/explorer) open in a separate browser window
* A brief understanding of the structure of the Facebook Social Graph from our [Graph API Overview](https://developers.facebook.com/docs/graph-api/overview#nodes) guide

### Your First Request <a id="your-first-request"></a>

#### Step 1: Open the Graph Explorer tool <a id="step-1--open-the-graph-explorer-tool"></a>

[Open the Graph Explorer in a new browser window.](https://developers.facebook.com/tools/explorer) This allows you to execute the examples as you read this tutorial.

The explorer loads with a default query with the `GET` method, the lastest version of the Graph API, the `/me` node and the `id` and `name` fields in the [Query String Field](https://developers.facebook.com/docs/graph-api/guides/explorer#query-string-field), and your Facebook App.![](https://scontent.fewr1-6.fna.fbcdn.net/v/t39.2365-6/232068365_563091814813799_6070357364579520404_n.png?_nc_cat=100&ccb=1-5&_nc_sid=ad8a9d&_nc_ohc=d0STK0yJGfYAX8i57dX&_nc_ht=scontent.fewr1-6.fna&oh=586bd0e1ae4eccb1b415fd330f75f206&oe=6158E5E4)

#### Step 2. Generate an Access Token <a id="step-2--generate-an-access-token"></a>

Click the **Generate Access Token** button. A **Log in With Facebook** window will pop up. This popup is your app asking for your permission to get your name and profile picture from Facebook.

<table>
  <thead>
    <tr>
      <th style="text-align:left">
        <p>This flow is our <a href="https://developers.facebook.com/docs/facebook-login">Facebook Login</a> product
          that allows a person to log into an app using their Facebook credentials.
          Facebook Login allows an app to ask a person to access the person&apos;s
          Facebook data, and for the person to accept or decline access. Your name
          and profile picture are public, to allow people to find you on Facebook,
          so no additional requirements are needed to run this request.</p>
        <p>Click <b>Continue as...</b>
        </p>
        <p>A User Access Token is created. This token contains information such as
          the app making the request, the person using the app to make a request,
          if the access token is still valid (it expires in about an hour), the expiration
          time, and the scope of data the app can request. In this request the scope
          is <code>public_profile</code> which includes your name and profile picture.</p>
      </th>
      <th style="text-align:left">
        <img src="https://scontent.fewr1-5.fna.fbcdn.net/v/t39.2365-6/231956490_308313234407833_1605768375436620205_n.png?_nc_cat=106&amp;ccb=1-5&amp;_nc_sid=ad8a9d&amp;_nc_ohc=X3u6jwe8hPUAX9W6ho8&amp;_nc_ht=scontent.fewr1-5.fna&amp;oh=d9f48005ce94c1fc73fd86adcaec4a56&amp;oe=6159E3EE"
        alt/>
      </th>
    </tr>
  </thead>
  <tbody></tbody>
</table>

| ![](https://scontent.fewr1-6.fna.fbcdn.net/v/t39.2365-6/232991718_592378688435455_3147910228443606263_n.png?_nc_cat=109&ccb=1-5&_nc_sid=ad8a9d&_nc_ohc=_YUz-uoLQvgAX8g8sdO&_nc_ht=scontent.fewr1-6.fna&oh=7d15ae4dcd3c2ed2ba0c3b8873f25cfb&oe=6159E874) | Click the information circle icon next to the acces token to view the token's information. |
| :--- | :--- |


#### Step 3. Submit the Request <a id="step-3--submit-the-request"></a>

Click the **Submit** button in the upper right corner.

**What You Should See**

In the [Response Window](https://developers.facebook.com/docs/graph-api/guides/explorer#response-window), you will see a JSON response with your Facebook User ID and your name.![](https://scontent.fewr1-5.fna.fbcdn.net/v/t39.2365-6/232902382_904467853476103_7217229934737479641_n.png?_nc_cat=105&ccb=1-5&_nc_sid=ad8a9d&_nc_ohc=-1ae6DvRnCEAX_ovoGt&_nc_oc=AQmMV5NwmiB2f8MKxmZh8aCPJNU-rgYkhJ55RJn0Pz9Uvy8B5BvrqLurxVR-2aBty30&_nc_ht=scontent.fewr1-5.fna&oh=60757657aac62ebcfd1915996c0c811d&oe=615A8463)

If you remove `?fields=id,name` from the query string field and click **Submit**, you will see the same result since `name` and `id` are the User node fields returned by default.

### Your Second Request <a id="your-second-request"></a>

#### Step 1. Let's Add a Field <a id="step-1--let-s-add-a-field"></a>

Let's make the First Request a little more complex by adding another field, `email`. There are two ways to add fields:

* Click the search dropdown menu in the [Node Field Viewer](https://developers.facebook.com/docs/graph-api/guides/explorer#node-field-viewer) to the left of the response window
* Start typing in the query string field.

Let's add the `email` field and click **Submit**.

**What You Should See**

While the call did not fail, only the `name` and `id` fields were returned along with a debug message. Click the \(Show\) link to debug the request.![](https://scontent.fewr1-5.fna.fbcdn.net/v/t39.2365-6/233410295_959323958245691_7180707304587023135_n.png?_nc_cat=104&ccb=1-5&_nc_sid=ad8a9d&_nc_ohc=4bWCd9-F5xUAX-8vD42&_nc_ht=scontent.fewr1-5.fna&oh=77b1a58bb9d60e89f4e04764462c1d5b&oe=6158F896)

Almost all nodes and fields need a specific permission to access them. The debug message is telling you that you need to give your app permission to access the email address that you have associated with your Facebook account.

#### Step 2. Add a Permission <a id="step-2--add-a-permission"></a>

<table>
  <thead>
    <tr>
      <th style="text-align:left">
        <p>In the right side panel, under <b>Permissions</b>, click the <b>Add a Permission</b> dropdown
          menu. Click <b>User Data Permissions</b> and select <b>email</b>.</p>
        <p><b>Generate A New User Access Token</b>
        </p>
        <p>Because you are changing the scope of the access token, you need to create
          a new one. Click <b>Generate Access Token</b>. Just like your first request,
          you must give your app permission to access your email in the Facebook
          Login dialog.</p>
        <p>Once the new token has been created, click <b>Submit</b>. Now all fields
          in your request will be returned.</p>
      </th>
      <th style="text-align:left">
        <img src="https://scontent.fewr1-5.fna.fbcdn.net/v/t39.2365-6/234580746_367949518031866_340317674627083357_n.png?_nc_cat=104&amp;ccb=1-5&amp;_nc_sid=ad8a9d&amp;_nc_ohc=vG3QPCchQ-QAX9JKqt8&amp;_nc_ht=scontent.fewr1-5.fna&amp;oh=7e819702886f027f048b59048ac294c6&amp;oe=6159515E"
        alt/>
      </th>
    </tr>
  </thead>
  <tbody></tbody>
</table>

Try getting your Facebook posts. 

[See the steps.](https://developers.facebook.com/docs/graph-api/get-started#)

**Links in the Response**

Notice that `id` values returned in the response window are links. These links can represent nodes, such as User, Page, or Post. If you click on a link, the ID will replace the contents of the query string field. Now you can run requests on that node. Because this node is connected to the parent node, a Post of a User, you may not need to add permissions. You can click on a Post ID now since we will be using it in the next example.

Notice: Some IDs are a combination of the parent ID and a new ID string. For example, a User's Post will have a Post ID that looks something like this: `1028223264288_102224043055529` where `1028223264288` is the User ID.

### Let's Look at an Edge <a id="let-s-look-at-an-edge"></a>

The User node does not have many edges that can return data. Access to User objects can only be given by the User who owns the object. In most cases, a User owns an object if they created it.

For example, if you publish a post you can see information about the post such as when it was created, text, photos, and links shared in the post, and the number of reactions the post received. If you comment on your post, you will be able to get that comment, but if another person publishes a comment on your post, you will not be able to see the comment or who published it.

Try getting the number of reactions for one of your posts. You will want to take a look at the [Post Reactions Edge reference.](https://developers.facebook.com/docs/graph-api/reference/post/reactions/#fields)

[See the steps.](https://developers.facebook.com/docs/graph-api/get-started#)

### Get the Code for your Request <a id="get-the-code-for-your-request"></a>

The explorer tool lets you test requests and once you have a successful response, you can get the code to insert into your app code. At the bottom of the response window, click **Get Code**. The explorer offers Android, iOS, JavaScript, PHP, and cURL code. The code is pre-selected so you can just copy and paste.![](https://scontent.fewr1-6.fna.fbcdn.net/v/t39.2365-6/231948896_1065545040645743_5920314088559660186_n.png?_nc_cat=101&ccb=1-5&_nc_sid=ad8a9d&_nc_ohc=miu9Np9RB-8AX-NN3dQ&_nc_ht=scontent.fewr1-6.fna&oh=f44387f1c0f4bc21a2e0d0d295aeb0d9&oe=61598F2C)

We recommend that you implement the Facebook SDK for your app. This SDK will include Facebook Login which allows your app to ask for permissions and get access tokens.

### Learn More <a id="learn-more"></a>

You can use the Graph Explorer to test any request for Users, Pages, Groups, and more. Visit the [reference](https://developers.facebook.com/docs/graph-api/reference) for each node or edge to determine the permission and access token type required.

<table>
  <thead>
    <tr>
      <th style="text-align:left">
        <ul>
          <li><a href="https://developers.facebook.com/docs/facebook-login/access-tokens">Access Token</a>
          </li>
          <li><a href="https://developers.facebook.com/docs/facebook-login">Facebook Login</a>
          </li>
          <li><a href="https://developers.facebook.com/docs#apis-and-sdks">Facebook SDKs</a>
          </li>
        </ul>
      </th>
      <th style="text-align:left">
        <ul>
          <li><a href="https://developers.facebook.com/docs/graph-api/reference">Graph API References</a>
          </li>
          <li><a href="https://developers.facebook.com/docs/graph-api/guides/explorer">Graph Explorer Guide</a>
          </li>
          <li><a href="https://developers.facebook.com/docs/permissions/reference">Permissions Reference</a>
          </li>
        </ul>
      </th>
    </tr>
  </thead>
  <tbody></tbody>
</table>

