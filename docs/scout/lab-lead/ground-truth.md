# Ground Truth Review of Tasks

The Ground Truth stage of a task involves a review of its images and annotations for accuracy by a lab lead. The purposes of the ground truth stage are to:

* Assess annotator accuracy.
* Define final, correct annotations for an image. Once an image has been through the ground truth stage, no matter how many tasks it appears in, that image is considered DONE. It will never appear again for Annotation or Ground Truth.

$$INFO
title: Info
*When you delete an annotation as part of the ground truth process, you do not delete it from the task. Rather, the deleted annotation is no longer considered a part of the final set of annotations that make up the ground truth.*
$$

When exporting annotations, it is important to understand which Annotations are Ground Truth annotations as these are considered the most accurate representation of the content of each image. See [Exporting task annotation and image data for analysis](https://docs.wildme.org/product-docs/en/scout/lab-lead/draw-division-lines/#exporting-task-annotation-and-image-data-for-analysis) for more information.

***

If a task is fully annotated but has not been 100% through the Ground Truth stage yet, you can click the **Ground Truth** button next to the task on the Tasks table to begin reviewing randomly presented images and their annotations.

1. The **Annotation screen** allows you to *click-drag* to create a new bounding box and then press the down arrow or begin typing to select the correct label for the annotation.
2. You can click on any previously created annotation to edit it. A **trash can** ![trash can button](https://lh5.googleusercontent.com/-ookZpLefV_EXFWhIKPO7p1iuds9hnjPye4JZZEzy7cCIaI1zkfZccjnAp26ijb6oG5McL34RGQsS49D_5KKxpjeDthgFT_rAZDs2QQWfJZMsA3rZzAIuASyyIZG1ecnYOZWiszU3cGIwS1I_jyO0gWNUzTr8NydO9ZjurLW3fmfsSMxX6mje0nTBHRX9g){width="" height=""}
3. In addition to the *click-drag motion* for creating annotations, the following tools are available to you in the annotation interface:

* ![zoom in button](https://lh4.googleusercontent.com/ySlf6UPYFFO25h6NoOWLOhT4Zt2b9P-6P56x6HrOp8USOTwEBd3RZm-8Iy7yRfKzxWQUmGNkDpHmXZCjjuVbKb8Wkai1CXtFPaKKfvh7kYzXnfhdr1LPZwwdl8B48Ny_drX2IA41iwPocI0iF2lH5ue9yr4JPm3khz81C7MaMBwlJTlPVxXcEnOPf4BwDA){width="" height=""}
    zooms in on the image.
* ![zoom out button](https://lh5.googleusercontent.com/6zMNykmY9AzY4nQNa5XW3K5-7L1ue_2SWWn8ymXFfZIh6WQZlqDOgAetOe7s4Hv-u0_xiQDvph3Kl-IYAzAbjdhFHBCmN4qia_YNueIH3HM3aIi73WyRu8LZNzg1LDy-6hrZ3eCeVw1MpVa_YsWcDgRR4qRj4D3Nk_wMc1TUNBaf3dDt0plyCubr0uRRsA){width="" height=""}
    zooms out of the image
* **scroll bars** for the image allow you to pan across the image looking for parts to annotate
* ![back button](https://lh3.googleusercontent.com/AMUc5oxKCLOJkUn0D51cWbJdSwIP6i3dZ00jK2m1VlP6UHaH0bBd1yBzixwHVCieiIFytAE3W4FoRZQ-zZFfEhI-TBIotPPnl4SKlPAc-VnpNIgeHJyNezYzc0G14tbYCP_MW2nrw1P6t5SVKeEf4TWM_uN96QnILAmehk5A0IQboLRYEeZE5BegCX9GEg){width="" height=""}
    returns to the last image annotated in this annotation session
* **Done** to finish the ground truth stage of this image, making it as completely and accurately *done*. If any annotations were created, modified, or destroyed, they are now saved as ground truth. If no annotations were present when **Done** was clicked, the image is considered empty.
* ![side-by-side display button](https://lh4.googleusercontent.com/mT2n4-vQV48HIwO2gO0KqnSbDIWQfsWCl1Bezi1PfY6QGWXRP-184SimIm0rTEPMUVEDCCy_NqjY-Ap76n2h2WsuRaxZhsGhCtNRX6WAesoVzuoNJOJfv1HcT1LMKzUj3dBcSojv9Ly420--j-LCIFeKsZptx5-W5OOVexdKIKAVN3-Hl3KZzAhYmmUjWw){width="" height=""}
    opens a side-by-side display that allows you to compare annotations for this image to other tasks that contain this image. The **Reference Task** pulldown allows you to switch between other tasks that include annotations on this image. This allows you to perform your ground truth review in the context of multiple annotators (*including ML*) who may find and miss correct annotations in different ways. However, what you annotate in the left window on the image is considered the final and correct Ground Truth for the image.

***

![Ground Truth complete](https://lh3.googleusercontent.com/qTq8EbVeW-2QOVC1_-bKcL9kBMxirwsOZPxgb6W2ASgEeweDsH4gwDaJ_IJmo21JcR9DjmkdcCdZSqDxXpqdIliHz0nA9gN2Hz1ttV34acAUQIaE_4FnkO7dW1SP7gUcsLQ8K7M3QCEXYtYBMrFFF5SqFw3q3LSMJ34ZNgHzzG2q2Gnat47vSn8wkzGO7Q){width="" height=""}
Once Ground Truth is complete *(i.e. reaches 100%),* a window will pop out confirming that the changes have been saved.

## Annotation Toggle

When annotating or ground truthing a task, annotation labels can be applied to specific regions or objects in an image as tags or markers.

Toggle the visibility of the annotation labels and label delete buttons by clicking the **Show Labels** checkbox in the bottom left corner:

* Toggle the checkbox on to view the annotation labels and trash can icons to delete annotation labels. This is the default state.
* Toggle the checkbox off to hide the annotation labels and delete buttons, so the image and annotations are fully visible.