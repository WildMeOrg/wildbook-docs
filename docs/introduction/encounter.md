# Encounter

In Wildbook, an Encounter is the foundation of the software. Encounters provide a reference to a time and location where a single animal was seen.

## Navigating to an Encounter Page

To see Encounter information, you must be signed into Wildbook. Once you've signed in, you can use **Search** > **Encounters** to filter Encounters or you can use **My Data** > **My Encounters** to see all of the Encounters assigned to you.

There are two [data entry methods](data-entry.md) for uploading Encounters: upload a single encounter from the [Report an Encounter](../data/report-encounter.md) page and upload multiple Encounters in a [Bulk Import](../data/bulk-import-beta.md).

## Encounter Page Format

The Encounter page has two views: Overview and More Details. The Encounter ID, Encounter workflow state, Contact Information, and Encounter History will persist between views. 

For each of the following sections, click the pencil icon to make changes.

If you see fields that are not covered on this page, they are custom to your Wildbook. Contact your administrator or [Wildbook support](https://community.wildme.org/) for any questions about how to use them.

### Date

At minimum, the year must be provided for the Encounter to be saved.

#### Encounter Date

The date and time the animal in the photo was seen. Must adhere to ISO format: **YYYY-MM-DD HH:mm**

#### Verbatim Event Date

A free-text field to describe the Encounter Date. This field is searchable, but is not used in finding matches.

### Identity

Identity tells us if an Encounter has been identified as a [Marked Individual](../introduction/marked-individual.md).

#### Matched by

Describes how the Encounter was identified. The options are:

* **Unmatched first encounter**: No matches were found in the Wildbook, making this a new individual. 
* **Visual Inspection**: Someone compared the pictures between two Encounters and determined they are the same individual.
* **Pattern Match**: Wildbook suggested a match candidate and the animal was determined to be the same individual.

#### Individual ID

If the Encounter is of an individual that does not exist in the current Wildbook, you should enter a unique ID. This ID needs to be distinct from any Individual ID in your catalog that currently exists. When you've entered the ID, click **Create** to confirm the value and then click **Save**.

If you have determined the Encounter is of an existing individual, type the individual ID you want to associate the Encounter with. A drop-down menu will display a list of all matching individuals. Select from the list then click **Save**.

To remove an Encounter from an individual, click **Unassign Individual**.

#### Alternate ID

If there is an alternative ID used to identify this animal, such as in a historical catalogue, enter it here. Once you've entered the ID, click **Save**.

#### Sighting ID (formerly "Occurrence ID")

Sighting IDs are automatically generated unless they are specified in a Bulk Import. A Sighting is made up of multiple Encounters. You may want to edit the default Sighting ID to more easily sort the Encounters that were recorded in a specific place and time. Click **Remove from Sighting** to remove your Encounter from the current ID and enter a new one. Click **Create** to confirm the value and then click **Save**.

If you want to add the Encounter to an existing Sighting ID, type the ID and a drop-down menu will display a list of all matching Sightings. Select from the list then click **Save**.

### Metadata

Displays the Encounter ID, the date the Encounter was created in Wildbook, last edited date, whether the Encounter was part of a bulk import, and the assigned  user.

#### Assigned user

Use the menu to select from a list of Wildbook users and assign that user as owner of the Encounter. Click **Save** to confirm the selection.

### Location

A location ID or coordinates must be set in order to save an Encounter. This information is used to determine match candidates, as well as identify where an Encounter took place.

#### Location

Provide a description of the location where the Encounter occurred. Click **Save**. 
* *Note: This field is searchable, but is not used to find matches. This is valuable if there is a set of landmarks that have multiple names, or if a citizen scientist submits an Encounter and are unsure of exact location.*

#### Location ID

Select from a list of location IDs ("study sites") where the Encounter occurred. Click **Save**. 

* *Note: This list is hierarchical and determined by the administrator of the Wildbook. We recommend no more than 5 hierarchical layers of locations. Reach out to your administrators or to [Wildbook support](https://community.wildme.org/) for configuration assistance)*

#### Country

Select from a list of countries where the Encounter occurred. Click **Save**.

#### GPS Coordinates

Use the map or text fields to enter the GPS coordinates where the Encounter occurred in decimal format. Click **Save**. 

### Delete Encounter

Click **Delete Encounter** to remove an Encounter from the database. A confirmation window will display; click OK to confirm. 

### Attributes

Encounters can also have these important attributes.

1. **Taxonomy**: Use the drop-down menu to select from available species. The Taxonomy affects how Annotations for the Encounter are processed through the [Image Analysis Pipeline](image-analysis-pipeline.md).
2. **Living Status**: Use the drop-down menu to select the animal's living status at the time of the Encounter. 
3. **Sex**: Use the drop-down menu to select the animal's sex. 
4. **Distinguishing Scar**: Describes any scarring that could be useful in making a visual comparison between animals.
5. **Behavior**: Provide a description of the animal's behavior. 
6. **Group Role**: Provide a description of the role the animal has within their group during this Encounter. 
* *Note: If this entry matches the pre-defined behavior list, you can use the search filter for the behavior on Encounter Search page.
7. **Patterning Code**: Use the drop-down menu to select the animal's patterning code.
8. **Life Stage**: Use the drop-down menu to select the life stage for the animal. Life stage is configured in the commonConfiguration.properties file. [See Configuration for more information.](../specifications-and-system-requirements/system-configuration.md) To update this field, contact Wildbook support for assistance.
9. **Observation comments**: Any information that you want to associate with the Encounter. 

Click **Save** to record your changes.

### Encounter State

The Encounter workflow state is defined as:

* **Unapproved** - An Encounter that has not been reviewed and accepted by a user. This is the default state for Encounters submitted using the  [Report an Encounter](../data/report-encounter.md) page.
* **Approved** - An Encounter that has been reviewed and accepted by a user. This is the default state for Encounters submitted using Bulk Import.
* **Unidentifiable** - An Encounter that has been reviewed and determined to be unusable for identification, but should remain in the system. Selecting your state will save it.

### Contact Information (People icon)

* **Managing Researcher**: This is the Wildbook user that's the Encounter owner. Only users with the Admin or Org admin role can edit this field. 
* **Submitter**: This is the researcher or citizen scientist that uploaded the Encounter. 
* **Photographer**: This is the photographer of the images on the Encounter. 
* **Add submitter by email address**, **Add photographer by email address**, and **Add others to notify by email address** all operate in the same manner.

To add someone to one of these sections, click the **Add People** button, enter their email address, select a role from the Role menu, and click **Save**.
To remove someone from one of these sections, click the **Trash** icon next to their information.

### Encounter History (Clock icon)

This contains a log of all modifications made to the Encounter since its upload.

### Images

The image gallery displays the annotations associated with an Encounter. An image will appear multiple times with different annotations highlighted to indicate different animals or animal parts detected.

Click on an annotation from your image to select it. Use the **Trash** icon to delete the annotation or the **Pencil** icon to edit or reposition the existing annotation.

#### Match Results

After an annotation has completed identification, click this button to see the match page and begin the [matching process](..data/matching-process.md).

#### Visual Matcher

Visual Matcher is a separate, limited user interface to support visual matching of Encounters without using computer vision. It was developed to support giant manta matching before computer vision was available. Some users may find it helpful for reviewing matches for other species.

#### New Match

This opens a workflow to refine the filters to find match candidates. You can refine the filters to inlcude multiple location IDs, search for candidates in the Wildbook database or only your own data, and select additional algorithms if they are available for your species.

#### Add Annotation

If detection missed annotating an animal, you can click this to add a [manual annotation](../data/manual-annotation-beta.md). 

#### Add Image

You can add additional images to your Encounter here. Detection is not automatically run on these images. Select the image form the gallery and click the **Add Annotation** button to manually annotate it.

##### Keywords

Keywords can be added to an image by clicking on an image to expland it. To select a keyword:

1. Click on an image.
2. Click the **+ Add keyword** button.
3. Select an existing keyword from the **Select Keyword** drop-down menu or add a new one in the **Add New Keyword** field. Click **Add** to save.
4. Use the **Select Labeled Keyword** drop-down menu to select one of the predefined labels.
5. From the subsequent value drop-down menu, select the desired value. Click **Add** to save.

Once selected, the keyword appears on the image and the labeled keyword will display in the format "label: value".

Labeled keywords are set in the [commonConfiguration.properties file](../specifications-and-system-requirements/system-configuration.md); reach out to your admin or to [Wildbook support](https://community.wildme.org) for configuration assistance. [See Configuration for more information.](../specifications-and-system-requirements/system-configuration.md)

Keywords are not automatically curated or checked against existing keywords, so you can create duplicate keywords easily. Admins can manage keywords from the **Administer** > **Photo Keywords** menu.

##### Delete Image

Click this button to remove the selected image from the Encounter. 

## More Details

### Tracking and Measurements

#### Tracking

Tracking is used to document tags seen during an Encounter.

* **Metal Tags**: Provides a space for a left or right-side tag.
* **Acoustic Tags**: Provides information for sound-emitting aquatic tags, including searial number and ID.
* **Satellite Tags**: Provides information associated with tagging done using satellites, including the name of the satellite, serial number, and Argos PTT.

Click **Save** after the tag information is entered.

#### Measurements

Measurements are used to track numeric information associated with an Encounter. These are set in the commonConfiguration.properties file. [See Configuration for more information.](../specifications-and-system-requirements/system-configuration.md) To request measurements be added, [contact Wildbook support for assistance](https://community.wildme.org).

Click **Save** after the measurements are entered.

### Biological Samples

* To enter a biological sample:

1. Click **Add biological sample**.
2. Enter the information you have associated with the sample. The only required information is the **Sample ID**.
3. Click **Set** to finalize the sample and its associated metadata.

* Use the link on the confirmation page to navigate back to the Encounter if you want to enter analysis information, including:

1. **Haplotype**
2. **Microsatellite markers**
3. **Genetic sex determination**
4. **Biological/chemical measurement**

* Open the appropriate analysis, then click **Set** to save the information you add.
* Click the **X** button under **Remove** to remove an entire sample.

### Projects

To add an  to an existing [project](..data/projects.md), select the project name from the drop-down menu or begin typing the project name in the search field and select it when it appears. Click **Add Project**.
