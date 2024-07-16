# Study Sites

A study site in Wildbook (also called an **Encounter's "location ID"**) is a fixed value that represents a specific area where wildlife data is collected. A study site is one of Wildbook's three "where" data fields, which also include the more exact GPS coordinates (exact positioning) and the less exact verbatim locality (simply called "location").

Study sites defined in Wildbook can be used to search and filter data, define location-specific permissions, and filter computer vision matching to only likely or realistic resighting locations.

![encounter Location ID](../assets/images/wb-encounter-locations.png)

***

## Reporting an Encounter with a Location ID

When you [report an Encounter](https://wildbook.docs.wildme.org/data/report-an-encounter/), you can set its **location ID** directly. **Location IDs** are hierarchical and nested, allowing for regional organization.

![encounter Location ID](../assets/images/wb-submit-locationid.png)

***

[You can start a manual match from the Encounter](https://wildbook.docs.wildme.org/data/matching-process/#manually-starting-a-match), which allows you to multi-select location IDs to match an Annotation against, as shown below.

![match Criteria](../assets/images/wb-encounter-customalg.png)

***

## Adding a New Study Site

To add a new study site, you'll need to contact your Wildbook's administrator or make the request at the [Wildbook Community](https://community.wildme.org).

**Location IDs** are added to a file in Wildbook named `locationID.json`. Each location ID is defined in the **JSON** format as follows:

`{ "name":"Iceland", "id":"Iceland", "locationID":[], "prefix": "Ice-", "prefixDigitPadding": 4, "defaultLatitude": 64.4577778110883, "defaultLongitude": -22.454850367706463 }`
and can be nested.
`{"name":"South Pacific","id":"South Pacific","locationID":[ {"name": "Tasman Sea", "id": "Tasman Sea" }, { "name":"NewZealand", "id":"NewZealand", "locationID":[] } ]}`

The fields are used as follows:

* **name** \- the descriptive\, human\-readable name of the study site
* **id** \- the value of the study site to store in the "ENCOUNTER" table of the Wildbook database in the `"LOCATIONID"` column. This value must be unique in `locationID.json`
* **locationID** \- a `JSON` array of other location IDs that are nested and logical subsites of this location
* **prefix**(optional) - an abbreviation to the study site that can optionally be used to name new individuals when an incremental naming system is desired (e.g., "Ice-0001", "Ice-0002", "Ice-0003", etc.)
* **prefixDigitPadding** (optional) - the number of orders of magnitude that you expect with the (optional) incremental individual naming system. For instance, picking `"prefixDigitPadding": 5` (instead of 4 as in the example above) would result in individual names such as "Ice-00001", "Ice-00002", "Ice-00003", etc. (note the additional 0).
* **defaultLatitude** (optional) - if there are no explicitly designated GPS coordinates for a particular encounter, the locationID can be used to designate a default latitude when exporting encounter search results using the "Exported Excel spreadsheet (.xls) file in OBIS format with locale inclusion for unreported GPS" option.
* **defaultLongitude** (optional) - if there are no explicitly designated GPS coordinates for a particular encounter, the locationID can be used to designate a default longitude when exporting encounter search results using the "Exported Excel spreadsheet (.xls) file in OBIS format with locale inclusion for unreported GPS" option.

Restart Tomcat after making changes.

### Example locationID.json

[Here is an example locationID.json file from the Flukebook.org platform.](https://github.com/WildMeOrg/Wildbook/blob/flukebook/src/main/resources/bundles/locationID.json)