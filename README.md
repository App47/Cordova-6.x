# App47 plugin for Cordova (PhoneGap) version 6.x

##iOS Installation

Create your project using the Cordova CLI:

```
cordova create AppName
```

Next add in the iOS platform:

```
cd AppName
cordova platform add ios
```

Finally add in the App47 plugin

```
cordova plugin add <path to App47 Plugin>
```

Open the project in Xcode and on the Project/General tab add the EmbeddedAgent.framework to the Embedded Binaries since this is a custom framework that will need to be bundled with the app.   This is currently an issue with Cordova that the embed="true" on a framework does not embed the framework. 
Next, in Xcode, find the class named `AppDelegate` and the following import:

```
#import <EmbeddedAgent/EmbeddedAgent.h>
```

And add the following lines to the `didFinishLaunchingWithOptions` method:

```
[EmbeddedAgent configureAgent];
[EmbeddedAgent InstallExceptionHandlers];
```


Next, find the `EmbeddedAgentSettings.plist` file in the Resources folder and add your app's id, which you can find in your App47 account dashboard. 

That's it for iOS -- please see the below section entitled "[Using the App47 Agent](#using-the-app47-agent)" for how to use the PhoneGap 6.x plugin. 
