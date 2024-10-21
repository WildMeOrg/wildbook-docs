# Org admin

Under Silo Security, users are grouped under organizations, which typically align with real-world organizations. To ensure that organizational goals are met, Wild Me established the **orgAdmin role**. These are platform members who will handle user management and address bulk import concerns for their organization.

## How to apply for the orgAdmin Role

To get the orgAdmin role, contact a user with the *staff* or *orgAdmin* role of the organization you want to help administer.

## Managing Users

### Adding Users

As an orgAdmin, you are able to create and add users to your organization. Here’s what you need to know to create a new user:

1. Go to **Administer**, then **User Management**.
2. Look for the **Create/Edit User** section.
3. Enter a *username, email, and password*.
4. Select the appropriate role based on the permission level you want the user to have. This is multi-select as the roles are not hierarchical.
    * **researcher** - Users that can manage their data and that of users they have an edit collaboration with, view data of users they have a view collaboration with, export thier and collaborator data, view their data integrity checks, and match and merge individuals.
    * **orgAdmin** - Users that can create and edit but not delete users within their org, manage user collaborations within their org, create other orgAdmins for their org, export data within their org, view data integrity checks within their org. Users cannot edit the data or roles of any user with the staff role, even within the same org.
    * **admin** - Users that can configure the Wildbook platform they belong to and can view ecological-related data integrity checks. *Can only be assigned by staff or another admin*
    * **staff** - Users that can create, delete, and edit users; create and delete orgs; manage all user data; configure the Wildbook platform they belong to; view user-related and ecological-related data integrity checks. *Can only be assigned by staff*
5. Under **Organization Membership**, select your organization to add a user to it.
6. Click **Save**.

### Deleting Users

Only users with the **staff** role can delete another user.

## Adding Users to your Organization

1. Go to **Administer**, then **User Management.**
2. In the filter box, type a *username, first or last name, or other identifying information*.
3. Select a user from the user grid.
4. Find the **Organization Membership** field in the user’s information.
5. Select your organization to add a user to it.
6. Click **Save**.

## Addressing Bulk Import Concerns

As an orgAdmin, you can manage **bulk imports** for any user in your organization.

1. Go to **Administer**, then **Bulk Import Logs**.
2. Select the desired *Bulk Import task* from the list.
3. Scroll to the bottom. You can take any of the following actions:
    * **Send to detection**: Send all imported Encounters to Detection. This can only be done if all Encounters have not been sent to Detection.
    * **Send to identification**: Send all imported Encounters to Detection and Identification. This can only be done if all Encounters have not been sent to Detection.
    * **Delete ImportTask**: Delete the Bulk Import and the related data. This can be done at any time.
