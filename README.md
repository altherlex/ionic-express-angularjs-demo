Ionic + Express + Angularjs + IBM Bluemix (deploy and datas) Demostration
===

[Demo](https://myhybridapp.mybluemix.net) https://myhybridapp.mybluemix.net

This demo uses the [Ionicframework](https://ionicframework.com) for the mobile web user experience;
[AngularJS](https://angularjs.org/) as the controller framework. 

The app is hosted inside a Cloud Code [Node.js](https://nodejs.org/) server and loads into a mobile browser or desktop browser. The app then uses the Cloud Code JavaScript SDK to invoke REST services managed in the same Cloud Code runtime. These REST endpoints are managed with [express](http://expressjs.com/). These REST endpoints then map to a set of CRUD (Create, Read, Update and Delete) operations that are then using the JavaScript Data Service SDK to store and manage data into the Mobile Cloud data services that is backed by [Cloudant](https://cloudant.com/).

This sample works with the Mobile Cloud boilerplate available on [IBM Bluemix](https://www.ng.bluemix.net).  With this boilerplate, you can quickly incorporate pre-built, managed, and scalable cloud services into your mobile applications without relying on IT involvement. You can focus on building your mobile applications rather than the complexities of managing the back end infrastructure.

Deploy to Bluemix
---

1. Download and install the Cloud Foundry CLI from https://github.com/cloudfoundry/cli/releases/tag/v6.0.0
2. From the sample app directory, run ```cf push ${yourAppName}``` to deploy the app to Bluemix. (Note: Be sure to run ```npm install --production``` and ```bower install``` prior to your ```cf push```)
3. The sample app can now be tested using your Bluemix URL
    

Downloading this sample
---

You can clone the samples with the following command:

    git clone https://github.com/altherlex/ionic-express-angularjs-demo
	

Running this sample IBM Bluemix and local
---

- The sample is designed so that it can be easily run locally and then be pushed up to to Bluemix and tested in the cloud. Use the following steps to setup the sample. To test the app you need to have created a Mobile Cloud application on [IBM Bluemix](http://bluemix.net) and you need to make a note of your App ID, App Secret and Route.

- Local
First, install [Node.js](https://nodejs.org/). Then, install the latest Cordova and Ionic [command-line tools](https://www.npmjs.com/package/ionic).

```
npm install -g cordova ionic
cd ionic-express-angularjs-demo
npm install
node app.js // localhost:3000
```

### Configuration

To run the app locally you need to first modify the ```public/bluelist.json``` file with your corresponding application id, application secret, and application route. The application route is the full application URL that you customized when creating your application on Bluemix.

```json
{
	"applicationId": "<INSERT_APPLICATION_ID_HERE>",
	"applicationSecret": "<INSERT_APPLICATION_SECRET_HERE>",
    "applicationRoute": "<INSERT_APPLICATION_ROUTE_HERE>"
}

```

### Dependencies
Modern mobile web applications are now built using dependency managers. The mobile web application sample uses two. It uses ```bower``` for the client side components and ```npm``` for the server side node.js components. This includes the pulling in of the latest levels of the [Mobile Cloud SDKs](https://hub.jazz.net/user/mobilec) .

1. Download and install the node.js runtime from http://nodejs.org/
2. From the sample app directory install the dependant node modules.
```bash
npm install --production
```
3. From the same directory install the ```bower``` dependency manager.
```bash
npm install -g bower
```
4. Once bower has been installed now install the client side dependencies using the following command.
```bash
bower install
```
5. From the app directory, run
```bash
node app
```
6. The sample app can then be accessed using this local URL: http://localhost:3000/
7. You should see the mobile web user interface now displayed in your browser.



