# JSON.OBJC
修改自https://github.com/haydump/objcJSON oc
#实例代码
```
 - (NSDictionary *)sampleDictionary {
    return @{
             @"title": @"Winter is coming",
             @"createdAt": @140000000,
             @"modifiedAt": @"140000000",
             @"data": @{
                     @"content": @"foo bar",
                     @"timelineID": @233,
                     @"author": @{
                             @"userID": @666,
                             @"userName": @"Jon Snow",
                             @"followerIDs": @[@1, @2, @3],
                             @"address": @{
                                     @"country": @"The North",
                                     @"castle": @"Winter Fell",
                                     },
                             @"address2": [NSNull null],
                             }
                     },
             @"likedUserIDs": @[@1, @2, @3],
             @"favoriteRate": @42.3762,
             @"recommended": @YES,
             @"hidden": @NO,
             @"sticky": @"1",
             @"hasAttachments": @"0"
             };
}
```
#使用
```
 RTCJSON *json = [[RTCJSON alloc]initWithObject:[self sampleDictionary]];
  RTCJSON *re = json[@"likedUserIDs"];
re[1] = @(100);
json[@"likedUserIDs"] = re;

json[@"title"]  = @{@"ddd":@"fffff"};
if (err) {
    NSLog(@"err:%@",err.localizedDescription);
}
NSLog(@"json:%@",json[@"title"]);
```


