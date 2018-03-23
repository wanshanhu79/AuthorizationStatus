# AuthorizationStatus
相机、图片、定位、通讯录、麦克风授权状态检测，用户从未进行过授权等处理则进行权限请求，其他情况可选择是否弹窗提示，还可选择是否跳转设置页面。

## 1.当前权限状态，不进行其他操作
```
/** 定位权限检测 */
+ (ZLLAuthorizationStatus)checkAccessForLocationServices;
/** 通讯录权限检测 */
+ (ZLLAuthorizationStatus)checkAccessForContacts;
/** 图片权限检测 */
+ (ZLLAuthorizationStatus)checkAccessForPhotos;
/** 麦克风权限检测 */
+ (ZLLAuthorizationStatus)checkAccessForMicrophone;
/** 相机权限检测 */
+ (ZLLAuthorizationStatus)checkAccessForCamera:(BOOL)isRear;
```

## 2.判断权限是否可用，根据传进来的参数进行相应操作
```
/*
* 定位权限是否可用
* @param currentVC 用来present一个alert VC
* @param jumpSettering 是否跳转到设置页面开启权限
* @param isAlert 不支持、没有描述、权限受限是否弹出alert
* @param resultBlock 结果回调 isAvailable:当status为ZLLAuthorizationStatus_NotDetermined或ZLLAuthorizationLocaStatus_AlwaysUsage或ZLLAuthorizationLocaStatus_WhenInUseUsage时返回YES
*/
+ (void)availableAccessForLocationServices:(UIViewController * _Nullable)currentVC
jumpSettering:(BOOL)jumpSettering
alertNotAvailable:(BOOL)isAlert
resultBlock:(ZLLAuthorizationBlock)resultBlock;
```
