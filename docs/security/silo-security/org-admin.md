# Org admin

Under Silo Security, users are grouped under organizations, which typically align with real-world organizations. To ensure that organizational goals are met, we have the **Org Admin Role**. These are Wildbook users who handle user management and bulk import concerns for their organization.

## How to apply for the Org Admin Role

To get the Org Admin Role, contact either a *site admin* or an *org admin* of the organization you want to help administer.

## Managing Users

### Adding Users

As an Org Admin, you are able to create and add users to your organization. Here’s what you need to know to create a new user:

1. Go to **Administer**, then **User Management**.
2. Look for the **Create/Edit User** section.
3. Enter a *username, email, and password*.
4. Select the appropriate role based on the permission level you want the user to have. This is multi-select as the roles are not hierarchical.
    * **researcher** - Users that can manage and export their own data, create projects, manage their collaborations, and confirm matches. Most users only need this role.
    * **orgAdmin** - Users that can create/edit users for their organization, and manage and export data for any user in their organization. Requires the **researcher** role.
    * **Admin** - Users that can manage all user data for the Wildbook they belong to. Requires the **researcher** and **orgAdmin** role.
    * **location ID name** - For Wildbooks with location-based roles; users with a specific location role can view, edit, and export all data for encounters with that location ID.
6. Under **Organization Membership**, select your organization to add a user to it.
7. Click **Save**.

### Deleting Users

*Note: Make sure to remove all roles associated with the user account you want to disable and change their password. We recommend disabling over deleting a user account if their data is trusted.*

1. Go to **Administer**, then **User Management**.
2. In the filter box, type a *username, first or last name, or other identifying information.*
3. Select a user from the user grid.
4. Click **Delete User** beneath the user’s information.

## Adding Users to your Organization

1. Go to **Administer**, then **User Management.**
2. In the filter box, type a *username, first or last name, or other identifying information*.
3. Select a user from the user grid.
4. Find the **Organization Membership** field in the user’s information.
5. Select your organization to add a user to it.
6. Click **Save**.

## Addressing Bulk Import Concerns

As an Org Admin, you can manage **bulk imports** for any user in your organization.

1. Go to **Administer**, then **Bulk Import Logs**.
2. Select the desired *Bulk Import task* from the list.
3. Scroll to the bottom. You can take any of the following actions:
    * **Send to identification**: Send all imported Encounters Identification. This can only be done if all Encounters have completed Detection.
    * **Delete Import Task**: Delete the Bulk Import and the related data. This can be done at any time.
