---
description: The Adobe Target Mobile Visual Experience Composer (VEC) lets developers do a one-time setup on their iOS mobile apps and enable marketers to use the capabilities of the Mobile App VEC.
keywords: Mobile App VEC;mobile visual experience composer;mobile experience composer options;setting up;ios;apple
seo-description: The Adobe Target Mobile Visual Experience Composer (VEC) lets developers do a one-time setup on their iOS mobile apps and enable marketers to use the capabilities of the Mobile App VEC.
seo-title: iOS - set up the mobile app
solution: Target
title: iOS - set up the mobile app
topic: Standard
uuid: 6db4f06a-d8f4-4192-af6f-917594e721e6
---

# iOS - set up the mobile app{#ios-set-up-the-mobile-app}

The Adobe Target Mobile App Visual Experience Composer (VEC) lets developers do a one-time setup on their iOS mobile apps and enable marketers to use the capabilities of the Mobile App VEC. 

For more information on enabling the Adobe Target VEC extension, see [Adobe Target - Visual Experience Composer](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-target-vec) in the *Adobe Experience Platform Mobile SDKs*.

## Include the Mobile SDK and the Target library {#sdk-library}

1. Add the library to your project via your Cocoapods [!DNL Podfile] by adding pod '`ACPTargetVEC`'. 

1. Open your Objective-C application project in XCode. 

1. Go to your project build settings and set 'Always Embed swift Standard Libraries' to Yes if already not set.

1. In project build settings find "Other linker flags," Add `$(inherited)` if not already there.

1. For objective-C only project - Create a swift file to create the bridging header. It will set up your application environment for Swift. 

1. Add the deeplink handler:

    1. In your application project settings, click **[!UICONTROL Info]**. 
    1. Under **[!UICONTROL URL Types]**, click the triangle to open it, then click the Plus Sign to add a new field. 
    1. Add the following information:

       * Identifier: `com.adobe.sdktest` 
       * URL Schemes: `vectester`
       * Role: Editor

    1. Click away from your application project settings > **[!UICONTROL General]**. 
    1. Click back on your application project settings > **[!UICONTROL Info]** to ensure your settings were saved.

       With the example URL type, the URL scheme for your app will be:

       ```    
       vectester://com.adobe.sdktest
       ```

1. In XCode, open your [!DNL AppDelegate] file. 

1. At the top of the file, add the following line at the end of your imports:

   `#import "ACPTargetVEC.h"`

   If you are using Swift, add the following line:

   `import ACPTargetVEC` 

1. In your [!DNL AppDelegate] file, add the following line to `AppDelegate::application:didFinishLaunchingWithOptions:`. If the delegate function is not defined, create it and add the following line for Objective-C or Swift application, respectively:

   ```
   // CONFIGURATION LINE FOR OBJECTIVE C ONLY
   - (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions {
     //Other Extensions that you need
     [ACPCore configureWithAppId:@"YOUR_ADOBE_LAUNCH_APP_ID"];
     [ACPCore setLogLevel:ACPMobileLogLevelDebug];
     [ACPTarget registerExtension];
     [ACPTargetVEC registerExtension];
     [ACPCore start:^{
       [ACPCore lifecycleStart:nil];
     }];
     // Override point for customization after application launch.
     return YES;
   }
      
   // CONFIGURATION LINE FOR SWIFT ONLY: 
   func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?) -> Bool {
     //Other Extensions that you need
     ACPCore.configure(withAppId: "YOUR_ADOBE_LAUNCH_APP_ID")
     ACPCore.setLogLevel(ACPMobileLogLevel.debug)
     ACPTarget.registerExtension()
     ACPTargetVEC.registerExtension()
     [ACPCore start:^{
       [ACPCore lifecycleStart:nil];
     }];
     return true
   }
   ```

