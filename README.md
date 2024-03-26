
# Report

1. renamed application name to "Liquipedia!" in strings.xml
2. enabled internet access by adding a new xml tag in AndroidManifest.xml
3. created a new webview by replacing TextView tag
    - added id "my_webview"
4. created member var in MainActivity for the webview
    - set it to the webview using the built-in find method
    - enabled js
5. Created a member var for the webview client.
    - set the webview to include the client
6. set initial page
7. added the internal and external urls 
8. call the methods inside the dropdown menu

## Code 

### strings.xml
``` xml
<resources>
    <string name="app_name">Liquipedia!</string>
    <string name="action_external_web">AOE2</string>
    <string name="action_internal_web">DOTA2</string>
</resources>

```


### MainActivity

#### fields
``` java
    private WebView myWebView;
    private WebViewClient myWebViewClient;
```


#### methods
``` java
public void showExternalWebPage(){
myWebView.loadUrl("https://liquipedia.net/ageofempires/");
}

public void showInternalWebPage(){
myWebView.loadUrl("https://liquipedia.net/dota2");
}
```

#### onCreate()
``` java
myWebView = findViewById(R.id.my_webView);          // find id
myWebViewClient = new WebViewClient();              // init client
myWebView.setWebViewClient(myWebViewClient);        //  set client on webview
myWebView.getSettings().setJavaScriptEnabled(true); // enable js
myWebView.loadUrl("https://liquipedia.net/");       // initial page
```
#### dropdown menu
``` java
if (id == R.id.action_external_web) {
showExternalWebPage();
Log.d("==>","Will display external web page");
return true;
}

if (id == R.id.action_internal_web) {
showInternalWebPage();
Log.d("==>","Will display internal web page");
return true;
}
```
