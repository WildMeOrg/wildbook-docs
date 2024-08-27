# Bulk Import (beta)

To allow for the integration and import of legacy data as well as batched volumes of data, Wildbook provides a system for uploading a large amount of data called **Bulk Import**. Bulk Import allows users with login privileges to provide photos and related metadata *en masse* (e.g., date, location, species, etc.).

```{note}
This functionality is in beta, but considered largely stable. Any substantial changes will be reported before they take place.
```

There are two pieces of input required for a bulk import:

* Photo archive in a local file system
* Excel spreadsheet linking photos to metadata

In setting up your bulk imports, ensure that each import has 200 Encounters or less.

## Photo Archive Set-up

On your computer, organize the photos you'd like to upload into a single folder.

1. Create a folder.
2. Move all images you intend to upload to the folder.
3. Ensure that all file names are unique from one another.

If you have file names that are the same, either *rename the duplicates or upload the duplicates in a separate batch*.
Remember, the image names must correspond exactly to the `"Encounter.MediaAsset"` entries in your Wildbook Standard Format spreadsheet. Special characters are removed from file names. *(Recommendation: Remove special characters before uploading to check for potential collisions. Your file names should only include letters from the English alphabet, 0-9, period, and space.)*

## Spreadsheet Set-up

In the header of an Excel (.xlsx) file, create a column for each field you want to upload to Wildbook. [See Fields Available for a list of supported fields.](#fields-available) This must include at least:

1. **Location Reference**: Encounter.verbatimLocality, Encounter.locationID, and/or Encounter.decimalLatitude and Encounter.decimalLongitude
2. **Date and Time Reference:** Encounter.year, Encounter.month, Encounter.day, etc. *(Note: At a minimum, include the year)*
3. **Photograph reference**: Encounter.MediaAsset*0*
4. **Taxonomy**: Encounter.genus and Encounter.specificEpithet

*(Note: All other fields are optional.)* Because this flow is only accessible to authorized users, the Encounters are uploaded as approved Encounters if **Encounter.state** is not otherwise set. Here are important guidelines for preparing your spreadsheet:

* **Determine which columns you have data for** (see [Fields Available](#fields-available)).
    It is OK to add, remove, and reorder columns as needed from the provided list. You can create your own version of our spreadsheet as long as you do not change the header names. Fields without data should be removed from your spreadsheet prior to importing it.
* **Fill out each line for a single** [Encounter](../introduction/encounter.md).
    If an encounter is associated with a [Sighting](../introduction/sighting.md), include the needed information for the Sighting on at least one line of an associated Encounter.
* If using any of the Occurrence fields for Sightings, ensure that each Encounter is linked with a common value in the Occurrence.occurrenceID column.
* Verify the following fields match exactly with what exists in the system:
    * **Encounter.locationID** - Must match the location as shown in the Location ID menu of the Report an Encounter page.
    * **Encounter.submitterID** - Your Wildbook account's username to ensure the encounter is credited to you. This is case-sensitive and must match how it appears in your account page.
    * **Encounter.mediaAsset0** - This is the exact file name of each image of the Encounter. Start numbering at 0, and for each additional image, increment by 1 (0, 1, 2, 3, etc.).

### Spreadsheet Templates by Use Case

Here are example Bulk Import Excel spreadsheet templates:

1. [Minimum import](../assets/templates/minimum_import.xlsx)
2. [Individual catalog](../assets/templates/individual_catalog_import.xlsx)
3. [Sighting import](../assets/templates/sighting_import.xlsx)

## Uploading Photos for Bulk Imports

When you have finished preparations, navigate to your Wildbook's Bulk Import page (import/instructions.jsp) and begin the guided walk-through.

1. Select **Upload Photos**.
2. Browse to your photo directory and select **Upload**.
3. Select **Begin Upload** to be taken to the photo review page. At this point, these images are uploaded to the platform and available.
4. Review that all photos you have uploaded are available in the import. If they are, select **Accept** and move on.
5. Browse to your spreadsheet and select **Open**.
6. Select **Begin Upload** to be taken to the import overview.
7. Review the data preview for data integrity.

```{note}
The system will verify the data in the spreadsheet against ALL images you have in the system, not only the ones you are currently uploading. Review the online data integrity report carefully before initiating an upload.
```

If everything looks as expected, select **Commit these results** and confirm that you want to import all data.

## Bulk Import Matching Process

After uploading a bulk import, you can send imported Encounters through the [Image Analysis Pipeline](../introduction/image-analysis-pipeline.md) if the pipeline is configured for the imported species.
Once the import completes, you can take these actions:

### Send to Detection (No Identification)

The MediaAssets you upload are sent to Detection, where Annotations are added for each animal found by the [Image Analysis Pipeline](../introduction/image-analysis-pipeline.md). Identification can be run later individually through each Encounter page. See [Matching Process](matching-process.md) for more information.

### Send to Identification

This option will appear after your images have been sent to Detection. The MediaAssets you have uploaded are sent through Detection, and any found Annotations are sent on to the Identification process. Select which locations to process Identification for and **Send to Identification**.

Bulk Detection and Identification can very significantly impact the Wildbook Image Analysis queue machine learning jobs. Other users can expect slowdowns waiting for Bulk Detection and ID jobs to finish.

## Deleting a Bulk Import

Mistakes happen. If you find systematic problems in the data of a Bulk Import job, you can return to the Bulk Import log page and click **Delete ImportTask** at the bottom, which will remove all of the imported data. You can now fix your data and reimport to Wildbook.

## Fields Available

The most commonly-used fields are listed in the table below.

| Name | Type | Example Value | Description |
| ---- | ---- | ------------- | ----------- |
| MarkedIndividual.individualID | V_WString | Lion045 | PrimaryKey. While Wildbook assigns unique user IDs to MarkedIndividuals, this field becomes the default display name for the MarkedIndividual. <br>Duplicate of Encounter.individualID. <br>We recommend using this field instead of Encounter.individualID. |
| Encounter.individualID | V_WString | Lion045 | Duplicate of MarkedIndividual.individualID. |
| Encounter.verbatimLocality | V_WString | Saw this about five minutes into our tour near mile marker 5, somewhere in Tanzania. | Descriptive string to reference location. No constraints on what is entered, but is not used for analysis. |
| Encounter.locationID | V_WString | Zone 5, Botswana | Hierarchical list of study sites. Allows for consistency and controlled granularity of location input. **Must match the location as shown in the Location ID menu of the Report an Encounter page.** |
| Encounter.decimalLatitude | Double | -35.46 | Enter latitude coordinates using decimals instead of degrees, minutes, and seconds (DMS). The first encounter of any setting will also set the decimal latitude at the sighting level. |
| Encounter.decimalLongitude | Double | 54.678 | Enter longitude coordinates using decimals instead of degrees, minutes, and seconds (DMS). The first encounter of any setting will also set the decimal latitude at the sighting level. |
| Encounter.year | Int32 | 2020 | For encounter date information, add what you have to the most precise accuracy. Storing the segments separately allows general dates such as "June 2014"; we do not store seconds or milliseconds for an encounter's date information, so there are no fields to allow the input of those values. Enter a 4 digit number. |
| Encounter.month | Int32 | 8 | Enter a number 1-12 corresponding with the the month of the encounter. |
| Encounter.day | Int32 | 24 | Enter a number 1-31 corresponding with the day of the month. |
| Encounter.mediaAsset0 | String | 20180905/12345.jpg | Must be entered exactly: relative path to the photo from the position of the imported spreadsheet on the file system. Values from 0 to infinity are iterated until a sequence value is not found. |
| Encounter.genus | V_WString | Panthera | Enter an option from the Taxonomy drop-down menu. This should be the first of the two phrases. This entry must begin with a capital letter. **These values are case-sensitive.** If entered incorrectly, Taxonomy will display as "Not Available". |
| Encounter.specificEpithet | V_WString | pardus | Enter an option from the Taxonomy drop-down menu. This should be the second of the two phrases. This entry must begin with a lowercase letter. **These values are case-sensitive.** If entered incorrectly, Taxonomy will display as "Not Available". |
| Encounter.submitterID | V_WString | tmcnutt | Add submitter's username in Wildbook. **These values are case-sensitive.** |
| Encounter.state | V_WString | approved<br>unapproved<br>unidentifiable | The curation state of this Encounter. Default value if left blank is "approved". <br>Uncurated data should be imported as "unapproved". <br>Encounters without photos should be imported as "unidentifiable". |

The following fields can be included when uploading an Encounter. Review the description of the field and validate that it is in use in your system (meaning if you are on a terrestrial Wildbook, you will likely not use Encounter.depth).

| Name | Type | Example Value | Description |
| ---- | ---- | ------------- | ----------- |
| Encounter.alternateID | V_WString | Bitey | Adds an Alternate ID to the Identity section of the Encounter. |
| Encounter.behavior | V_WString | feeding | List of behaviors commonly observed in the species. |
| Encounter.country | V_WString | Botswana | Country where the Encounter took place. |
| Encounter.dateInMilliseconds | Int64 | 1589554848 | Skip other Encounter date fields if you have a precise date and time (milliseconds since epoch---the standard computer format for date and times). Format is a large integer like 1516685992499. |
| Encounter.distinguishingScar | V_WString | left body | Description of any highly-identifiable markings/scarring that help with visual Identificaton. |
| Encounter.groupRole | V_WString | escort male | Not commonly used. Largely used for point-in-time observations of role rather than longer-term observations. |
| Encounter.hour | Int32 | 11 | Enter a number 1-24, 24 corresponding with midnight. |
| Encounter.keyword0 | String | left strange marking | Applies a keyword to a mediaAsset; the number of Encounter.keyword(X) should correspond to number of Encounter.mediaAsset(X). |
| Encounter.mediaAsset0.keywords | String | left strange marking_scar on body_ProfilePhoto | Underscore-delimited list of keywords to be associated with the MediaAsset. Can be used for one or many keywords. Values from 0 to infinity are iterated until a sequence value is not found. |
| Encounter.lifeStage | V_WString | juvenile | List of potential life stages. Standards are "adult", "juvenile", and "unknown". |
| Encounter.livingStatus | V_WString |  | Accepted values: "alive" or "dead" |
| Encounter.measurement0 | String | 5 | Supported column headings are numeric. Values from 0 to infinity are iterated until a sequence value is not found. |
| Encounter.mediaAsset0.[label name] | String | [label name]: flukeType, value: dorsal | Name a column for a labeled keyword and provide an associated value for each encounter. Labeled keyword names can be found in the keyword drop-down menu on a MediaAsset. Labeled keywords can be defined in the commonConfiguration.properties file. |
| Encounter.minutes | V_WString | 35 | Enter a number 1-60. |
| Encounter.occurrenceID | V_WString | BPCT_20190825_1 | A unique code that links encounters across a single sighting. Helpful if you can cross-reference to your records. If you enter an ID that exists in the system, the encounter will be associated with the existing sighting. If you enter a new and unique ID or if you leave the field blank, a new sighting will be created and the encounter associated with the newly created sighting. Restricted to Latin alphanumeric characters (a-z, A-Z, 0-9), - and _. <br>Duplicate of Occurrence.occurrenceID. We recommend using this field instead of Occurrence.occurrenceID. |
| Occurrence.occurrenceID | V_WString |  | Duplicate of Encounter.occurrenceID |
| Encounter.researcherComments | V_WString | We also took a separate video observation. | Unconstrained field for general notes regarding the specific encounter (single annotation and related metadata). <br>Leaves comments on the Encounter page under Metadata > Audit Trail. |
| Encounter.occurrenceRemarks | V_WString | We saw this pack while driving through the forest. | Leaves comments on the Encounter page under Attributes > Additional Comments. Use this field if you need the comments to persist on any cloned Encounters. |
| Occurrence.comments | V_WString |  | Leaves comments on the Sighting/Occurrence ID page. |
| Encounter.otherCatalogNumbers | V_WString | fieldObs12 | Links the Encounter to other numbers, such as a field encounter number for the day. Limited use in Wildbook. |
| Encounter.patterningCode | V_WString | tan | A code that defines some standardized feature of body coloring, such as how humpback whale flukes are categorized 1-5 (light to dark) or wild dogs are categorized by general body color (e.g., tan). This field is stored on the back-end and displayed without UI editing capability. |
| Encounter.informOther0.affiliation | String | BPCT | Unconstrained string to indicate an affiliation to inform. Values from 0 to infinity are iterated until a sequence value is not found. **Does not save unless Encounter.informOther0.emailAddress is also reported.** |
| Encounter.informOther0.emailAddress | String | [joe@joe.com](mailto:joe@joe.com) | Add the email address of someone else to inform of Encounter updates. Values from 0 to infinity are iterated until a sequence value is not found. Links to the email address of a Wildbook account. |
| Encounter.informOther0.fullName | String | Joe Smith | Provide the full name of someone else to inform of Encounter updates. Values from 0 to infinity are iterated until a sequence value is not found. **Does not save unless Encounter.informOther0.emailAddress is also reported.** |
| Encounter.photographer0.affiliation | String | BPCT | Unconstrained string to list an organization the photographer is associated with. When the photographer is an existing Wildbook user, only include the *Encounter.photographer0.emailAddress* field. Whatever is in *Encounter.photographer0.affiliation* will be ignored in favor of what the system associates with the user's email address. Values from 0 to infinity are iterated until a sequence value is not found. **Does not save unless photographer0.emailAddress is also reported.** |
| Encounter.photographer0.emailAddress | String | [joe@joe.com](mailto:joe@joe.com) | Add the email address of the photographer. Values from 0 to infinity are iterated until a sequence value is not found. Links to the email address of a Wildbook account. |
| Encounter.photographer0.fullName | String | Joe Smith | Provide the full name of the photographer. When the photographer is an existing Wildbook user, only include the *Encounter.photographer0.emailAddress* field. Whatever is in *Encounter.photographer0.fullName* will be ignored in favor of what the system associates with the user's email address. Values from 0 to infinity are iterated until a sequence value is not found. **Does not save unless photographer0.emailAddress is also reported.** |
| Encounter.submitter0.affiliation | String | Joe's Safaris | Unconstrained string to list the submitter's organization. Values  from 0 to infinity are iterated until a sequence value is not found. **Does** **not save** **unless** **submitter0.emailAddress** **is also reported.** |
| Encounter.submitter0.emailAddress | String | joe@joe.com | Add the email address of the submitter. Values from 0 to infinity are iterated until a sequence value is not found. Links to the email address of a Wildbook account. |
| Encounter.submitter0.fullName | String | Joe Smith | Provide the full name of the submitter. Values from 0 to infinity are iterated until a sequence value is not found. **Does not save unless submitter0.emailAddress is also reported.** |
| Encounter.project0.projectIdPrefix | String | Cen20- | The prefix used when assigning project IDs to encounters. **These values are case-sensitive.** Values from 0 to infinity are iterated until a sequence value is not found, allowing you to put encounters into multiple projects. Required for imports into existing and new projects. |
| Encounter.project0.researchProjectName | String | Census 2020 | The project's name. **These** **values** **are** **case-sensitive.** Values from 0 to infinity are iterated until a sequence value is not found, allowing you to put encounters into multiple projects. Required for imports into both existing and new projects. |
| Encounter.project0.ownerUsername | String | censusadmin | The username of the person who should manage the project. **These values are case-sensitive.** Required for imports into new projects only. To prevent caching or threading issues, associate the new owner with all encounters in the spreadsheet that are going into the new project. |
| Encounter.mediaAsset0.quality | String | An integer value 0 to 4. | Estimated quality of Encounter.mediaAsset0. Values from 0 to infinity are iterated until a sequence value is not found. |
| Encounter.sex | V_WString | male | Focus on values: "male", "female", and "unknown". |
| MarkedIndividual.nickname | V_WString | Barry the Slow Lion | Enter a name that can be more easily referenced; does not override ID. |
| Membership.role | V_WString | alpha | Role as a member of a social unit (SocialUnit.socialUnitName). |
| Occurrence.bestGroupSizeEstimate | Double | 5 | Researcher-provided estimate of group size. |
| Occurrence.effortCode | Double |  | Categorized set of values denoting the amount of effort that went into collecting data for a sighting. |
| Occurrence.fieldStudySite | V_WString |  | String for location. Site names should be recognizable. |
| Occurrence.fieldSurveyCode | V_WString |  | String to be associated with a given survey. |
| Occurrence.groupBehavior | V_WString |  | String for description of observed behavior. |
| Occurrence.groupComposition | V_WString |  | String for description of what animals are observed and their potential relationships. |
| Occurrence.groupSize | V_WString |  | String for description of group size. |
| Occurrence.humanActivityNearby | V_WString |  | Description of any activity known to occur in the area. |
| Occurrence.individualCount | Int32 |  | Number of Individuals counted manually in the sighting. |
| Occurrence.initialCue | V_WString |  | Text value denoting what signaled attention to the Sighting. Stored in the database only. No UI. |
| Occurrence.maxGroupSizeEstimate | Int32 |  | Researcher-provided estimate of upper limit group size. |
| Occurrence.millis | Int64 |  | Time of the Sighting in milliseconds since Epoch; typically originates from hardware used to capture image. |
| Occurrence.minGroupSizeEstimate | Int32 |  | Researcher-provided estimate of lower limit group size. |
| Occurrence.numAdults | Int32 |  | Researcher-provided determination of number of adults |
| Occurrence.numAdultFemales | Int32 |  | Researcher-provided determination of number of adult females. |
| Occurrence.numAdultMales | Int32 |  | Researcher-provided determination of number of adult males. |
| Occurrence.numCalves | Int32 |  | Researcher-provided determination of number of calves. Can be used for any infant stage of a species. |
| Occurrence.numJuveniles | Int32 |  | Researcher-provided determination of number of juveniles. |
| Occurrence.numSubAdults | Int32 |  | Researcher-provided determination of number of subadults. |
| Occurrence.numSubFemales | Int32 |  | Researcher-provided determination of number of subadult females. |
| Occurrence.numSubMales | Int32 |  | Researcher-provided determination of number of subadult males. |
| Occurrence.observer | String |  | The name of the observing researcher. |
| Occurrence.transectName | V_WString |  | Name of the transect that logged the sighting. Stored in the database only. |
| Occurrence.visibilityIndex | Double |  | Indexed values of the visibility during the time of the sighting. Stored in the database only. |
| SatelliteTag.serialNumber | V_WString | 12345 | Serial number. Reference only |
| SocialUnit.socialUnitName | V_WString | G Pack | PrimaryKey. Unique to each social unit. |
| SurveyTrack.vesselID | V_WString | Car 45 | User-provided identifier of ship used during survey. |
| survey.vessel | V_WString | Car 45 | Duplicate of SurveyTrack.vesselID. |
| TissueSample.sampleID | V_WString | 12345 | ID of the tissue sample taken during this Encounter. Only one TissueSample can be imported per Encounter. |
| SexAnalysis.sex | V_WString | female | Determination from a genetic analysis of the individual's sex. Results from the analysis of a tissue sample taken during the same encounter. **A corresponding TissueSample.sampleID entry is required for this field to import.** |
| MitochondrialDNAAnalysis.haplotype | V_WString | "A+" | Determination from a genetic analysis of the individual's haplotype. Results from analysis of a tissue sample taken during the same encounter. **A corresponding TissueSample.sampleID entry is required for this field to import.** |
| MicrosatelliteMarkersAnalysis.alleleNames <br>MicrosatelliteMarkersAnalysis.alleles0 <br>MicrosatelliteMarkersAnalysis.alleles1 | V_WString | alleleNames: "EV1,<br>EV5,EV94,GT23,<br>GT575,rw410,<br>464465,GATA417,<br>SW13,EV37,<br>EV14,FCB1,SW19" <br>alleles0: "120,154,<br>201,79,131,177,140,<br>182,158,231,125,<br>121,123" <br>alleles1: "120,158,<br>209,85,135,183,<br>140,186,160,237,<br>145,129,147" | Determination from a genetic analysis of the Individual's genotype. Results from analysis of a tissue sample taken during the same Encounter. **A corresponding** **TissueSample.sampleID** **entry is** **required** **for** **this field to import**. These three fields must all be present and have the exact same number of values as separated by commas. |
| survey.id | String |  | Record number of the survey performed. |

The following fields are for aquatic use.

| Name | Type | Example Value | Description |
| ---- | ---- | ------------- | ----------- |
| Encounter.depth | Double | 35 | Depth of water where the Encounter occurred. Aquatic-only. |
| Occurrence.bearing | Double | 45 | Value to work with decimalLatitude, decimalLongitude, and distance of Sighting. Typically aquatic-only. |
| Occurrence.distance | Double |  | Value to work with decimalLatitude, decimalLongitude, and bearing of Sighting. |
| Occurrence.seaState | V_WString |  | Description of water conditions during the Sighting. Aquatic-only. |
| Occurrence.seaSurfaceTemp | Double |  | Water temperature in degrees celsius. Aquatic-only. |
| Occurrence.swellHeight | Double |  | Height of any waves in the area in meters. Aquatic-only. |
| Occurrence.transectBearing | Double |  | Numeric value of the bearing from the observation vessel to the observed sighting. Stored in database only. Aquatic-only. |

## Reviewing Bulk Imports

You can review your Bulk Imports by selecting **Bulk Import Logs** from the **Administer** menu. If you have admin or orgAdmin roles on your User account, you may see additional logs for other users as well.
