# Site Status

Overview status regarding the site and jobs running on the site, primarily used for troubleshooting.

## Site information

**Versions**: The current version of each code project that comprises the current build being run. Production instances should only run official release versions, which can be found in the release tags on the [Wild Me GitHub](https://github.com/WildMeOrg).
**Commit hashes**: This is a more fine-grained verification than version, and is aimed at supporting developers.

## Job information

Last Hour: limits to the jobs completed in the last hour. Averages will return NaN (not a number) if no jobs have run in the last hour.

* **Job Turnaround Time**: An average of how long it took jobs to receive either a complete or error status.
* **Job Run Time**: An average of how long it took jobs to complete after leaving the queue.
* **Jobs Processed**: Count of the jobs that completed.

All Jobs: statistics about all jobs that have run on the platform.

* **Job Turnaround Time**: An average of how long it took jobs to receive either a complete or error status.
* **Job Run Time**: An average of how long it took jobs to complete after leaving the queue.
* **Jobs in Queue**: Count of the jobs waiting to process.

## Job status display

The job status display relates to recent and active jobs that are in the [Image Analysis Pipeline](https://docs.wildme.org/product-docs/en/codex/getting-started-with-codex/image-analysis/).

* **In detection queue**: Job is waiting to be processed for annotations.
* **In identification queue**: Job is waiting to be processed for match results.
* **Error**: Job did not successfully run.
* **Completed**: Job successfully completed both detection and identification.
* **In progress**: Job is actively being processed for either annotations or match results.