1. Add the following line to the beginning of `AppDelegate:application:openURL`. If the delegate function is not defined, create it and add the following line.

   ```
   // URL HANDLER LINE FOR OBJECTIVE C ONLY: 
   - (BOOL)application:(UIApplication *)application openURL:(NSURL *)url options:(NSDictionary<NSString *, id> *)options {
     [ACPCore collectLaunchInfo:@ {@"adb_deeplink": url.absoluteString}];
     return YES;
   }

   // URL HANDLER LINE FOR SWIFT ONLY: 
   func application(_ app: UIApplication, open url: URL, options: [UIApplicationOpenURLOptionsKey : Any] = [:]) -> Bool {
     ACPCore.collectLaunchInfo(["adb_deeplink": url.absoluteString])
     return true
   }
   ```

   Build and run your application and use it to test Mobile App VEC capabilities.


## Set Up Target Views on your mobile app {#views}

The Adobe Mobile SDK exposes a new method for developers to trigger whenever a new View is rendered. Please read through the general guidelines on how to properly insert the Target View API calls for an iOS app. In iOS, all the Target Views are defined relative to the `UIViewController` in which they appear. So, unlike Android, the insertion of `TargetViews` are limited to the following calls.

The Adobe Mobile App VEC Extension auto-generates names for your `UIViewControllers` to interact within the Mobile App VEC framework, based upon the class name of the subclassed `UIViewController`. If you want to override these names, you can call the following method in `viewWillAppear` of the `ViewController`.

```
// TARGET VIEW LINE FOR OBJECTIVE C ONLY 
[ACPTargetVEC setTargetView:@"exampleViewController"]; 
   
// TARGET VIEW LINE FOR SWIFT ONLY 
ACPTargetVEC.setTargetView("exampleViewController")
```

The Adobe Mobile SDK also exposes an alternate method for developers to target custom views during runtime. As a developer, you must ensure that the views are named uniquely. Call the following method before adding view to the `superview`:

```
// EXAMPLE TARGET VIEW FOR A CUSTOM VIEW IN OBJECTIVE C 
CustomPopupView *popupView = [[CustomPopupView alloc] initWithFrame:CGRectMake(0, 0, 300, 200)]; 
[ACPTargetVEC setTargetView:@"myCustomPopupView" forView:popupView];

// EXAMPLE TARGET VIEW FOR A CUSTOM VIEW IN SWIFT 
let popupView = CustomPopupView.init(frame: CGRect(x: 0, y: 0, width: 300, height: 200)) 
ACPTargetVEC.setTargetView("myCustomPopupView", for: popupView)
```

## Setting Up profile parameters and other global parameters {#parameters}

We now support setting global parameters that are passed in each and every API call, as well as passing mbox/view parameters to corresponding views.

Parameters include:

* mbox/view parameters 
* profile parameters 
* Product parameters 
* Order parameters

**Global parameter support:**

```
//For Objective-c 
NSDictionary *mboxParams = @{@"mboxparam1":@"mboxvalue1"}; //mbox or view params 
NSDictionary *profileParams = @{@"profilekey1":@"profilevalue1"}; //profile params 
  
ACPTargetProduct *product = [ACPTargetProduct targetProductWithId:@"1234" categoryId:@"furniture"]; 
ACPTargetOrder *order = [ACPTargetOrder targetOrderWithId:@"12343" total:@(123.45) purchasedProductIds:@[@"100",@"200"]]; 
ACPTargetParameters *targetParams = [ACPTargetParameters targetParametersWithParameters: mboxParams
                      profileParameters: profileParams
                      product: product
                      order: order];
[ACPTargetVEC setGlobalRequestParameters:targetParams];

//For Swift 
var mboxParams = ["mboxparam1":"mboxvalue1"] 
var profileParams = ["profilekey1":"profilevalue1"] 
var product = ACPTargetProduct(id: "1234", categoryId: "furniture")
var order = ACPTargetOrder(id: "12345", total: 123.45, purchasedProductIds: ["100", "200"])
var targetParams = ACPTargetParameters(parameters: mboxParams, profileParameters: profileParams, product: product, order: order)
ACPTargetVEC.setGlobalRequest(targetParams)
```

