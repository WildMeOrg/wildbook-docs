# Silo Security

```{toctree}
:hidden:

photo-keywords
data-integrity
library-management
bulk-import-logs
```

The **Silo Security model** lets users decide who they share their data with. The users who most commonly use it are those working on academic research or at-risk species.

Permissions are granted at the Encounter level, meaning a user can access any **Sighting**, **Individual**, or **Survey** as long as they have access to the **Encounter** those belong to.

## User Roles

**researcher** 
* Users that can manage their data and that of users they have an edit collaboration with, view data of users they have a view collaboration with, export their data and that of users they have a collaboration with, view their data integrity checks, and match and merge individuals.

**orgAdmin**
* Users that can create and edit users within their org, manage user collaborations within their org, create other orgAdmins for their org, export data within their org, view data integrity checks within their org. OrgAdmins cannot edit the data or roles of any user with the **staff** or **admin** role, even within the same org.

**admin**  
* Users that can view ecological-related data integrity checks and configure the Wildbook platform they belong to (such as managing [photo keywords](photo-keywords.md)).

**staff**
* This role is intended for Conservation X Labs organization members and is managed in the Wildbook's configuration setting (not within the platform). Staff can create, delete, and edit users; create and delete orgs; manage all user data; configure the Wildbook platform they belong to; and view user-related and ecological-related data integrity checks. 

## Managing Users

### Adding Users

OrgAdmins can create and add users to their organization. To get the orgAdmin role, contact a user with the *staff* or *orgAdmin* role of the organization you want to help administer. To create a new user:

1. Go to **Administer**, then **User Management**.
2. Look for the **Create/Edit User** section.
3. Enter a *username, email, and password*.
4. Select the appropriate role based on the permission level you want the user to have. This is multi-select as the roles are not hierarchical. OrgAdmins cannot assign or remove the **admin** or **staff** role from other users.
5. Under **Organization Membership**, select your organization to add a user to it.
6. Click **Save**.

### Deleting Users

Only users with the **staff** role can delete another user.

### Adding Users to your Organization

1. Go to **Administer**, then **User Management.**
2. In the filter box, type a *username, first or last name, or other identifying information*.
3. Select a user from the user grid.
4. Find the **Organization Membership** field in the user’s information.
5. Select your organization to add a user to it.
6. Click **Save**.

### Addressing Bulk Import Concerns

OrgAdmins can manage **bulk imports** for any user in their organization.

1. Go to **Administer**, then **Bulk Import Logs**.
2. Select the desired *Bulk Import task* from the list.
3. Scroll to the bottom. You can take any of the following actions:
    * **Send to detection**: Send all imported Encounters to Detection. This can only be done if all Encounters have not been sent to Detection.
    * **Send to identification**: Send all imported Encounters to Detection and Identification. This can only be done if all Encounters have not been sent to Detection.
    * **Delete ImportTask**: Delete the Bulk Import and the related data. This can be done at any time.

## Collaborations

Collaborations between users allow them to share data. Here’s what you need to know:

* Whether a user you’re in collaboration with can edit or just view your data is based on the permission you set.
* If you attempt access to an **Encounter** you don’t have access to, you will be prompted to start a collaboration with the user that **Encounter** belongs to.
* You can also search for a user you want to collaborate with if you go to **Administer** > **My Account**. *(Note: search by username and name)*
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
* You have the staff role.
* You're an orgAdmin and the Encounter belongs to a member of your org.
* You have a Collaboration with another user that allows for view access.
* The Encounter was publicly submitted and not assigned to another User.

## Editing Permissions

You can edit an encounter if:

* You have the staff role.
* You're an orgAdmin and the Encounter belongs to a member of your org.
* You reported the Encounter.
* You have a collaboration with the owner and the owner grants you edit rights. *Note that edit rights can be revoked at any time.*

## Collaborating with Citizen Scientists

While the Silo Security model provides heightened security for your data, you can allow members of the public, like *citizen scientists*, to see your catalog (Encounter and Marked Individuals) by following these steps:

* Create a User Account in Wildbook with *‘public*’ as a username. This User has no roles and is not intended for login. Make sure to give it a secure password.
* Extend a *view-only collaboration* to the user *‘public’*. The public user account will automatically accept the collaboration.
