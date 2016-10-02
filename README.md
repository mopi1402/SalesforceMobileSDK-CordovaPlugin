This version is a fork from forcedotcom/SalesforceMobileSDK-CordovaPlugin.

This plugin makes `Cordova` use the `WKWebView` component instead of the default `UIWebView` component, and is installable only on a system with the iOS 9.0 SDK. 

In iOS 9, Apple has fixed the [issue](http://www.openradar.me/18039024) present through iOS 8 where you cannot load locale files using file://, and must resort to using a local webserver. **However, you are still not able to use XHR from the file:// protocol without [CORS](https://developer.mozilla.org/en-US/docs/Web/HTTP/Access_control_CORS) enabled on your server.**


Steps to use the Cordova plugin for the Salesforce Mobile SDK with Ionic (WKWebView)
------------------------

<pre>
npm install -g ionic
ionic start MyIonicApp salesforce
cd MyIonicApp
cordova platform add ios@4.2.0
cordova plugin add https://github.com/mopi1402/SalesforceMobileSDK-CordovaPlugin
cordova plugin rm cordova-plugin-splashscreen
cordova prepare
</pre>

more information [here](https://trailhead.salesforce.com/en/project/mobile-sdk-hybrid-apps/mobilesdk-hybrid-apps-04)

Note :
1 - cordova-plugin-splashscreen should be remove to avoid application hidding under the splash screen.
    SalesforceMobileSDK seems to manage the splashscreen by itself
    
2 - You MUST use ios 9 or more, because of this [issue](http://www.openradar.me/18039024). 

3 - You need to compile templates in a js file because runtime injection is not working... It should work on ios 9, but I don't know why, this triggers a CORS error. So, use gulp to compile templates in one js file, and add this one to modules.
Read this [guide] for more information (http://www.justin-credible.net/2015/12/31/use-wkwebview-in-your-cordova-app-without-a-local-web-server/)


For more information, check out [Salesforce Mobile SDK Development Guide](https://github.com/forcedotcom/SalesforceMobileSDK-Shared/blob/master/doc/mobile_sdk.pdf?raw=true)
