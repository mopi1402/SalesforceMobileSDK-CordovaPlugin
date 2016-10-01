This version is a fork from forcedotcom/SalesforceMobileSDK-CordovaPlugin.

This plugin makes `Cordova` use the `WKWebView` component instead of the default `UIWebView` component, and is installable only on a system with the iOS 9.0 SDK. 

In iOS 9, Apple has fixed the [issue](http://www.openradar.me/18039024) present through iOS 8 where you cannot load locale files using file://, and must resort to using a local webserver. **However, you are still not able to use XHR from the file:// protocol without [CORS](https://developer.mozilla.org/en-US/docs/Web/HTTP/Access_control_CORS) enabled on your server.**


Steps to use the Cordova plugin for the Salesforce Mobile SDK (WKWebView)
------------------------

<pre>
npm install cordova -g

cordova create TestApp
cd TestApp
cordova plugin add https://github.com/mopi1402/SalesforceMobileSDK-CordovaPlugin
cordova platform add android@5.0.0
cordova platform add ios@4.2.0
cordova prepare
</pre>

For more information, check out [Salesforce Mobile SDK Development Guide](https://github.com/forcedotcom/SalesforceMobileSDK-Shared/blob/master/doc/mobile_sdk.pdf?raw=true)
