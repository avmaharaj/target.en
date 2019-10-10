---
description: Target's new SDK Library allows developers to do a one-time setup on their Android mobile apps and enable marketers to use the capabilities of the Mobile Visual Experience Composer (VEC).
keywords: mobile vec;mobile visual experience composer;mobile experience composer options;setting up;android
seo-description: Adobe Target's new SDK Library allows developers to do a one-time setup on their Android mobile apps and enable marketers to use the capabilities of the Mobile Visual Experience Composer (VEC).
seo-title: Android - set up the mobile app for Adobe Target
solution: Target
title: Android - set up the mobile app
topic: Standard
uuid: 39938ec2-b12e-44cf-9218-69195fba0ff7
---

# Android - set up the mobile app{#android-set-up-the-mobile-app}

The Adobe Target Mobile App Visual Experience Composer (VEC) lets developers do a one-time setup on their Android mobile apps and enable marketers to use the capabilities of the Mobile App VEC. 

For more information on enabling the Adobe Target VEC extension, see [Adobe Target - Visual Experience Composer](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-target-vec) in the *Adobe Experience Platform Mobile SDKs*.

## Include the Mobile SDK and the Target library {#sdk-library}

1. For information about SDK V5 initialization, see [Initialize the SDK and Set Up Tracking](https://aep-sdks.gitbook.io/docs/getting-started/initialize-the-sdk). 
1. Add the following line to the dependencies section:

   ```
   implementation 'com.adobe.marketing.mobile:target:1.+'
   implementation 'com.adobe.marketing.mobile:target-vec:1.+'
   ```

1. The Mobile App VEC requires the following artifacts to be included as a dependency in `build.gradle`.

   ```
    implementation 'android.arch.lifecycle:extensions:1.1.1'
    implementation 'io.github.sac:SocketclusterClientJava:1.7.5'
    implementation 'com.android.support:support-compat:28.0.0'
    implementation 'com.android.support:support-fragment:28.0.0'
   ```

1. Add an intent filter in your `AndroidManifest.XML` file, choosing a unique deep-link scheme for Mobile App VEC authoring (for example, `[sdkbetabus://com.adobe.sdkbetabus](sdkbetabus://com.adobe.sdkbetabus)`):

   ```
   <activity 
       android:name=".listing.MoviesListingActivity" 
       android:launchMode="singleTask"> 
       <intent-filter> 
           <action android:name="android.intent.action.VIEW" /> 
      
           <category android:name="android.intent.category.DEFAULT" /> 
           <category android:name="android.intent.category.BROWSABLE" /> 
      
           <data 
               android:host="com.adobe.sdkbetabus" 
               android:scheme="sdkbetabus" /> 
       </intent-filter> 
   </activity>
   ```

1. Go to your mobile project and insert the following lines at the end of `Application::onCreate override`:

   ```
   public class SDKTest extends MultiDexApplication { 
      
       @Override 
       public void onCreate() { 
           /* Put Your App's implementation */ 
           MobileCore.setApplication(this); 
           MobileCore.setLogLevel(LoggingMode.DEBUG); 
           MobileCore.configureWithAppID("YOUR_ADOBE_LAUNCH_APP_ID"); 
             
           ... 
           try { 
               TargetVEC.registerExtension(); //Single line code to initialize TargetVEC
               Target.registerExtension();
               Identity.registerExtension();
               Lifecycle.registerExtension();
               Signal.registerExtension();
               MobileCore.start(null);
           } catch (InvalidInitException e) { 
             .. 
           }
       }

   /* Rest of Application test goes here ... */
   ```

1. If your build is not working, review the example projects provided below that should build out-of-the-box and review changes in the following locations:

    1. `Application::OnCreate override` 
    1. `AndroidManifest.XML`
    1. `build.gradle` of the Android application

## Set Up Target Views on your mobile app {#views}

The Adobe Mobile SDK exposes a new method for developers to trigger whenever a new View is rendered. As a developer, you must ensure that the views are named uniquely, and the `targetView` call is on the UI main thread. In this section, we will first demonstrate how to insert these calls with two different demonstration applications and discuss general guidelines on how to properly insert the Target View API calls for any Android app.

>[!NOTE]
>
>If the `targetView function` is not triggered, the VEC extension tries to identify View from the Android activity. For applications that do not have dynamic views, this can be an optional step.

A Target View can be triggered with a function call. Any targeting parameters can be optionally provided with the view.

```
public class TargetVEC { 
   
   /** 
    * Marks a view hierarchy for editing in Mobile App VEC.  Call must insert when the view hierarchy 
    * is memory and committed to being shown, but not yet shown on the screen. 
    * 
    * @param viewName the unique Target View Name 
    */ 
   public static void targetView(String viewName); 
  
  /** 
   * Trigger Target view 
   * Triggering a Target view may cause Target offers to be applied on the current container component. 
   * Note that Target offers are applied from local Target cache, so flicker should be negligible. 
   * 
   * @param viewName Mandatory Target View name, which must be unique at app level 
   * @param parameters Parameters to be included in the next Target call 
   */ 
  
    public static void targetView(String viewName, TargetParameters parameters); 
}
```

Our first example project is a mock-up of simple bus schedule application. To set up this application for use in the Mobile App VEC:

1. In Android Studio, open the project with the `build.gradle` file in the package subdirectory `BusBooking`. 
1. In the `DemoApplication::OnCreate` method, add `TargetVEC.registerExtension()` to register the Target VEC extension, along with other extensions. 
1. Build and run the application. 
1. To enter the Mobile App VEC authoring mode, use the [!DNL sdkbetabus://com.adobe.sdkbetabus] as its URL scheme, and open the generated deep link on the device (see directions below).

From this simple bus-booking application, we use all the automatically generated Target Views associated with the activity life cycle. Furthermore, we demonstrate the flexibility of the API by calling the Target View API on a custom view element that is dynamically added when a hidden button is clicked (the offer image on the screen). This new Target View is implemented by inserting an API call in the code at `OfferDetailsActivity.java:40`. When the hidden button is clicked, a new Target View event called "SURPRISE_VIEW" is fired, allowing the marketer to more precisely target change on the application experience.

Targeted Dynamic View Insertion:

```
package com.adobe.target.examples.bus; 
   
import android.app.DialogFragment; 
import android.os.Bundle; 
import android.os.Handler; 
import android.support.v7.app.AppCompatActivity; 
import android.support.v7.widget.Toolbar; 
import android.view.View; 
import android.view.ViewGroup; 
import android.widget.LinearLayout; 
import android.widget.Toast; 
   
import com.adobe.target.mobile.TargetVEC; 
   
/** 
 * This activity class is responsible to show offer details 
 */ 
public class OfferDetailsActivity extends AppCompatActivity { 
    @Override 
    protected void onCreate(Bundle savedInstanceState) { 
        super.onCreate(savedInstanceState); 
        setContentView(R.layout.activity_offer_details); 
        setUpToolBar(); 
        final Handler mainHandler = new Handler(getApplicationContext().getMainLooper()); 
   
        final View surpriseView = getLayoutInflater().inflate(R.layout.suprise_layout, 
                (ViewGroup) findViewById(android.R.id.content), false); 
   
        final View imagePresentView = this.findViewById(R.id.image_present); 
        final LinearLayout currentLayout = this.findViewById(R.id.offer_layout); 
   
        imagePresentView.setOnClickListener(new View.OnClickListener() { 
            @Override 
            public void onClick(View v) { 
                Toast.makeText(getApplicationContext(),"Surprise!", Toast.LENGTH_SHORT).show(); 
                mainHandler.post(new Runnable() { 
                    @Override 
                    public void run() { 
                        currentLayout.addView(surpriseView); 
                        TargetVEC.targetView("SURPRISE_VIEW"); 
                        currentLayout.invalidate(); 
                    } 
                }); 
                // One-shot.  Remove clicker afterwards. 
                imagePresentView.setOnClickListener(null); 
            } 
        }); 
    } 
   
    private void setUpToolBar() { 
        Toolbar toolbar = findViewById(R.id.toolbar); 
        toolbar.setNavigationIcon(R.drawable.abc_ic_ab_back_material); 
        toolbar.setTitle("Buy 1 Get 1"); 
        toolbar.setNavigationOnClickListener(new View.OnClickListener() { 
            @Override 
            public void onClick(View v) { 
                onBackPressed(); 
            } 
        }); 
    } 
   
    @Override 
    protected void onPause() { 
        super.onPause();
        MobileCore.lifecyclePause();
    } 
   
    @Override 
    protected void onResume() { 
        super.onResume();
        MobileCore.lifecycleStart(null);
    } 
}
```

## Setting Up profile parameters and other global parameters {#parameters}

We now support setting global parameters that will be passed in each and every API call, as well as passing mbox/view parameters to corresponding views.

Parameters include:

* mbox/view parameters 
* profile parameters 
* Product parameters 
* Order parameters

**Global parameter support:**

```
Map<String, String> mboxParams = new HashMap<>();  //Mbox or view params 
mboxParams.put("mboxparam1", "mboxvalue1"); 
Map<String, String> profileParams = new HashMap<>();  //Profile params 
profileParams.put("profilekey1", "profilevalue1"); 
  
TargetVEC.setGlobalRequestParameters(new TargetParameters.Builder() 
        .parameters(mboxParams) 
        .profileParameters(profileParams) 
        .product(new TargetProduct("1234", "furniture")) 
        .order(new TargetOrder("12343", 123.45, Arrays.asList("100", "200"))) 
        .build());
```

**Passing parameters for next view trigger:**

We have provided some automatic views that are created by default, such as "`AUTO_<activity|fragment name>`" for each activity and fragment present in your app. If you want to pass these parameters, you can call the following API:

```
Map<String, String> mboxParams = new HashMap<>();  //Mbox or view params 
mboxParams.put("viewKey1", "viewparam1"); 
Map<String, String> profileParams = new HashMap<>();  //Profile params 
profileParams.put("profilekeyforview1", "profilevalueforview1"); 
  
TargetVEC.setRequestParameters(new TargetParameters.Builder() 
        .parameters(mboxParams) 
        .profileParameters(profileParams) 
        .product(new TargetProduct("1234", "furniture")) 
        .order(new TargetOrder("12343", 123.45, Arrays.asList("100", "200"))) 
        .build());
```

**Passing parameters to a specific view:**

We have seen the API trigger Views via `TargetVEC.targetView("view_name")`. You can also pass parameters that are specific to the particular view, as shown below:

```
Map<String, String> profileParams = new HashMap<>(); 
profileParams.put("surprisekey1", "surprisevalue1");  //ProfileParams 
TargetVEC.targetView("SURPRISE_VIEW", 
        new TargetParameters.Builder() 
                .profileParameters(profileParams) 
                .product(new TargetProduct("3354", "kitchen")) 
                .build());
```

## Calling the Prefetch API explicitly {#section_2D02B74558474D3BA9F25E4D25E7C7E3}

There might be certain scenarios when you might want to call the prefetch API again to refresh the offers stored in cache. The following APIs are exposed, which are described as:

* **prefetchOffers**

  ```
  /** 
   * Prefetch Target offers. 
   * Note that calling this will pre-hide the current layout, until Target offers are prefetched 
   * and applied to currently visible Target views, possibly causing flicker, thus it's recommended 
   * to call this method inside the containing component's onCreate() lifecycle method 
   */ 
  public static void prefetchOffers();
  ```

* **prefetchOffersBackground**

  ```
  /** 
   * Prefetch Target offers in the background. 
   * Note, that in contrast to prefetchOffers(), calling this method will NOT pre-hide 
   * the current layout, instead prefetched Target offers will be only be cached and will subsequently 
   * be applied as Target Views are being triggered. 
   */ 
  public static void prefetchOffersBackground();
  ```

## Tutorial: Implement the Experience Cloud in Mobile Android Applications {#tutorial}

* [Implement the Experience Cloud in Mobile Android Applications](https://docs.adobe.com/content/help/en/experience-cloud/implementing-in-mobile-android-apps-with-launch/index.html)

After completing this tutorial you will be able to:

* Create a mobile Launch property
* Install a Launch property in an Android app
* Implement the following Adobe Experience Cloud solutions:
  * Experience Cloud ID Service
  * Adobe Target
  * Adobe Analytics
  * Adobe Audience Manager

* Publish changes in Launch through development, staging, and production environments
