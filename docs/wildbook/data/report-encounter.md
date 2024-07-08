# Report an encounter

Under the **Submit** menu in Wildbook, there are two options: **[Report an encounter](https://docs.wildme.org/product-docs/en/wildbook/data/report-an-encounter/)** and **[Bulk Import](https://docs.wildme.org/product-docs/en/wildbook/data/bulk-import-beta/)**. Here we present the single Encounter reporting method (**Report an Encounter**), which allows for data entry in a simple, web-based form. This form supports two use cases:

## Reporting an Encounter

Complete the following steps to successfully submit anEencounter. These fields are the minimum requirements. Any additional data provided can assist with Detection and Identification, but will not prevent a user from uploading their Encounter.

1. Access your Wildbook homepage.
2. From the **Submit** menu, select **Report an Encounter**.
3. Under **Footage**, drag a file or click to add images.
4. Under **Date** and **Location**, enter a date in the Encounter date field. Use an ISO format: ***(YYYY-MM-DD HH:mm)***.
5. Under **Encounter location**, provide one or more of the following:
    a. **Where were you?**: Provide a freeform description of where you saw this animal.
    b. **Was this one of our location IDs?**: Is this a formal study site (a.k.a. "location ID") defined in this Wildbook? If you don't know, leave it blank. If a location ID is selected and [Wildbook Image Analysis](https://docs.wildme.org/product-docs/en/wildbook/introduction/image-analysis-pipeline/) is configured for this species, the Identification matching phase will only try to match this Encounter's Annotations against other Annotations from this same area.
    c. **GPS Latitude/Longtitude**: By either manual entry or map selection, indicate precisely where this Encounter occurred.
6. Under **About You**, enter your name in the **Name** field and email in the **Email** field.
7. Click **Send Encounter Report**.

Your Encounter is now available as an unapproved Encounter.

### Reporting an Encounter of a single animal with one or more photos shown of only that Individual.

It is assumed that all photos contain only the same animal, satisfying the definition of an Encounter being one animal at a location and point in time. This method is best used for more solitary animals (e.g., whale sharks).

### Reporting an Encounter of multiple Individuals, with only one photo submitted.

If machine learning Detection has been configured for the submitted species, it will process the submitted photo and dynamically clone new encounters each time, Annotations are found. This method allows for each resulting Encounter to contain all of the reported metadata (location, date, etc.) but only one Annotation of only one Individual, satisfying the definition of an Encounter being one animal at a location and point in time.

### Additional Fields

* **Organization**: Allows for an association between you, your data, and your organization
* **Project**: If the picture was taken as part of a specific effort, such as a census event
* **Additional** **Comments**: Any information that does not seem relevant in another field
* **Species**: A list of species supported on the platform
* **Sex**: Indication of if the photographed animal is male, female, or unidentified
* **Observed Behavior**: Description of behavior that occurred during the Encounter, such as environment interactions or interactions between two animals
* **Noticeable Scarring**: Description of scarring that can be used to identify the Animal
* **Life stage**: A list of age groupings that can be applied, such as adult or juvenile

If you are submitting as a signed-in user, you will also have the following options:

* **Status**: If the animal is alive or dead
* **Alternate ID**: Allows for entry of any other IDs that may be used for finding the picture, such as a catalogue number from your records
* **Sighting ID**: A reference number for a collection of Encounters that occurred at the same time
* **Other Email Addresses**: Allows for a list of email addresses, separated by commas. The emails provided will receive updates regarding the Encounter as information is added to the platform, such as resightings or association with a marked Individual.

## Fields Not Listed

You may see a number of fields on your Wildbook that are not listed here. Wildbook allows for some degree of customization, which means that options may be available that are specific to your Wildbook. If you have questions about these fields, post to the [Wildbook Community](https://community.wildme.org) or contact the platform managers identified under the **Learn** tab.