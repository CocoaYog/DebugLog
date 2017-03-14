# DebugLog
##描述
通过宏定义，自定义控制台的log格式。将这个段代码放入.pch文件中，即可全局使用。
##主要代码

```
#ifdef DEBUG
# define DebugLog(fmt, ...) NSLog((@"\n[文件名:%s]\n" "[函数名:%s]\n" "[行号:%d] \n" fmt), __FILE__, __FUNCTION__, __LINE__, ##__VA_ARGS__);
#else
# define DebugLog(...);
#endif
```

##效果

```
2017-03-14 10:52:28.094 UGDribbble[3685:769768] 
[文件名:/Users/cocoayog/dribbble/UGDribbble/LoginInfoManager/UGDSignInManager.m]
[函数名:+[UGDSignInManager user]]
[行号:143] 
{
    "avatar_url" = "https://d13yacurqjgara.cloudfront.net/users/1416452/avatars/normal/92f5bd044f9404bbc37495de27fc66bc.jpeg?1488523987";
    bio = "I am a iOS developer";
    "buckets_count" = 8;
}
```





