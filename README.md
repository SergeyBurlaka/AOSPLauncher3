# AOSPLauncher3

Launcher3 is the default launcher in [AOSP Android](https://android.googlesource.com/platform/packages/apps/Launcher3/), 
and is the base behind many customized launchers - even Google's own Now Launcher (obsolete) and Pixel Launcher. 

## describe 
My repo has [ore-m2-release ](https://android.googlesource.com/platform/packages/apps/Launcher3/+/oreo-m2-release) [Launcher3](https://android.googlesource.com/platform/packages/apps/Launcher3/) project branch 
with fixed and bring-up [build gradle file](https://github.com/SergeyBurlaka/AOSPLauncher3/blob/oreo-m2-release/build.gradle)  for android studio success building.

## art

<div class="center-block">
  
  <img src="https://github.com/SergeyBurlaka/AOSPLauncher3/blob/oreo-m2-release/art/photo5377854175276280538.jpg" height="1000" alt="Screenshot">
  
<img src="https://github.com/SergeyBurlaka/AOSPLauncher3/blob/oreo-m2-release/art/photo5377854175276280539.jpg" height="1000" alt="Screenshot"/>


## how aps loading into launcker view

```java
 com.android.launcher3.allapps   
 
   private final AlphabeticalAppsList mApps;

  public void setPredictedApps(List<ComponentKeyMapper<AppInfo>> apps) {
       [- AlphabeticalAppsList-] mApps.setPredictedApps(apps);
    }



//LOAD APS INTO VIEW->
 [- AlphabeticalAppsList-] mApps.setPredictedApps(apps);


//BIND APPS
LoaderResults[]---|
                  |
                  | 
   public void bindAllApplications(final ArrayList<AppInfo> apps) [-
                                                                   
                                           mAppsView.setApps(apps);
                                          mLauncherCallbacks.bindAllApplications(apps);
                                                                   
                                                                   -]
```

