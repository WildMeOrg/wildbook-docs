# Image Analysis Development

## Code Pathways to IA

### Single Encounter Submission
1. User starts on submit.jsp
2. `EncounterForm`
  - `IA.intakeMediaAssets(myShepherd, enc.getMedia().parentTask);`
  - `IA. intakeMediaAssetsOneSpecies(myShepherd, assetsBySpecies.get(0), parentTask);`
  - `intakeMediaAssetsOneSpecies(myShepherd, mas, taxy, parentTask);	`
  - `intakeMediaAssetsOneSpecies(Shepherd myShepherd, List<MediaAsset> mas,Taxonomy taxy, final Task parentTask, int tweetAssetId)`
  - `IAGateway.addToDetectionQueue(context,qjob.toString());`
3. WBIA detection occurs independently
4. `IBEISIA.processCallback`
  - `processCallbackDetect(...)`
  - `IA.intakeAnnotations(myShepherd2, needIdentifying, parentTask, false);`
  - `IAGateway.addToQueue(context, qjob.toString());`
5. `IBEISIA.processCallback`
  - `IBEISIA.processCallbackIdentify`
6. Results visible from "match results" button on annotation on Encounter page

### Bulk Import
_Assumes bulk detection on the ImportTask has already occurred._

1. User has completed a bulk import and is looking at it on the related import.jsp page.
2. `resendBulkImportID.jsp`
  - `IA.intakeAnnotations(myShepherd, matchMeAnns, subParentTask,false);`
  - `IAGateway.addToQueue(context, qjob.toString());`
3. Queue (“IA”) sends to WBIA
4. `IBEISIA.processCallback` when job returned by WBIA to /ia
  - `IBEISIA.processCallbackIdentify`
5. Results visible from “match results” button on annotation on an imported Encounter page or from the import.jsp for the bulk import.

### Manual 'Start Match' from Encounter Page
_Assumes detection has already run, and annotations already exist._

1. User clicks “start match” or “start another match”  from encounter.jsp
  - `encounter.jsp.iaMatchFilterGo(...)`
  - `ia.IBEIS.js.restCall(...)`
2. `IAGateway.java`
  - doPost
  - `if (j.optBoolean("enqueue", false) || j.optBoolean("v2", false)) { `
  - `addToDetectionQueue(context, j.toString());` or `addToQueue (...)` depending on fastlane status
3. Queue (“detection”/fastlane) - except for HotSpotter jobs which are sent to “IA” queue sends to WBIA
4. `IBEISIA.processCallback` when job returned by WBIA to /ia
  - `IBEISIA.processCallbackIdentify`
5. Results visible from “match results” button on annotation on Encounter page
