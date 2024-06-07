# How to Evaluate Annotator Performance

Use both the Image and Annotation CSV exports allows evaluation of the whole image classifier (WIC). For this performance method, we use the following definition of ground truth:

An image is a “positive” in the ground truth if the annotation CSV has at least one ground truth positive annotation in this image. An image is a “negative” if there are no such annotations.

This definition could be varied to measure the performance of the WIC as a function of the number of animals in the image.

## Method

The CSV output of the annotations provides the basis for evaluating the labeling accuracy of the ML detection model by comparing its detected annotations to those of the ground truth. This may also be done to evaluate the labeling accuracy of an assignee (regardless of if the assignee is a model or human annotator). In this case, the accuracy measure is a measure of consistency.

Consider the comparison between the ML model and the ground truth.

* For each row, determine if the assignee is the ML model of interest. If yes, the row constitutes a *detected annotation*.
* For each row, determine if the Ground Truth field is true. If yes, the row constitutes a *ground truth annotation*.
* Each *ground truth annotation* is only allowed to be assigned one detected annotation.

For each the detected annotation, verify if:

1. A ground truth annotation found in the same image
2. The matching annotation has the same Classification label
3. The bounding box has sufficient overlap with that the detected annotation

## Evaluation criteria

* If ground truth annotation has no detected annotations, then the row is considered to be a false negative.
* If all three are true, then the detected annotation is a true positive.
* If there is no such ground truth annotation, then the detected annotation is a false positive.

From these definitions of true positives, false positives, and false negatives, values for precision, recall and F1 may be calculated.

A key point here is the notion of “sufficient overlap”. The amount of overlap between Boxes is usually measured in terms of intersection over union (IOU). Intersection is the area of the intersection between the Boxes. Union is the area of the union between the Boxes. IOU is the ratio of these. These are straightforward to compute because the axes of the Boxes are parallel to the horizontal and vertical axes of the images. If a single IOU threshold is chosen it is typically 0.5, but often a plot is given of the effect of using different IOU scores.

## Final Notes

1. When multiple possible ground truth annotations (same image, same label) are found for a detected annotation, the ground truth annotation having the largest IOU with the detected annotation should be chosen.
2. It is recommended that the exclusion line is not used in performance evaluation of assignees and ML models.
3. Further experiments with the machine learning model and its output could fine tune it for a variety of use cases. Typically these are based on the summary statistic of the “mean average precision” (mAP), which is widely discussed in the detection literature. This is beyond the scope of Scout 1.0.