Push Notification (APNs)
=====

通知設定ファイル(.apns)  

```
{
  "Simulator Target Bundle": "tucur.prg.push",
  "aps": {
    "alert": {
      "title": "My Message",
      "subtitle": "simurator",
      "body": "イベント受信",
    },
    "category": "cate1",
    "sound": "default",
    "badge": 1
  },
  "custom": {
    "key": "value",
  },
}
```

作成したファイルをシミュレータにD&Dすれば通知が飛ぶ  

## 実装 (Objective-C)  

Foregroundで通知を受け取る  

AppDelegate.m  
```
- (void)application:(UIApplication *)application didReceiveRemoteNotification:(NSDictionary *)userInfo fetchCompletionHandler:(void (^)(UIBackgroundFetchResult))completionHandler {

    for (id key in [userInfo keyEnumerator]) {
        NSLog(@"Key:%@ Value:%@", key, [userInfo valueForKey:key]);
    }

    completionHandler(UIBackgroundFetchResultNoData);
}
```
