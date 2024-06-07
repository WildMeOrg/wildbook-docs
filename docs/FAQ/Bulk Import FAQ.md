# Wildbook

Additional help with [Bulk Imports](https://docs.wildme.org/product-docs/en/wildbook/data/bulk-import-beta/) in Wildbook is available in our docs.

## What should I put in media asset columns in a bulk import?

Media asset columns should be named `"Encounter.MediaAsset.X"`, where **X** is an actual number, starting with **0** `(Encounter.MediaAsset.0)`. The content of each cell should be the asset filename, including the path to the asset. For example, the `"Encounter.MediaAsset.1"` column could contain cells `"majestic_whale1.jpg"` and `"majestic_whale2.jpg"`. Check the [Photography guidelines](https://docs.wildme.org/product-docs/en/wildbook/data/photography-guidelines/#image-formats-and-sizes) for supported image formats.

## Why is my bulk import taking so long?

Although bulk imports can support up to 1000 encounters in a single spreadsheet, that also makes it slow to process and slow to load. Try to limit each spreadsheet to a few hundred encounters or less.

## What do the statuses in the Match Results By Class column mean?

* waiting to queue - Images haven't sent to [WBIA](https://docs.wildme.org/product-docs/en/wildbook/introduction/) yet
* queuing - Trying to send images to WBIA
* queued - Images in WBIA, waiting for them to come back
* working - Identification actively in progress.
* error - Something went wrong. Let us know in the [Community Forums](https://community.wildme.org/).
* exception - Something went wrong. Let us know in the [Community Forums](https://community.wildme.org/).
* suppressed - Something went wrong. Let us know in the [Community Forums](https://community.wildme.org/).
* completed - Done; images back from WBIA

## Why can't I edit my imported encounters?

If you don't include your username in the `Encounter.submitterID` field of your spreadsheet, your imported encounters will be unassigned. To fix this, [delete your bulk import](https://docs.wildme.org/product-docs/en/wildbook/data/bulk-import-beta/#deleting-a-bulk-import), update your spreadsheet, and import your data again.

### What Excel file formats are supported?

.xlsx only

### I found other fields in the database, but they don't work when I try to use them in the importer.

There are a number of additional fields that cannot be set using the Bulk Import capability. For example, the following fields can only be used in Wildbooks where sightings occur under water:

* `Encounter.depth`
* `Occurrence.bearing`
* `Occurrence.distance`
* `Occurrence.seaState`
* `Occurrence.seaSurfaceTemp`
* `Occurrence.swellHeight`
* `Occurrence.transectBearing`

### I made a mistake and want to reload my encounters.

You can [delete your bulk import](https://docs.wildme.org/product-docs/en/wildbook/data/bulk-import-beta/#deleting-a-bulk-import) and reimport your data.

### I uploaded the wrong image, but when I clicked back to try again, the image was still listed in the Photo Review page.

The Photo Review page is a temporary storage space of recently imported photos. This is the first step of the bulk import process. The second step happens when the spreadsheet is uploaded and connects the data to the images from that temporary folder.

If any of the images are re-imported with the same file name, the new image data will overwrite the image in that temporary folder, but historical data that has already completed the second step of the bulk import process is left alone.

If the wrong image isn't cited in your spreadsheet or if you didn't upload your spreadsheet yet before going back to fix your images, then it won't appear in your encounters.

### How do I associate multiple images with a single encounter?

You can add a virtually infinite number of images with a single encounter using the Encounter.mediaAsset**X** field. For each photo you want to associate with a given encounter, create an Encounter.mediaAsset**X** column, where **X** is a variable you replace with a number starting with X=0.

| Encounter.mediaAsset0 | Encounter.mediaAsset1 | Encounter.mediaAsset2 |
| --------------------- | --------------------- | --------------------- |
| photo1.png | photo2.png | photo3.png |

### I want to set photographerX.affiliation or photographerX.fullName without providing an email address.

At present, there is no way to provide this information without providing an email address because these fields are tied into the system user management.

To work around this, you can provide an email that is used system-wide for all submissions that don't have an email associated (e.g., if you have a photograph submitted by a tourist through an external site, you can reference an email associated with the site along with the tourist's name). This is also true for submitter**X**.affiliation and submitter**X**.fullName.

### The docs say I can't do XYZ in my spreadsheet, but I've done it before without a problem.

Wildbooks are always being improved as a result of testing and user feedback. Sometimes this means that we have to make changes to old processes to make way for new ones. We do our best to keep our docs updated to reflect the most up-to-date information on using Wildbooks. When in doubt, check the [docs](https://docs.wildme.org/product-docs/en/) or visit the [Community Forums](https://community.wildme.org/) for guidance.

***

# Scout

Work in progress

***

# Codex

Additional help with [Bulk Imports](https://docs.wildme.org/product-docs/en/codex/getting-started-with-codex/bulk-reporting/) in Codex is available in our docs.