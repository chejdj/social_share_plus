# social_share

A plugin supports variety of sharing contents and sharing platforms.

## Introduction

| Platforms | Content | OS  |
| ----  | ---- | ----|
| **wechat**    | **Text/Image/Music/Video/WebPage/File** | **Android/iOS**  |
| **Facebook**   | **Text/Image/WebView/File**| **Android/iOS** |
| **Line** | **Text/Image/File** | **Android/iOS**|
| **Twiter**| **Text/Image/File** | **Android/iOS**|
| **WhatsApp**| **Text/Image/File** | **Andorid/iOS**|
| **SystemShare** | --- | --- |

![all.png](https://s2.loli.net/2022/07/13/L6q5pDtOSfMNbBl.jpg)  ![facebook.png](https://s2.loli.net/2022/07/13/P5vh7mUY9fuectG.jpg)  
![whatsapp.png](https://s2.loli.net/2022/07/13/edq2A3S9OQaZKEx.jpg) ![wechat.png](https://s2.loli.net/2022/07/13/342FbwsHMdEpLli.jpg)  ![line.png](https://s2.loli.net/2022/07/13/oDKvgL6fYyQrIeA.jpg)  

## Usage
### reigster
```
 LaShareRegister register = LaShareRegister();
    register.setupWechat(appId, secretKey, universalLink); //only need wechat 
    LaSharePlugin.registerPlatforms(register);
```  
### share
#### 1.construct share data**
```
LaShareParamsBean generateBean() {
        return LaShareParamsBean(
              contentType: LaShareContentTypes.webpage,
              platform: LaSharePlatforms.whatsApp,
              webUrl: webUrl,
              title: title,
              text: desc,
              imageFilePath: imgFilePath,
            );
    }
```  
#### 2.start share
```
 LaSharePlugin.share(
          generateBean(),
          notInstallCallBack,
          successCallBack,
          errorCallBack,
        );
```  
### 3. check App whether install
```
LaSharePlugin.isClientInstalled(LaSharePlatforms.whatsApp);
```  
### 4. pop share dialog
```
   LaSharePlugin.startShare(generateBean(),notInstallCallBack,successCallBack,errorCallBack);
```  
## Attention
1. iOS wechat image share use the SystemShare because wechat forbidden the image share for foreign.
2. You should add some scheme config for accessing outer apps. Refer to example configuration.

