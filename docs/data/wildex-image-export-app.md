# WildEx Image Export App

The WildEx Image Export app is a desktop tool that pairs with Wildbook and allows users to export the annotated images and the related metadata. The primary goal is to allow users to update their individual ID kits using the data from the curated catalog.

> This tool is possible thanks to our partnership with [Tech4Conservation](https://www.t4c.org/), who generously donated the original code to the Wild Me tool suite.

## Install the desktop app

WildEx Image Export is available for both Windows and Mac.

1. To download, visit [Wild Me Add-ons](https://www.wildme.org/addons.html).
2. Double-click to download the appropriate version.
3. Once the download completes, click to install.
4. The app should automatically open once installed.

```{note}
Despite the warning that generates when you click to install the app, the tool is secure. We are aware of the issue and will work to resolve it. For now, acknowledge the security warnings and select to install anyway.
```

## Generate a WildEx export from Wildbook

1. Sign in to your Wildbook account.
2. Select **Search** > **Encounter Search**.
3. Set the available filters to limit the data to your desired results and click **Search Encounters**.
4. Once the search results have generated, select the **Export** tab.
5. Next to Encounter Annotation Export, click **Click here**.
6. Wait while the export is generated. It will appear as a download and be accessible from your desktop, typically in the Downloads folder.

## Export from the desktop app

1. Open the WildEx Image Export app on your desktop.
2. Select the generated Annotation export file from the previous section.
3. If you want to **include unidentified encounters in the export**, select **Yes**. Otherwise, keep the defaults.
4. Set the **number of annotations per individual ID** you want to download. By default, this will be 4, which downloads one annotation per viewpoint.
5. Click **Download Annotations**.
6. Select where the folder should be created.
7. Wait for your download to complete.

Downloaded images will be available in folders labelled by the individual. If you selected to include unidentified individuals, they will all be included in a single folder labeled *Unidentified_individuals*.

## FAQ

### What if my internet is slow? Can I still download?

You can still use the tool, but it is recommended to create smaller export sheets, either by modifying your search or subsetting the resulting export.

### I got an error notification. What do I do?

1. Go to the folder where you’re downloading the images to
2. Find an excel file with the same name as the original export file except with .resume added to the file name – open this file
3. Go to the “Encounter.sourceUrl” column (column B) to access the encounter(s) that are causing the download to error
4. Resolve the issue(s)
5. Return to the WildEx desktop utility and select the .resume version of the original export file to restart and complete the download