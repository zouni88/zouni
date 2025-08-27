### 打开第三方站点需要保留登录状态，webview需要接受cookie，按照官方提供的API `CookieManager`可以实现
```java
// 1. 在loadurl之前调用接受cookie方法
android.webkit.CookieManager cookieManager = android.webkit.CookieManager.getInstance();
cookieManager.setAcceptThi~rdPartyCookies(this,true);
// 2. onPageFinished 
CookieManager.getInstance().flush();
```

