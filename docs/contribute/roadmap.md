# Roadmap
The roadmaps below are rough outlines of our objectives. We operate by milestones, and sometimes things change dramatically because of technical limitations or pressing issues reported by users.

## Wildbook
We are working on a improve-and-refresh objective. We want to improve on the user experience of Wildbook platform users with each release while also making the technology more accessible to the development community and indepedent installers. As such, we trade off a major feature release with a timeboxed tech debt release. We plan to continue this cadence through the end of 2024.

### 10.6.0
Feature focused release.
* All objects indexing in open search
* All filters available for all search formats
* Manual annotation and rotation

### 10.7.0
Tech debt release.
* Decouple WBIA
* Generated API documentation
* Weblate setup

### 10.8.0
Feature focused release.
* Custom fields support 
* Note: for production platforms, will include data migration to the custom field schema

### And Beyond
This work is planned for development, but is not set for an immediate release. Note that this list does not include minor changes and updates, some of which may be done iteratively. Are you interested in working on something here? [Reach out!](https://discord.gg/zw4tr3RE4R)

* One branch: All production instances run off the `main` branch and customizations are handled in-app
* Animal profiles: best representative image, best image by viewpoint, highlight on the front page
* Improved localization: integrate with Weblate to provide users ability to update translations
* Bulk Import improvement: move to 3rd party tool for on-page data validation and editing prior to submission
* Permissions: staff role, simplify permissions structure, clean up collaboration code and expand to include additional levels
* Organizations: Organization management view for org admins that includes organization-wide messaging, organization view for members, restrict org admin role to relevant org
* Data integrity tools: display hanging objects and provide options to resolve the issues
* Expanded match set controls: customize match sets wih any filter available in the platform, set default match set by user
* Improved notifications: clean up email and in-platform notifications, including graphic design elements
* Improved exports: improve existing exports to support all relevant fields automatically (dependent on custom fields), and add new exports such as customized community building templates
* Projects: Catalogues that can be processed rapidly, ability to identify, skip, and match as part of flow
* Surveys: collections of sightings are surveys
* In-product data analysis and visualization: Spatial and time analysis of all major biological elements (encounters, sightings, individuals, etc)
* Delete encounter: remove encounter from system, provide restore encounter function to admins, automatically fully delete (including images) after 30 days
* Leaderboards and gamification: tools to engage citizen scientists for continuous engagement
* Newsfeed: updates on the platform as relevant to a given user, allow for announcements from a user to a given population and/or tag