**Passing parameters for next view trigger:**

We have provided some automatic views that are created by default, such as "`AUTO_<viewControllerName>`" for each view controller present in your app. If you want to pass these parameters, you can call the following API:

```
//For Objective-c 
NSDictionary *mboxParams = @{@"viewparam1":@"viewvalue1"}; //mbox or view params 
NSDictionary *profileParams = @{@"profilekeyforview1":@"profilevalueforview1"}; //profile params 
  
ACPTargetProduct *product = [ACPTargetProduct targetProductWithId:@"1234" categoryId:@"furniture"]; 
ACPTargetOrder *order = [ACPTargetOrder targetOrderWithId:@"12343" total:@(123.45) purchasedProductIds:@[@"100",@"200"]]; 
ACPTargetParameters *targetParams = [ACPTargetParameters targetParametersWithParameters:mboxParams 
                                                                      profileParameters:profileParams 
                                                                                product:product 
                                                                                  order:order]; 
[ACPTargetVEC setGlobalRequestParameters:targetParams];

//For Swift 
var mboxParams = ["mboxparam1":"mboxvalue1"] 
var profileParams = ["profilekey1":"profilevalue1"] 
var product = ACPTargetProduct(id: "1234", categoryId: "furniture")
var order = ACPTargetOrder(id: "12345", total: 123.45, purchasedProductIds: ["100", "200"])
var targetParams = ACPTargetParameters(parameters: mboxParams, profileParameters: profileParams, product: product, order: order)
ACPTargetVEC.setRequest(targetParams)
```

**Passing parameters to specific view:**

We have seen the API trigger Views via `TargetVEC.targetView("view_name")`. You can also pass parameters that are specific to the particular view, as shown below:

```
//For Objective-c 
[ACPTargetVEC setTargetView:@"VIEW_NAME" withParameters:TARGET_PARAMS];

//FOR SWIFT 
ACPTargetVEC.setTargetView("VIEW_NAME", with: TARGET_PARAMS)
```

## Calling the Prefetch API explicitly {#section_373DB4527FC649C58FBA3DF0C18C9836}

There might be certain scenarios when you might want to call the prefetch API again to refresh the offers stored in cache. The following APIs are exposed, which are described as:

**Prefetch Offers:**

```
/** 
 * Prefetch all offers for all views in the cache. It will remove existing offers and changes for the current view will be 
 refreshed only when the view is triggered. This call happens on the main thread blocking the UI. 
 */ 
+ (void) prefetchOffers;
```

**Prefetch Offers in background:**

```
/** 
 * Prefetch all offers for all views in the cache. It will remove existing offers and changes for the current view will be 
 refreshed only when the view is triggered. This call happens on the background thread so doesn't block UI. 
 */ 
+ (void) prefetchOffersBackground;
```

## Tutorials: Implement the Experience Cloud in Mobile iOS Objective-C and Swift applications {#tutorial}

* [Implement the Experience Cloud in Mobile iOS Objective-C Applications](https://docs.adobe.com/content/help/en/experience-cloud/implementing-in-mobile-ios-objective-c-apps-with-launch/index.html)
* [Implement the Experience Cloud in Mobile iOS Swift Applications](https://docs.adobe.com/content/help/en/experience-cloud/implementing-in-mobile-ios-swift-apps-with-launch/index.html)

After completing these tutorials you will be able to:

* Create a mobile Launch property
* Install a Launch property in an Objective-C or Swift app
* Implement the following Adobe Experience Cloud solutions:
  * Experience Cloud ID Service
  * Adobe Target
  * Adobe Analytics
  * Adobe Audience Manager

* Publish changes in Launch through development, staging, and production environments