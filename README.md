# Use examples

# Get the preloaded information configured inside the AndroidManifest


String resultData = null;
        try {
            PackageManager packageManager = getPackageManager();

            if (packageManager != null) {
                ApplicationInfo applicationInfo = packageManager.getApplicationInfo("com.meizu.flyme.meizupreinstall", PackageManager.GET_META_DATA);
                if (applicationInfo != null) {
                    if (applicationInfo.metaData != null) {
                        resultData = applicationInfo.metaData.getString(getPackageName());
                    }
                }

            }
        } catch (PackageManager.NameNotFoundException e) {
            e.printStackTrace();
        }
        //Whether or not it is meizu preinstalled
        if (resultData != null && resultData.equalsIgnoreCase("meizu_preinstall")) {

        } else {

        }
