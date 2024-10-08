# Merging FAQ

Additional help with [Marked Individuals](../introduction/marked-individual.md) in Wildbook is available in our docs.

## I’ve discovered that two individuals in the system are the same animal, but they don’t show up in each other’s match results. How do I merge them?

Move all encounters from one individual to the other. When the individual you don’t want to keep has no encounters associated with it anymore, it will automatically be removed from the system.

1. Open each individual’s page and see which one has fewer encounters to reassign.
2. From the marked individual page with fewer encounters, open each encounter from the list.
3. Click the Edit button in the Identity section of an encounter.
4. Under Manage Identity, click "Remove from marked individual."
5. In the same section, you'll now see the option to "Add to existing individual ID." Type in the ID of the individual you want to reassign the encounter to.
6. Click the Add button to save your changes and close the edit window.
7. Repeat steps 3-6 for the encounters you opened.

## How to merge via URL

You can also merge two individuals without having to go through the match results first.

1. Visit the Individual page for Individual A
2. Copy the 36-digit alphanumeric ID from the URL (everything after **?id=**)
    Ex: `https://wildbook.org/individuals.jsp?id=1234`
3. Repeat this process for Individual B
4. Use this formula to access the merge page:
    https://`Wildbook URL`/merge.jsp?individualA=`code from Individual A`&individualB=`code from Individual B`
    Your final result will look something like this:
    `https://wildbook.org/merge.jsp?individualA=1234&individualB=4321`
5. On the merge page, fields in red have conflicting values and need to be corrected before merging. If no conflicts exist, click "Merge Individuals".

## How do I unmerge two animals?

Click the Edit button in the Identity section of an encounter. Under Manage Identity, click "Remove from marked individual." 

Enter the correct ID in the "Set new individual ID" field if it’s a new individual or in the "Add to existing individual ID" field if the individual already exists in Wildbook.

## How do I cancel a merge request?

If a user doesn't own any of the previous encounters of the individual they want to merge with, they need permission from someone who does. Those owners are sent a notification in Wildbook to approve or deny the request. If nobody responds to the merge request after two weeks, the merge is completed. In order to cancel a pending merge request, you need to contact the owner of the encounter and ask them to deny the merge.
