# Roadmap
The roadmaps below are rough outlines of our objectives. We operate by milestones, and sometimes things change dramatically because of technical limitations or pressing issues reported by users.

## Wildbook
We are working on a improve-and-refresh objective. We want to improve on the user experience of Wildbook platform users with each release while also making the technology more accessible to the development community and indepedent installers. As such, we trade off a major feature release with a timeboxed tech debt release. We plan to continue this cadence through the end of 2024.

### 10.3.0
Feature focused release.
* Improve encounter search through OpenSearch integration. Better indexing for large scale platforms, and integration open source technology allows for continuous improvement rather than our home-spun search.
* Feedback from 10.2.0 indicates that we need to smooth  the transition for the React changeover. We'll start by matching the header between react and jsp, giving a consistent navigation experience on all pages.
* Fix Wildbook docker update so it updates on every release. Has been broken for several years, just needs the attention on it.
* Documentation is currently spread out between different formats and locations. Consolidated Wildbook/Scout/contributor documentation release that allows for direct contribution will reduce overhead for all doc management.

### 10.4.0
Tech debt release.
* Remove adoptions functionality, which is a support burden and does not function as a revenue stream.
* Setup the default Wildbook information to be site-neutral, allowing users to set up their own Wildbooks more easily.

### 10.5.0
Feature focused release.
* One search. Index Sighting and Individual information using OpenSearch
* Custom field support.

### 10.6.0
Tech debt release.
* Transition platform fields to custom field structure.

### 10.7.0
Feature focused release.
* Bulk import refresh. Leverage an open source technology that allows for column mapping and provides clear validation before submission.

## Scout
Because Scout started as a tool to support a single project, We are working to broaden the usage by making it a more generalized tool. We want to improve the workflow management and annotation interface.

### 2.2.0

### 2.3.0
