# Matching Process

Wildbook provides several ways to automatically and manually access the [Image Analysis Pipeline](https://docs.wildme.org/product-docs/en/wildbook/introduction/image-analysis-pipeline/) to identify individual animals, as well as to perform by-eye individual ID. Wildbook assists you in photo ID but never makes a decision for you. You can find answers to frequently asked questions about matching [here](https://docs.wildme.org/product-docs/en/faq/matching-faq/).

***

## Automated Detection and ID with Encounter submission

When you [Report an Encounter](https://docs.wildme.org/product-docs/en/wildbook/data/report-an-encounter/) of a single animal, if you set the species to one supported by the [Image Analysis Pipeline](https://docs.wildme.org/product-docs/en/wildbook/introduction/image-analysis-pipeline/), Wildbook will automatically perform the following steps:

1. Send each submitted image to **Detection** to find one or more **Annotations** in each photo. In the event that **Detection** doesn’t find any animal in the photo, users can use **[Manual Annotation](https://docs.wildme.org/product-docs/en/wildbook/data/manual-annotation-beta/))**.
2. Depending on the type of **Annotations** returned (its **"Image Analysis Class"**), such as **"whale\_orca"** or **"panthera\_uncia"**, route each Annotation to one or more ID algorithms.
3. If the location **ID** (or **"study site"**) was set during the submission, the pipeline will limit candidate matches to only that study site.
4. Consolidate all Annotation match results into a single page for your review and ID assignment **(e.g., setting an existing individual ID or assigning a new ID).** See [Reviewing Match Results](https://docs.wildme.org/product-docs/en/wildbook/data/matching-process/#reviewing-match-results) to understand the results page. The Encounter page also allows you to set individual ID later, and you can return to these match results in the future as well.

Because **Detection** and **Identification** reside in a queue of computer vision actions requested by all users of your Wildbook, you may not immediately see the results of the [Image Analysis Pipeline](https://docs.wildme.org/product-docs/en/wildbook/introduction/image-analysis-pipeline/).

If you see green bounding boxes on images in your submitted Encounter, then Detection has completed. After submission, you may need to periodically refresh the Encounter page for the bounding boxes to appear.

![](uploads/image.png-2212181302){width="515" height="429"}

***

* whale\_orca+fin\_dorsal **(bounding box around the dorsal fin)**
* whale\_orca **(bounding box around the whale body)**

If you see green bounding boxes on images in your submitted Encounter and **match results** appears in the menu of any image, then Identification has started or completed. After submission, you may need to periodically refresh the Encounter page for the bounding boxes to appear and match results to be ready. Click **match results** to review potential ID matches.

See [Reviewing Match Results](https://docs.wildme.org/product-docs/en/wildbook/data/matching-process/#reviewing-match-results) for more information.

***

![simpleGalleryBoundingBoxMatchResults](uploads/image.png-2212181820){width="529" height="474"}

***

## Automated Detection and ID with Bulk Import

After a successful [Bulk Import](https://docs.wildme.org/product-docs/en/wildbook/data/bulk-import-beta/), Detection and Identification can be run from the **Import summary**, allowing for large scale processing. However, this can also cause delays for other Users attempting to use the [Image Analysis Pipeline](https://docs.wildme.org/product-docs/en/wildbook/introduction/image-analysis-pipeline/) and its job queue. See [Bulk Import](https://docs.wildme.org/product-docs/en/wildbook/data/bulk-import-beta/) for more information.

## Manual Annotation with Automated ID

While Wildbook uses advance machine learning to find and label animals in images, it always has a probability of missing an Annotation. Wildbook allows you to draw additional bounding boxes on an image, label their viewpoints (e.g., "left", "right", etc.), and their classes (e.g., "whale\_fluke", "panthera\_uncia", etc.). Once a manual Annotation has been created, its will appear as a normal Annotation on an image and will allow you to [manually start a match](https://docs.wildme.org/product-docs/en/wildbook/data/matching-process/#manually-starting-a-match). See [Manual Annotation](https://docs.wildme.org/product-docs/en/wildbook/data/manual-annotation-beta/) for more information.

***

![add Annotation](uploads/image.png-2212181958){width="529" height="474"}

***

### Removing an Annotation

To remove an Annotation from *machine learning-based Detection* or **[Manual Annotation](https://docs.wildme.org/product-docs/en/wildbook/data/manual-annotation-beta/)**, go to **Encounter Gallery** and select **Remove Annotation**.

#### **Removing a single annotation:**

* Removing an **Annotation** from an image will not remove the image from the **Encounter** it’s referenced in *as long as there are no other Encounters that share the same image.*

#### Removing multiple annotations:

* Removing all the **Annotations** that are only present on a single **Encounter** will automatically remove the record of that image on that Encounter.
* If other **Annotations** of the same image are referenced in other **Encounters**, those other **Annotations** and the image’s record will still be present in those **Encounters**.

***

![delete Annotation](uploads/image.png-2212182037){width="529" height="474"}

***

## Manually Starting a Match

For a matchable Annotation, you can start or re-run matching from the Encounter page Gallery by selecting **start match** or **start another match** from the menu for the Annotation.

***

![start Match](uploads/image.png-2212182200){width="529" height="474"}

***

**Choose criteria to match against** dialog box appears and allows you to:

* multi-select location IDs to match against, allowing you to remove unlikely locations from the results. If set, the location ID of the Encounter will be selected by default.
* filter to only your data
* select one or more algorithms to use for identification

***

![match Criteria](uploads/image.png-2212182250){width="694" height="566"}

Click **Match** to start the matching process.

***

## Reviewing Match Results

To review the results of the automated matching process, select **match results** from the menu on the Annotation in the Encounter Gallery. If you recently submitted the Encounter, you may need to wait and then refresh your browser periodically for Wildbook to process the results from automated Detection before the **match results** menu option appears.

***

![simple Gallery Bounding Box Match Results](uploads/image.png-2212182435){width="529" height="474"}

***

Each match result page may show one or more sets of matches, potentially displaying:

* one algorithm match for one annotation (e.g., by clicking **start another match** on an annotation for which only one ID algorithm is configured)
* multiple algorithm matches for one annotation (e.g., by clicking **start another match** on an annotation for which multiple ID algorithms are configured)
* multiple algorithm matches for multiple annotations (e.g., a new Encounter submission with multiple photos)

The information displayed depends on where in Wildbook the [Image Analysis Pipeline](https://docs.wildme.org/product-docs/en/wildbook/introduction/image-analysis-pipeline/) was called from and for which species.

***

![match Results](uploads/image.png-2212182547){width="" height=""}

***

### Match results page sections

The following sections make up the matching results page.

#### Encounter banner

A banner labeled **Matching results for** at the top of the page provides a link to the related encounter and the associated Marked Individual, if an ID has been assigned to the Encounter.

#### Instructions

Click to expand the **Instructions** section to get instructions for reviewing matches on the page. Some of those are repeated here:

* Hover mouse over results to **compare candidates** to target.
* Links to the corresponding **encounters** and **individuals** are next to each match score.
* Select **correct match** by hovering over the correct result and checking the checkbox
* Use the buttons to switch between result types:
    * **Individual Scores:** This is the default. It computes one match score for every *individual* in the database. This is the aggregate of each image score for that individual.
    * **Image Scores:** computes the match score for every annotation in the database when compared to the query annotation
* Adjust the number of results that display in each list by changing the value in **Num Results** and selecting **set**.

#### Results: One ranked set per annotation per algorithm

Each block of ranked results represents the top-*N* matches (default top 12) to an Annotation in descending order. Rank 1 is the top suggested match, and each successive match is presented with relatively less confidence. Roll over each row in the list to review the potentially matched annotations. The annotation from your encounter appears on the left, labeled as the TARGET image. Potential candidates for matching appear on the right side, labeled to match their position in the list.

***

![match Results Section](uploads/image.png-2212182709){width="" height=""}

***

* **Rank:** The position in the listing (1,2,3,4, etc.).
* **Match score:** The match score represents the numeric value returned from the algorithm. These scores are not standardized between algorithms or platforms and are generally not bounded. For more information about interpreting algorithm scores, see [Identification](https://docs.wildme.org/product-docs/en/wildbook/introduction/image-analysis-pipeline/#identification).
* **Encounter link:** Opens a new tab to the potential match encounter.
* **Inspect:** Opens a new page focused on the features being matched. Areas that are highlighted display potentially matched features. Not every algorithm will provide additional detail. Only the first 12 matches may have additional detail.
* **Checkbox**: Select the checkbox to indicate that an encounter is a match with the target annotation.

***

### Setting the ID using the checkbox

In addition to setting the Individual ID from the [Encounter page](https://docs.wildme.org/product-docs/en/wildbook/introduction/encounter/), you can set the ID directly from the match results using the checkbox on any listed result. By clicking the checkbox, one of the following results will be suggested:

* *If the annotation is on an encounter for which the ID has not yet been set and the candidate annotation does not have an ID*, selecting the checkbox will display a new option in the upper right that includes:
    * a typeahead form field that allows you to enter a new ID to assign to both encounters or to look up an existing ID to assign to both encounters.
    * The button **Set individual on both encounters** that allows you to set the ID from the form field. Both annotations and their respective encounters now belong to the same marked individual.
* *If the annotation is on an encounter for which the ID has not yet been set and the candidate annotation has an ID set*, selecting the checkbox will display a new button in the upper right **Set to individual**. Click the button to assign the suggested individual ID to the annotation and its Encounter. Both annotations and their respective encounters now belong to the same marked individual.
* *If the annotation is on an encounter for which the ID has been set and the candidate annotation has a different ID set*, selecting the checkbox will display a new button in the upper right **Merge individuals**. Click **Merge individuals** to merge the two Marked Individuals into a single record, assigning all encounters from both previously individuals to a single individual.

***

## Visual Matcher

Visual Matcher is a separate, very limited user interface to support visual matching of encounters without computer vision. To access the Visual Matcher, select **visual matcher** on the annotation menu. Visual Matcher was largely developed to support giant manta matching before the availability of computer vision. It has very limited value outside of that task and the MantaMatcher.org platform.

![visual Matcher](uploads/image.png-2212182810){width="529" height="474"}

<br>
***

## Spot Mapping

For certain species in Sharkbook, the match process begins with spot mapping instead of an automated detection.

![](uploads/spotmapmenu.png-231102310){width="306" height="387"}

Detection for whale sharks, grey nurse sharks, and broadnose sevengill sharks all start with spot mapping. Spot mapping allows only one left side pattern and one right side pattern per Encounter.

From the Encounter image gallery, click on the menu icon of the image and select **spot mapping**. From here, you'll set your spot mapping region.

To create your region, use the the rotation icons to align the top blue line of the box with the dorsal fins. Grab anywhere else on the box to resize. Once you've set your region, toggle the radio buttons to set the anchor points for where the fins meet the body and map the spots. If you misplace a spot, click it again to remove it. The minimum number of spots you should add, not including the markers for the fins, is 3-5. **Save** your spot data when you're finished.

For whale sharks, click the **return to encounter** button. From the image menu of your new spot mapped region, follow the steps in [Manually Starting a Match](https://docs.wildme.org/product-docs/en/wildbook/data/matching-process/#manually-starting-a-match). Note that while you can run a scan task on whale sharks using the steps below, it produces less accurate results.

For grey nurse sharks and broadnose sevengill sharks, click the **start ScanTask** button. Click the **Go to sharkGrid administration to monitor for completion** link. **My Pending scanTasks** will display the spot map you just worked on. When it's ready, your completed tasks will appear in **My Completed scanTasks**.

Each scan will show the results of two algorithms: [Modified Groth and I3s](https://docs.wildme.org/product-docs/en/wildbook/introduction/image-analysis-pipeline/#modified-groth-and-i3s-spot-pattern-matching). The match score for Modified Groth means that the higher the score, the more likely the match is a correct one. For I3s, it’s the opposite: the higher the score, the less likely the match is a correct one.

If you’ve found a match, go back to your Encounter and edit the **[Identity](https://docs.wildme.org/product-docs/en/wildbook/introduction/encounter/#identity)** section to add to an existing Marked Individual or create a new one. Select matched by **Pattern match**.

Next, set the workflow state in the **[Metadata](https://docs.wildme.org/product-docs/en/wildbook/introduction/encounter/#metadata)** section to **approved**.

In addition to match candidates based on spot mapping placement, you may also be shown Nearby Matches. If a match is made between two locations for a given species, those locations are used for Nearby Matches in all future match sets.

If you want to create an association between two locations that don't already appear as Nearby Matches for each other, upload two encounters from each location for a Marked Individual and match them right away.

### Delete a Spot Map

Work in progress.

### Delete a Scan Task

Work in progress.