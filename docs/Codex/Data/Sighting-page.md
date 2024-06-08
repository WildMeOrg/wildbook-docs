A Sighting page provides information regarding a [sighting](https://docs.wildme.org/product-docs/en/codex/getting-started-with-codex/#sighting), to include the photographs and annotations, time and date, and queue status. Sightings can contain Animals or Individuals.

## Header

The header content is visible as long as you are on the sighting page. This includes:

* Featured Photo: the image that displays as a thumbnail of this sighting.
* Submitter name: A link to profile of the user who submitted the sighting. Use this to determine if a fellow researcher is a good candidate for collaboration.
* Sighting status: The processing status of the sighting. This is intended to allow users to know if all expected matches have been found. Status options include Unreviewed, In progress, Reviewed, and Unidentifiable.
* 3-dot menu: Located in the upper right corner of the header. Provides two options:
    * Re-run identification: Send the sighting through the identification pipeline again. Sightings are typically re-run with new parameters or after annotations and animals have been adjusted.
    * Delete sighting: Delete the entire sighting, including images and annotations, from the system. If sighting is associated with an individual and that individual has other sightings, the individual will remain.

### Change Featured Photo

If you have more than one image of a Sighting, you can change the Featured Photo.

1. Hover over the current Featured Photo and click the Change Photo overlay to open a modal.
2. Select the image you want to be featured and click Save.

## Overview tab

### Metadata

The information displayed here is relevant to all animals in the sighting. This includes time, location, and notes, as well as any custom fields in the platform.

#### Editing Metadata

1. Click the pencil on the metadata display card to open the Edit Sighting Metadata modal.
2. Make changes to all fields you want to edit. Verify that all required fields have data. Required fields are denoted with an asterisk (\*).
3. Click Save.

### Identification Pipeline Status

Processing a sighting requires both computational and human intervention. The pipeline displays the current status of the sighting's processing and indicates if a user is needed for the current step.

* Sighting Submission: The sighting was uploaded to the Codex. No user involvement is needed.
* Sighting Preparation: The sighting is added to the job queue. Also records the number of photographs in the sighting. No user involvement is needed.
* Animal Detection: Annotations are found within the images uploaded, or that detection was skipped. No user involvement is needed.
* Sighting Curation: Annotations are available to be assigned to animals. This stage requires human review and confirmation. Access the curation by clicking Assign Annotations. Note: if detection was skipped, instead click Annotate Photographs to draw the annotations manually.
* Identification: The sighting's annotations have been compared to the database and potential matches are available. This stage requires human review and confirmation. Access the match results by clicking View Match Results.

## Annotations tab

The annotations tab shows all of the photographs and annotations associated with the sighting. If multiple annotations are on a single image, the image will be displayed multiple times.

* Show annotations: A toggle the shows and hides the annotations of an image. Annotations are shown by default.
* 3-dot menu: Options for annotation management, including Add Annotation and Delete Annotation. The options in the 3-dot menus will only be available if the option is available.
* Tags: Tags are metadata that is associated with the annotation. Click on an image to add tags to the annotation.

### Add Annotation

To add an annotation to an image:

1. Click the image's 3-dot menu and select the Add annotation button to open the Create Annotation page.
2. On the image display, adjust the annotations.
    * Use the edges of the annotation square (blue) to make the annotation line up closely with the animal.
    * The dashed line needs to align with the top of the animal. Use the double dot to rotate the annotation so the dotted line is correctly aligned.
3. Set the Viewpoint by selecting the side of the animal that is shown in the image.
4. Click Annotation class to select the correct species.
5. Click Save to create a new annotation, and return to the Annotations tab.

### Delete Annotations

To delete annotation from an image:

1. Click the image's 3-dot menu and select Delete annotation.
2. On the Confirm Delete modal, select Delete.

### Manage Tags

To add a tag:

1. Click Add Tag.
2. Type the name of the tag. A list of existing tags will display.
    * If the tag you want to use displays in the list, click the tag then click Add tag.
    * If the tag you want to use is not in the list, finish typing out the full tag, then click Add tag.

To delete an existing tag, click the X on the tag. There is no confirmation.

## Animals tab

The Animals tab shows a list of all of the animals in a given sighting, and provides for management of the animals.

### Animals List

The animal list is intended to allow for user to curate the annotations of a sighting. Each annotation needs to be assigned to an animal.

#### Curate Sightings

* To add unassigned annotations to an animal, click the Assign button of the animal.
* To add another animal to the sighting, click + Click Animal.
* To move an assigned annotation to another animal, click the annotation's 3-dot menu and select Move to another animal. In the Move Annotation to Another Animal modal, select the animal and click Move Annotation.
* To delete an animal, click the animal's 3-dot menu and click Delete animal.

Once all annotations are assigned, you are ready to commit the sighting.

#### Commit Sighting

1. In the blue alert, click Commit.
2. Select the settings for the Identification job for this sighting.
    * Run identification job with the default settings: matches against all annotations that have the same species, same region, and the related viewpoints, using model selected during upload.
    * Do not start an identification job: Sighting processes, but no match results become available. Useful for sightings that have known matches that can be assigned manually.
    * Customize settings for this identification job: select what region or model is used for match job.

#### Identify Animal

Create new individual: Create a new individual from this animal, associating the sighting with the new individual.

Manually assign: Search the existing individual's in the database and associate the animal with the existing individual.

### Metadata

A metadata display card is available for each animal in the sighting; this data does not apply to the sighting generally.

1. Click the pencil on the metadata display card to open the Edit Animal Metadata modal.
2. Make changes to all fields you want to edit. Verify that all required fields have data. Required fields are denoted with an asterisk (\*).
3. Click Save.