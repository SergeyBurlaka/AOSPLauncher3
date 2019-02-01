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


## code snippet 
> How aps loading into launcker view.

> LauncherModel.java

```java
 com.android.launcher3
 
public boolean startLoader(int synchronousBindPage)
                // ----LoaderResults----
                                         
                    
                    loaderResults.bindWorkspace();
                    // For now, continue posting the binding of AllApps as there are other
                    // issues that arise from that.
                    loaderResults.bindAllApps();
                    loaderResults.bindDeepShortcuts();
                    loaderResults.bindWidgets();


```

> LoaderResult.java

```java
  com.android.launcher3.model

//LoaderTask.java  mResults.bindAllApps()

public void bindAllApps()

       final ArrayList<AppInfo> list = (ArrayList<AppInfo>) mBgAllAppsList.data.clone();
       
         callbacks.bindAllApplications(list);  // (Launcher) bindAllApplications

```

>LoaderTask.java

```java

            // second step
            if (DEBUG_LOADERS) Log.d(TAG, "step 2.1: loading all apps");
            loadAllApps();

            if (DEBUG_LOADERS) Log.d(TAG, "step 2.2: Binding all apps");
            verifyNotStopped();
            mResults.bindAllApps();
```
