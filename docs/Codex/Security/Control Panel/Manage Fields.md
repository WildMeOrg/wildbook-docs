# Configure Default Fields

Use the header menu (triangle button in the top right) to select **Control panel** from the drop-down menu. From this page, click on the **MANAGE FIELDS** button.

## Configurable Default Fields

The first table on the **Manage fields** page is the **Configurable default fields** table. These fields are automatically preselected by Codex and can be customized.

## Table Headings

* **Label:** Codex assigns four default labels to a media asset which are **Species**, **Region**, **Social groups**, and **Relationship**.
* **Type:** States the type of interaction, either an **Encounter**, **Individual**, or a **Sighting**.
* **Actions:** Click on the **pencil icon** under actions to edit any of the **Label** fields.

## Species

1. Click on the pencil icon at the end of the **Species** row.
2. Select a species using the Species drop-down menu. Only species that we have training data are displayed here.
3. Enter an **ID Prefix** for the species. This is the prefix that will appear as part of an animal's Codex ID.
4. Click the **FINISH** button to save any changes.

## Regions

1. Click the **pencil icon** at the end of the **Region** row to edit the field. Click the **ADD REGION** button to add a new location. A field will appear for you to type in the new region.
2. Each listed region has a **+ icon** next to it. Click on this to organize regions into a hierarchy. Regions staggered towards the left are larger areas, such as countries (e.g., South Africa). Regions staggered towards the right are smaller areas within the larger region (e.g., KwaZulu-Natal).
3. Each listed region has a checkbox, default checked on. De-select a region if the region is too big to be useful as a search term, but is useful in hierarchy searches. (ex: Atlantic Ocean can be useful when searching for specific coastal sites, but would not be useful as a data segment.)
4. Each listed region has a delete button. Use this to remove the region from the system. Note that this will be blocked if the region is actively in use.
5. Click the **SAVE** button to save any changes.

## Relationships

1. Click on the **pencil icon** at the end of the **Relationship** row to edit the relationship fields. The listed fields will appear when creating relationships on an individual's page.
2. Click the **ADD TYPE** button to add a type of relationship (e.g., familial or social grouping).
3. Click the **+** **icon** next to each relationship type to add a specific role within that type (e.g., mother or alpha).
4. Click the **trash can icon** to delete any relationship types or roles.
5. Click the **SAVE** button to save any changes.

## Social Groups

1. The listed social group roles appear on the drop-down menu for any social groups made on an individual's page.
2. Click the **ADD ROLE** button to create new social group roles that will be available to choose from on an individual’s page. Click the trash can icon next to any role to delete it.
3. Click the **Allow multiple of this role** toggle button if you want to allow more than one individual to assume the same role.
4. Click the yellow **SAVE** button to save any changes you have made.

***

## Configure Custom Fields

Editing custom fields allows for the maintenance of all metadata, for both recent and historical catalogs. There are three types of customizable fields: **Individual**, **Sighting**, and **Encounter**.

* **Individual:** Individuals are animals that are recorded and identified already within the Codex platform.
* **Sighting:** Sightings are instances of a human interacting with one or more animals at a specific location and time.
* **Encounter:** Encounters are instances of a human interacting with a *single animal* at a specific location and time.

***

## **Field Categories**

**Field categories** is the second table on the **Manage fields** page. **Label** is customizable, it helps organize fields on the report sighting form. **Type** is how to categorize **Label**, it can either be **sighting fields**, **encounter fields**, or **individual fields**.

1. Click the **ADD NEW** button.
2. A pop-up window will appear with spaces for **Label** and a drop-down menu for **Type**.
3. You can customize **Label**.
4. Based on what you enter on **Label**, you need to select **sighting fields**, **encounter fields**, or **individual fields** on the drop-down menu for **Type**.
5. Select the **SAVE** button.

***

## Create Custom Fields

Codex users with the Admin role can create new custom fields in Codex. At a minimum you will need a field name, a description, and set values.

### Manage Fields

Go to the **Actions** menu and click on **Control Panel**, then click on **Manage Fields**.

* **Field categories** organize fields on the sighting submission form. You may need to create a new field category before you can add a new field. *Note that **Field categories** cannot be changed.*
* **Custom individual fields** create a new [Metadata](https://docs.wildme.org/product-docs/en/codex/data/individual-page/#metadata-for-your-individual) entry on the [Individual page](https://docs.wildme.org/product-docs/en/codex/data/individual-page/).
* **Custom sighting fields** create a new [Metadata](https://docs.wildme.org/product-docs/en/codex/data/sighting-page/#metadata) entry on the [Sighting page](https://docs.wildme.org/product-docs/en/codex/data/sighting-page/).

### Configuration

1. **Database field (required):** This should have no spaces and be intuitive. If you're adding a new custom individual field include "indiv", for a new custom sighting field, use "sgt", for a new custom encounter field, use "enc". For example: “indiv\_with\_pup".
2. **Type (required):** Choose an option from the menu (text, date, dropdown, etc.). *Note that once you save all the changes you made, **Type** cannot be edited anymore.*
3. **Required:** Try not to set required fields because it can discourage submissions from those outside the org and citizen scientists. If a field is required, set a **Default value**.
4. **Description:** Briefly explain what the field is for.
5. **Category (required):** Choose an option from the menu (Life Events, Tagging, etc.).
6. **Options:** If you selected "dropdown" or "Multi-select dropdown" in the **Type** menu, add your dropdown menu options here.
    * **Option label:** This is what will display in Codex in sentence case.
    * **Value:** Treat this like the Database field. This will be in lowercase with underscores. Click Add Another Option to add more. When you're done, click the Finish button.
7. **Default value:** If you're creating a required field, make the default "unknown" or choose a default option that is accurate, if not precise.

When you're finished, click the **SAVE FIELD** button. This will take you back to the **Manage Fields** screen. You can preview your new field by clicking the View icon next to it.

***

## Edit Custom Fields

1. Select the **pen icon** to edit the custom fields you’ve created.
2. You will be directed to the **Edit custom field** page.
3. Aside from the custom field **Type**, everything can be edited on the *Configuration* panel on the right.
4. A live preview on the right will show you all the changes you made,
5. Click the **Save field** button to save all the changes you made.

## Delete Custom Fields

1. Select the **trash can** icon to delete the custom fields you’ve created.
2. A pop-up window will appear to confirm that you want to delete a custom field.
3. Click the **DELETE** button to confirm the changes that you want to make.