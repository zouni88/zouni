### flutter webview 访问url

```dart
 Future<void> launcherURL() async {
    // Uri uri = Uri(scheme: 'http',host: 'www.baidu.com');
    Uri url = Uri.parse('https://www.baidu.com');
    if (!await launchUrl(
      url,
      mode: LaunchMode.inAppWebView,
      webViewConfiguration: const WebViewConfiguration(enableJavaScript: true),
    )) {
      throw 'Could not launch $url';
    }
  }
```