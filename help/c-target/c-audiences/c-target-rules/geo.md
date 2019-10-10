---
description: Use audiences to target users based on their geographical location, including their country, state/province, city, zip/postal code, DMA, or mobile carrier.
keywords: targeting;a4t;geo;geotargeting;geotargeting accuracy;country;state;city;zip code;dma;mobile carrier;city codes;region codes;country codes;metro codes;profile scripts;geotargeting profile scripts;geotargeting mobile
seo-description: Use Adobe Target audiences to target users based on their geographical location, including their country, state/province, city, zip/postal code, DMA, or mobile carrier.
seo-title: Geo
solution: Target,Analytics
title: Geo targeting in Adobe Target
topic: Reports and analytics
uuid: d30cda0e-016e-4391-95b7-ff3b55e06bf0
---

# Geo{#geo}

Use audiences to target users based on their geographical location, including their country, state/province, city, zip/postal code, DMA, or mobile carrier.

Geo location parameters allow you to target activities and experiences based on your visitors' geography. You can include or exclude visitors based on their country, state/province, city, zip/postal code, latitude, longitude, DMA, or mobile carrier. This data is sent with each Target request and is based on the visitor's IP address. Select these parameters just like any targeting values.

## Create an Audience with Geo Targeting {#section_49CBFFAAC8694C4AAD3DE4B2DB7B05DE}

1. In the [!DNL Target] interface, click **[!UICONTROL Audiences]** > **[!UICONTROL Create Audience]**. 
1. Name the audience. 
1. Click **[!UICONTROL Add Rule]** > **[!UICONTROL Geo]**.

