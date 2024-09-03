# Codex to Wildbook FAQ

## What's the difference between an Encounter and a Sighting?

[Sightings](../introduction/sighting.md) in Wildbook are the same as in Codex - a group of animals at a related time and place. An animal from the Codex Animal tab is the same as a Wildbook [Encounter](../introduction/encounter.md) page.

## The dates and times on my Encounters are different from the ones I reported in my Sightings.

Codex used a time zone calculation that was not fully implemented in the front end. Wildbook does not use time zones and transferred the date and time data without consideration for it, interpreting all reported dates and times as UTC (time zone Z). We plan on adding [time zone support](https://github.com/WildMeOrg/Wildbook/issues/721) to Wildbooks as part of a multi-stage fix across releases. 

If you don't want to wait for the fix, you can manually edit the time and date from the [Encounter](../introduction/encounter.md) page.
