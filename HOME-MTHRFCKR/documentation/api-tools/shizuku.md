# Shizuku

---

```cardlink
url: https://shizuku.rikka.app/
title: "Shizuku"
description: "Let your app use system APIs directly"
host: shizuku.rikka.app
favicon: /icon/android-icon-192x192.png
```

Let your app use system APIs directly

[Learn more](/introduction.html)

## Use System APIs Elegantly

Forget about root shell, you can use APIs with higher privileges "directly". Also, Shizuku is significantly faster than shell.

## Supports Adb Usage

If your "root required app" only needs adb permission, you can easily expand the audience by using Shizuku.

## Save Your time

Shizuku has detailed documentation to guide users. Only you need to do is to let the users install Shizuku.

### [#](#as-easy-as-you-are-a-system-app) As Easy as You Are a System App

```
private static final IPackageManager PACKAGE_MANAGER = IPackageManager.Stub.asInterface(
    new ShizukuBinderWrapper(SystemServiceHelper.getSystemService("package")));

public static void grantRuntimePermission(String packageName, String permissionName, int userId) {
    try {
        PACKAGE_MANAGER.grantRuntimePermission(packageName, permissionName, userId);
    } catch (RemoteException tr) {
        throw new RuntimeException(tr.getMessage(), tr);
    }
}
```
