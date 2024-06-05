# Export

When you've performed a [search ](https://docs.wildme.org/product-docs/en/wildbook/data/search/)in Wildbook, you can navigate to the **Export** tab to export the data that matches your search results in various formats. Available formats vary by search type and may include the following.

***

## Encounter Search Exports

### Standard Format Export

Exports an Excel file of results corresponding to the [Bulk Import format](https://docs.wildme.org/product-docs/en/wildbook/data/bulk-import-beta/) of Wildbook.

### Exported Excel spreadsheet (.xls) file in OBIS format

Exports an Excel file in the Darwin Core format compatible with import into [OBIS.org](https://www.obis.org), [GBIF.org](https://www.gbif.org), or a similar biodiversity database using the [Darwin Core data format](https://dwc.tdwg.org/terms/).

#### Include locale inclusion for unreported GPS

Exports an Excel file in the Darwin Core format compatible with import into [OBIS.org](https://www.obis.org), [GBIF.org](https://www.gbif.org), or a similar biodiversity database using the [Darwin Core data format](https://dwc.tdwg.org/terms/). For matching Encounters without GPS coordinates but belonging to a [study site](https://docs.wildme.org/product-docs/en/wildbook/specifications-and-system-requirements/system-configuration/#configuring-location-ids-study-sites) mapped to default GPS coordinates in locationIDGPS.properties, those default properties will be used in the export file.

### Exported email data contributors file

Exports a text list of the email addresses of data contributors related to the search result.

### Exported Google Earth KML file

Exports a KML file of search results for use in Google Earth or GIS applications.

### Exported Google Earth KML file with timeline

Exports a KML file of search results for use in Google Earth. This includes date information to allow for timeline display.

### Exported GIS shapefile

Exports a zip of GIS shapefiles for import into GIS applications.

### Simple Mark-Recapture History File Export

Exports matching search data in a capture history format compatible with Program Mark, RMark, or other similar programs.

*Note: you should filter the results by a locationID because the comparison will only be made against the first locationID in the results.*

1. To start, set the **Number of capture sessions** by entering a number.
2. Click submit.
3. Enter the time frames for each capture session.
4. Click submit.

The generated output will check your time frames for each individual and unassigned encounter.

Addition configuration options include:

* **Include marked individual ID as a comment at the end of each line**: Check this box to include the individual ID of the Marked Individual as a comment in the export format.
* **Include search query summary as a comment and URL at the start of the file**: Check this box to include query details as a comment in the exported file.

## Individual Search

* **Picture Book** \- Generates a printable web page for offline manual identification\. This page can be printed to PDF from your browser and should format with one animal per page\.
* **Capture** \- Exports the match results in a format compatible with the CAPTURE program\.
* **SOCPROG** \- Exports the match results in a format compatible with the [SOCPROG program](http://whitelab.biology.dal.ca/SOCPROG/social.htm).
* **Kinalyzer CSV** \- Exports the match results in a format compatible with the Kinalyzer program\.
* **Mark Recapture Export** \- Exports matching search data in a capture history format compatible with Program Mark\, RMark\, etc\. Copy this search
    * **Number of capture sessions** \- The number of primary capture sessions in your format\.
    * **Include marked individual ID as a comment at the end of each line (Program MARK only)** \- Check this box to include the individual ID of the Marked Individual as a comment in the export format\.
    * **Include search query summary as a comment and URL at the start of the file (Program MARK only)** \- Check this box to include query details as a comment in the exported file\.

## Sighting Search

* **Excel Metadata Summary** \- Excel\-based export of the search results\.