# Manual Annotation (Beta)

When looking at an Encounter page, you may see that a **MediaAsset** does not have a dashed rectangle **(e.g. Annotation bounding box)** around an animal in the picture. In this case, the detection stage did not recognize the animal.

## Navigating to the Manual Annotation Page

In an Encounter page's **Gallery**, open the hamburger menu on the image and select **add annotation** to open the manual annotation screen.

```{note}
- Select **spot mapping** if you're annotating grey nurse sharks or broadnose sevengill sharks in Sharkbook and for sea bass in Spotting Giant Sea Bass. More detailed instructions on spot mapping are on our [YouTube channel](https://www.youtube.com/watch?v=DaHu2K9j4AY).
```

![add anotation button](../assets/images/wb-manual-annotation-menu-option.png)

## Understanding the Manual Annotation Page

**The Manual Annotation page** has the following sections:

![manual annotation sections](../assets/images/wb-manual-annotation-interface.png)

## Creating a Manual Annotation

Creating a Manual Annotation

1. **IA Class** defines the type of animal or feature that represents the annotation. This is a fixed list per species that corresponds to detection classes returned by the [Image Analysis pipeline](../introduction/image-analysis-pipeline.md).
    * **Animal (ex: turtle_green, whale_orca)**: Select all visible parts of the body in one annotation.
    * **Animal+body part (ex: turtle_green+head, whale_orca+fin_dorsal)**: Select only the body part used for identification, such as the head, dorsal fin, fluke, etc.
    * If there are multiple animals in your photo or multiple *IA Classes* you want to annotate, add them later. Only one annotation at a time can be created.
2. In **Viewpoint**, choose the primary viewpoint that the photographer is observing the animal from, such as the animal's **left**, the animal's **right**, looking **down** at the animal, looking **up** at its belly, etc. *Note that for salamanders in Amphibian and Reptile Wildbook only, **up** is used when looking down at the salamander from above.*
3. In **Draw Annotation**:
    * Hold left-click with your mouse to start drawing the annotation.
    * Move your mouse pointer to the opposing corner position of a rectangle and release the mouse button (i.e. if you start at the top-left of the animal, move your mouse pointer toward the bottom-right). Click **Delete** if you made a mistake and want to redraw the annotation.
    * If your animal is positioned at an angle, you can rotate the annotation box by clicking on its border and using the handle to adjust its position. 
4. Click **Save Annotation** when you're done. A confirmation page will appear with a link back to the Encounter page.

```{note}
When annotating multiple animals in a photo, Wildbook may clone this Encounter if another annotation is already on this MediaAsset. Two annotations in one image generally means that two animals are present and at least two Encounters (one animal at a location and date) must exist.
```

1. Navigate back to the Encounter page and add new annotations if needed, or click [start match](matching-process.md) to begin the identification pipeline for this new annotation.

## Troubleshooting

### How do I fix an annotation?

If an incorrect annotation is created, whether through the detection process or manually, you can first [delete the annotation](../data/matching-process.md#removing-a-single-annotation) and then re-draw the annotation if desired using the steps above.

### How do I annotate a part of an individual (Ex. head, tail, etc.)?

When selecting the annotation iaClass, look for the species, plus the part symbol '+'. For example, if you would like to annotate green turtle heads, search 'turtle_green+head'.

### How do I associate a part with the body in my encounter?

For a new annotation:

1. From the encounter you want to add a part to, select **add annotation** from the hamburger menu on the correct image.
2. Complete the steps above for adding a new annotation, making sure to select the IA Class that includes the body part.

If the species of the body and the species of the part are the same, the annotations will both be associated with the encounter. If they are not:

1. Delete your newly created part annotation by deleting the new encounter created.
2. Return to your original encounter. Create a new annotation for the body with the correct species.
3. Delete the previous body annotation.
4. Create a new part annotation.

### How do I move an annotation from one individual to another?

1. Navigate to the Encounter with the misassigned annotation
2. In the hamburger menu on the image, select **add annotatio**
3. Choose the **IA Class** and **Viewpoint**, then draw the same annotation around the animal. When you click **Save Annotation**, it will clone the encounter metadata and add your new annotation to it. The new encounter will not be part of the Individual, but it will be part of the same Sighting.
4. Go back to your original Encounter. In the hamburger menu of the annotation you just duplicated, select **remove annotation**.
