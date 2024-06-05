# Wildbook

Additional help with [Matching](https://docs.wildme.org/product-docs/en/wildbook/data/matching-process/) in Wildbook is available in our docs.

## How long do I need to wait for detection? Identification?

Machine learning jobs in Wildbook run in a shared, serial queue. Detection jobs can take between 10 seconds and hours, depending on how much shared ML work is in the queue. Identification jobs generally run only a few minutes but also share resources in the queue and can take longer while waiting for work farther ahead in the queue to complete.

## How can I tell if a detection job has completed?

You can tell if a detection job has completed by visiting the encounter page. If the images in the gallery have an annotation (dashed green line) around the animal, detection has completed. You will need to refresh the page to see the annotation appear.

## How can I tell if an identification job has completed?

You can tell if an identification job has completed by clicking the hamburger menu on an image in the encounter gallery and checking for “View Match Results”. If, instead, the menu says “Waiting on results”, the job is still processing. You will need to refresh the page to see the menu option change. If the menu says “Cannot start match” let us know in the [Community Forum](https://community.wildme.org/).

## How do I manually start a match?

You may want to re-run your match if you corrected an annotation, got an error message in your previous match results, want to compare to a bigger or smaller list of location IDs, or want try different identification algorithms. You can [manually start a match](https://docs.wildme.org/product-docs/en/wildbook/data/matching-process/#manually-starting-a-match) from the Encounter page. From here, you can modify the location and identification algorithms used.

## Where are my match results?

* "**No matchable detection**" means that due to the image quality or the animal being obscured, the animal wasn't detected. You can add a [manual annotation](https://docs.wildme.org/product-docs/en/wildbook/data/manual-annotation-beta/) and [start your match](https://docs.wildme.org/product-docs/en/wildbook/data/matching-process/#manually-starting-a-match). Note: If you see this appear when attempting to match whale sharks or sand tiger sharks, you need to select "spot mapping" from the menu instead.
* "**Error initiating IA job**" means there was in issue with detection that's preventing identification from starting. If you see this message when starting a new match from your manual annotation after seeing "No matchable detection" in the image menu, WBIA may be down. Let us know in the [Community Forum](https://community.wildme.org/).
* "**Attempting to fetch results**" or “**Gave up trying to match**” usually means that matching is still in progress. If you don't see match results within 24 hours, something may be wrong. Let us know in the [Community Forum](https://community.wildme.org/).
* "**Image Analysis has returned and no match was found**", "**No match confirmed**", or "**No match results**" means that there are no potential matches for that animal based on the location ID you selected.
* If you see "**Unknown error**", try [restarting the match](https://docs.wildme.org/product-docs/en/wildbook/data/matching-process/#manually-starting-a-match). If that doesn’t produce matches, remove the annotation, [create a new one](https://docs.wildme.org/product-docs/en/wildbook/data/manual-annotation-beta/), and start a new match. If you still get an error after following these steps, let us know in the [Community Forum](https://community.wildme.org/).
* 

## Why do I see matches for a different side of the animal than what's in my image?

This happens if the annotation viewpoint is incorrect (such as labeling the animal's left side as its right side). You can delete your annotation and [manually create a new one](https://docs.wildme.org/product-docs/en/wildbook/data/manual-annotation-beta/#creating-a-manual-annotation) if you think there's been a mistake. You won't be able to edit the viewpoint of someone else's image unless you have an edit [Collaboration](https://docs.wildme.org/product-docs/en/wildbook/security/silo-security/#collaborations) with that user.

## I uploaded the same image twice; why doesn't the identical image appear in the match results?

WBIA checks for identical images uploaded by the same user and excludes them from the list of potential match candidates.

## I'm on a project and I can't confirm matches on its encounters.

You need to have an edit [Collaboration](https://docs.wildme.org/product-docs/en/wildbook/security/silo-security/#collaborations) with the other project participants in order to confirm their matches.

## I've bulk imported my data, but my match results don't include candidates in a sub-region of my selected location.

Wildbook will only run identification for the exact location you put in your bulk import spreadsheet. If you want to expand the location range, you can [re-run the match manually](https://docs.wildme.org/product-docs/en/wildbook/data/matching-process/#manually-starting-a-match) on the encounter page and check the boxes for the additional sub-regions to include in the Location ID section.

Alternately, you can choose “ALL LOCATIONS” when you resend to identification from the bulk import page, but be aware that this option will take longer for identification to complete.

***

# Scout

Work in progress

***

# Codex

Work in progress