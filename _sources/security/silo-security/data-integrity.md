# Data Integrity

Data integrity tools can be found under *Administer > Data Integrity*.

## Check for Annotations with Multiple Individual IDs

Check your data for annotations that have been assigned to two or more different individuals. When these are present, it can cause matching to fail or result in falsely merged individuals. Ideally, this table will be empty.

## Find Annotations Duplicated in Two or More Encounters

Look for duplicated annotations to clean up your data set. From here you can also see which bulk imports contributed to the duplicate annotations or if a single bulk import contained multiple duplicate annotations.

## Check Annotation iaClasses and MediaAsset States by Species (visible to admins only)

Look for old iaClasses on annotations and media assets that are stuck in a "pending" state. This can cause poor matching performance as they are ignored. The species list allows you to inspect the iaClass values assigned for each species as well as the detection state of media assets in the database.

## URL Access Security Checks (visible to admins only)

Look for URLs in Wildbook that should or should not be accessible to the public or users with certain roles.

## Wildbook Machine Learning Queue Monitoring (visible to admins only)

See a current snapshot and 24 hour historical review of the machine learning pipeline. This can help you determine if a specific user's uploads are contributing to a backlog.

## Questionable (Data) Values

Look for data values in Wildbook that may contain errors, such as unsupported species values or bad GPS coordinates.