1. Click **[!UICONTROL Select]**, then select one of the following options:

    * Country 
    * State 
    * City 
    * Zip Code 
    * Latitude 
    * Longitude 
    * DMA 
    * Mobile Carrier

   A visitor's IP address is passed with an mbox request, once per visit (session), to resolve geo targeting parameters for that visitor.

   For Mobile Carrier, [!DNL Target] uses the IP address registration data (who owns the block of IP addresses) to determine the appropriate mobile carrier using [Mobile Country Codes (MCC) and Mobile Network Codes MNC)](https://www.mcc-mnc.com).

1. Specify an operator and the the appropriate value.
1. (Optional) Click **[!UICONTROL Add Rule]** and set up additional rules for the audience. 
1. Click **[!UICONTROL Save]**.

The following illustration shows an audience that targets users accessing the activity from a latitude greater than 44 degrees and a longitude less than 22 degrees.

![](assets/target_geo.png)

## Accuracy {#section_D63D5FFCB49C42F9933AFD0BD7C79DF1}

The accuracy of geo targeting depends on several factors. WiFi connections are more accurate than cellular networks. When the visitor is using a cellular data connection, the accuracy of the geo-lookup can be affected by location, the provider's data relationship with [DeviceAtlas](https://deviceatlas.com/device-data/user-agent-tester), and other factors. Cell tower-based network connections might be less accurate than wired or WiFi connections. Also, a visitor's IP address might be mapped to his or her ISP location, which might not be the same as the visitor's actual location. Some mobile geo-location issues can be solved using the [Geolocation API](https://developer.mozilla.org/en-US/docs/Web/API/Geolocation_API).

The following table shows the accuracy of IP-based geographical information from [DigitalEnvoy](https://www.digitalelement.com/solutions/) for wired or WiFi Internet connections. DigitalEnvoy provides the most accurate data in the industry. Global accuracy is more than 99.9 percent at the country level and is up to 97 percent accurate at a city level. Accuracy information does not apply to cell tower-based networks.

| Country | State | City | Region |
|--- |--- |--- |--- |
|US|99.99%|96%|94%|
|Canada|99.99%|96%|94%|
|Europe|99.99%|||
|UK|99.99%||87%|
|Germany|99.99%|95%|93%|
|Scandinavia|99%|Low 90s|Mid 80s|
|Spain|99.99%|Around 90%|Mid to high 90s|
|Asia|99%|Mid 90s|Low 90s|
|Japan|99.99%|Mid 90s|Low 90s|
|Australia|99.99%|94%|91%|

## Using Geo-Targeting in Profile Scripts {#section_92C93138542C4A94997E3F4BE3F5DA28}

You can use geo information for profile scripts.

For example, use:

* `profile.geolocation.country` 
* `profile.geolocation.state` 
* `profile.geolocation.city` 
* `profile.geolocation.zip` 
* `profile.geolocation.dma` 
* `profile.geolocation.domainName` 
* `profile.geolocation.ispName` 
* `profile.geolocation.connectionSpeed` 
* `profile.geolocation.mobileCarrier`

So, you can write a target expression called "From North America" with the following code:

`return profile.geolocation.country == 'united states' || profile.geolocation.country == 'canada' || profile.geolocation.country == 'mexico';`

## Using Geo-Targeting Values as Tokens {#section_E7F7FDF62C3B4934A6565D04B24655F6}

You can now use `profile.geolocation` values directly as tokens in offers, plugins, and so forth.

For example, use:

* `${profile.geolocation.country}` 
* `${profile.geolocation.state}` 
* `${profile.geolocation.city}` 
* `${profile.geolocation.zip}` 
* `${profile.geolocation.dma}` 
* `${profile.geolocation.domainName}` 
* `${profile.geolocation.ispName}` 
* `${profile.geolocation.connectionSpeed}` 
* `${profile.geolocation.mobileCarrier}` 
* `${profile.geolocation.latitude}` 
* `${profile.geolocation.longitude}`

## Geotargeting FAQ {#section_DD308A53AF0F48FA8C81423580561FE7}

**How do I specify latitude and longitude?**

* The value for latitude/longitude should be a numeric value in degrees. 
* The value for latitude/longitude can have a maximum precision of five decimal places. 
* The value for latitude should be between -90 and 90. 
* The value for longitude should be between -180 and 180.

**How does geo targeting work for mobile devices?**

The vast majority of mobile device users access content via WiFi, which means Target's IP-based geo targeting is as accurate as on a desktop. Cell tower-based connections might be less accurate because the visitor's IP address is based on the tower where the signal is being picked up. Some mobile geo-location issues can be solved using the [Geolocation API](https://developer.mozilla.org/en-US/docs/Web/API/Geolocation_API).

**How does geo feature handle visitors from AOL?**

Due to the way AOL proxies its traffic, we can only target them at a country level. For example, a campaign targeted to France will successfully target AOL users in France. But a campaign targeted to Paris will not successfully target AOL users in Paris. If your intent is to specifically target AOL users, you can set the region field to "aol." In fact, you can target US AOL users by specifying two targeting conditions: country exactly matches "united states" and region exactly matches "aol."

**What location granularity does geo targeting provide?**

* Country - global 
* State/province/region - global 
* City - global 
* Zip/postal code - US, Germany, Canada 
* DMA/ITV (UK) - US, UK 
* Mobile carrier - global

**How can I test my activities as if I'm a user coming from a different location?**

You can override your IP address with an IP address from a different location and use the `mboxOverride.browserIp url` parameter. So if your company is in the UK, but your global campaign targets visitors in Aukland, New Zealand, use this style of URL assuming that `60.234.0.39` is an IP address in Auckland:

`https://www.mycompany.com?mboxOverride.browserIp=60.234.0.39`

You'll need to clear your cookies before doing this.

**How are territories, such as Puerto Rico and Hong Kong, mapped into the geo-targeting structure?**

Puerto Rico, Hong Kong, and other territories are treated as separate "Country" values. 

## Training video: Creating Audiences

This video includes information about using audience categories.

* Create audiences 
* Define audience categories

>[!VIDEO](https://video.tv.adobe.com/v/17392)
