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
    "badge": 1,
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

### Log

```
2023-06-22 15:10:34.313718+0900 push[27843:1322549] Key:aps Value:{
    alert =     {
        body = "\U30a4\U30d9\U30f3\U30c8\U53d7\U4fe1";
        subtitle = simurator;
        title = "My Message";
    };
    badge = 1;
    category = cate1;
    sound = default;
}
2023-06-22 15:10:34.313942+0900 push[27843:1322549] Key:custom Value:{
    key = value;
}
2023-06-22 15:10:34.314099+0900 push[27843:1322549] Key:Simulator Target Bundle Value:tucur.prg.push
```
