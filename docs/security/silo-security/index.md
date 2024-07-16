# Silo Security

```{toctree}
:hidden:

org-admin
site-admin
photo-keywords
data-integrity
library-management
bulk-import-logs
```

The **Silo Security model** lets users decide who they share their data with. The users who most commonly use it are those working on academic research or at-risk species.

Permissions are granted at Encounter-level, meaning a user can access any **Sighting**, **Individual**, or **Survey** as long as they have access to the **Encounter** those belong to.

## User Roles

* **Contributor** \- users that are limited to only submit Sightings
* **Researcher** \- users that can manage their own data \(Sightings and Individuals\) and collaborations\,  match and merge individuals\, and search
* **User Manager** \- users that can create and edit users\, and manage user collaborations
* **Exporter** \- users that can export all the data they own and collaborate with
* **Administrator** \- users that can manage data and configure the Codex platform they belong to
* **machinelearning** \- not functional
* **rest** \- not functional

## Collaborations

Collaborations between users allow them to share data. Here’s what you need to know:

* Whether a user you’re in collaboration with can edit or just view your data is based on the permission you set.
* If you attempt access to an **Encounter** you don’t have access to, you will be prompted to start a collaboration with the user that **Encounter** belongs to.
* You can also search for a user you want to collaborate with if you go to **Administer** \> **My Account**. *(Note: search by username and name)*
* You cannot establish a collaboration with yourself.

Here’s a list of *associated permission* levels and available actions that you might encounter:

* **invitation sent:** You sent an invitation to another user. There are no actions to be taken.
* **invited:** You received an invitation. You can approve the invitation and grant the user view access to your data (can view), or you can deny the invitation and prevent a collaboration from being established (access denied).
* **can view:** Your collaboration has been accepted, and you can now see all data for encounters belonging to the other user and vice versa. End the collaboration with Revoke View Permissions.
* **can edit:** You can upgrade your collaboration with another user and edit each other's data for **Encounters**. If you want to revert to *view-only permission*, you can click **Revoke View Permissions**. If you want to end the collaboration, you can **Revoke View Permissions**.
* **access denied:** The invitation was denied or view access was revoked, while the request is retained so you can keep records of your collaborations. To resend the invitation, click **Restore Invite**.

### Example collaboration between two users

The person who initiates the collaboration has an assumed acceptance, so the receiver sets the collaboration permission level.

* If User Ana initiates collaboration with User Barry:
    *Neither party has view or edit access to data.*
* If User Barry accepts collaboration:
    *Ana and Barry can view each other’s data, but they cannot edit it.*
* If User Barry and User Anna click grant edit permission:
    *Both Ana and Barry can view and edit each other’s data.*
* If User Barry does not grant edit permission or revokes edit permission after granting it:
    *Ana and Barry can view each other’s data, but they cannot edit it.*

## Viewing Permissions

You can view an encounter if:

* You reported the Encounter.
* You’re a Site Admin.
* You have a Collaboration with another user that allows for view access.
* The Encounter was publicly submitted and not assigned to another User.

## Editing Permissions

You can edit an encounter if:

* You’re a site admin.
* You reported the Encounter.
* You have a collaboration with the owner and the owner grants you edit rights. *Note that edit rights can be revoked at any time.*

## Collaborating with Citizen Scientists

While the Silo Security model provides heightened security for your data, you can allow members of the public, like *citizen scientists*, to see your catalog (Encounter and Marked Individuals) by following these steps:

* Create a User Account in Wildbook with *‘public*’ as a username. This User has no roles and is not intended for login. Make sure to give it a secure password.
* Extend a *view-only collaboration* to the user *‘public’*. The public user account will automatically accept the collaboration.