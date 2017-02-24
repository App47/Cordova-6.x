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

Next, in Xcode, find the class named `AppDelegate` and the following import:

```
#import <EmbeddedAgent/EmbeddedAgent.h>
```

And add the following lines to the `didFinishLaunchingWithOptions` method:

```
[EmbeddedAgent configureAgent];
[EmbeddedAgent InstallExceptionHandlers];
```

Next, find the `EmbeddedAgentSettings.plist` file and add your app's id, which you can find in your App47 account dashboard. 

That's it for iOS -- please see the below section entitled "[Using the App47 Agent](#using-the-app47-agent)" for how to install the PhoneGap 6.x plugin. 
