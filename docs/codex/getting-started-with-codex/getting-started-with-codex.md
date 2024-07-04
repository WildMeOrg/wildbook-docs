# Getting Started with Codex

Codex is an open-source software framework supporting collaborative mark recapture, molecular ecology, and social ecology studies. It helps blend structured wildlife research with artificial intelligence, citizen science, and computer vision to accelerate population analysis and develop new insights to fight extinction.

***

## **Codex Features**

Here are the features that Codex users need to be aware of for effective data storage, curation, searching, and analysis:

* track individual animals in wildlife populations using natural markings, genetic identifiers, or vocalizations
* collect biological samples from wildlife populations to perform genetic and/or chemical analyses like stable isotope measurements, haplotype determination, etc.
* engage citizen scientists and use social media to collect sighting information
* build a collaborative and distributed research network for a migratory and global species
* develop a new animal biometrics solution, like pattern matching from photos, for one or more species
* collect behavioral and social data for a wildlife study population

***

## **Codex Terminologies**

Codex applies computer vision algorithms and deep learning to distinguish and keep track of species from the images uploaded to the database. Here are helpful terminologies to help you understand Codex’s functionality and features:

### **MediaAsset**

Codex will run the images through a *machine learning stage* *called Detection* to **Annotate** each Animal found on the images.

### Encounter

An **Encounter** is a recorded interaction with a single animal at a specific place and time. For example, if you interacted with 5 animals in the same location and time, you would have 5 Encounters.

**Encounters** are a critical component of Codex as they determine if an animal is qualified in a population analysis.

### **Sighting**

If you interact with 5 animals in the same location at a specific place and time, then that’s a **Sighting** composed of 5 **Encounters**. **Sightings** are for researchers to conduct a thorough study of animals’ social relationships and behaviors.

### **Individuals**

A single animal that has been given an identifying name and **Annotation** within **Codex** or other Wild Me platforms is called an Individual. For animals to be considered an Individual, their identities and metadata, like social information, needs to be confirmed by a researcher.

***

## Account Registration

When you first access a Codex site, you see the home page. You can view information on this specific instance by scrolling down the page, which displays content including how Codex works, facts and figures, social links, and buttons with calls to action. To get started, register an account.

### Registering a new account

1. From the home page, click the **Login** button in the top right corner.
2. Click the **Request an invitation** link.
3. You will be routed to the **Request an invitation** page.
4. Provide the **Email address** you want to be associated with your account and **Your name** so the site administrators know who is making the request. Optionally, you can also provide a note to the administrators explaining why you want access, by typing in the **Message for administrators** field.
5. Click the **SEND REQUEST** button.
6. You will receive an email with your temporary login information. Follow the instructions in the email to finish the registration process for your Codex account.

### Logging into your account

1. Click the **Login** button at the top right of the page.
2. Provide your **Email address** and the temporary **Password** you received from your welcome email in the fields.
3. Optionally, you can toggle the **Keep me logged in** button to keep yourself logged in for your next session.
4. Click the **LOGIN** button.
5. Check your email for a link to verify your account. Click the **Verify Email** link in the message.
6. Click **RETURN HOME** on the verification success page.
7. Provide your **Full name** and click the checkbox after reviewing the **Terms and Conditions** and **Data Usage Policy** to finish setting up your profile.
8. Click **SAVE PROFILE**.

***

## Change Your Password

To reset the password for your Codex account:

1. On the Account Login page, click the **Forgot?** link below the **LOGIN** button.
2. On the next page, provide the email address associated with your Codex account in the **Email address** field.
3. Click the **Reset Password** button.
4. Check your email inbox where you will receive an account password reset email. If you do not receive this, click the **Resend Email** button on the Password reset page.
5. Click on the link in the email you receive, which will direct you back to the Codex website to create a new password.
6. Type in your desired new password and repeat the same password in the **Confirm password** field. We recommend using at least 8 characters and a combination of letters, numbers, and special characters.
7. Click the **RESET PASSWORD** button. Once you see a confirmation popup message that says you have successfully reset your password, click the **Return to login page** link.
8. Log in with your email address and your newly updated password.

***

## **Matching and Submitting Encounters**

1. On the Codex Home page, click the **plus icon (+)** on the top right corner of the page.
2. In the space provided, you can *drag* *and* *drop* the images you want to import. You can also select **browse files** to import the images on your device.
3. To add more, select the **+Add more** button on the top right corner of the page then click **CONTINUE**.
4. Users have the option to *skip importing images* and go straight to uploading a **.csv file** by selecting the **CONTINUE WITHOUT PHOTOGRAPHS** button at the bottom of the screen.
5. Provide accurate answers to the questions that would follow. Users need to indicate the *number of animals on the sighting, Time of Sighting, Species Detection Model, Region, etc*.
6. Click **REPORT SIGHTING**.
7. After the animal detection phase, users will be prompted to assign Annotations for the images that were uploaded.
8. Click the **plus icon (+)** for each animal detected, then select the image with a bounding box around the animal you would like associated. Users may also add any additional metadata to the animals in the sighting at this point.
9. Select **Commit** at the top of the page.
10. Users will have the option to run an *identification job* on the images for any matches on other sightings.
11. Follow **[Confirm Match](https://docs.wildme.org/product-docs/en/codex/data/matching/#confirm-match)** if you decide to run an identification job.
12. If you decide to go against the identification job, you can still manually identify the animals in your sighting using **Identify** dropdown in the **Animals** tab to either **Create new individual** or **Manually assign** to an existing individual.

***

## Next Steps

Codex is a scalable and collaborative platform so that anyone from around the globe can participate. Sharing information such as images and data regarding them will make all the difference in collecting data for studying the wildlife population.

Codex is designed with a suite of functionality that can be extended to meet the needs of wildlife projects, especially where individual identification is used.

### Extend Collaboration Invites

You might want to extend invitations to collaborate with other Codex users. Visit **[Extend Collaboration Invites - Codex](https://docs.wildme.org/product-docs/en/codex/getting-started-with-codex/collaboration-invites/#extend-collaboration-invites-codex)** to learn more about how to add, edit and revoke collaborations.

### Request Further Configuration

A Codex platform might need some configurations to improve the quality of your research. Here are some of the common configuration changes:

* Adding your project’s study sites (also known as **Location ID** in Codex) that represent distinct areas where you conduct your data collection.
* Associating your user account with an organization and/or providing you with orgAdmin privileges allows you to bring additional users into Codex for your organization.
* Adding additional species to Codex.
* Working with Wild Me to create new machine learning or cross-apply existing techniques for a species.

If these categories apply, please request support on the[ ](https://community.wildme.org/c/feature-requests/6)**[Wild Me Community Forums - Feature Requests](https://community.wildme.org/c/feature-requests/6)**.

### Bulk Import Legacy Data for Matching

Many researchers have data from previous studies that need importing into Codex, such as the history of an animal and discoveries over distance/time. See **[Bulk Reporting](https://docs.wildme.org/product-docs/en/codex/getting-started-with-codex/bulk-reporting/)** for more information on how to convert your data to an Excel-based format for import into Codex.

#### How to Upload Images

1. From your *Codex homepage*, click the **Actions** button in the upper right corner of the screen.
2. Select **Bulk import**. You can only upload images in `.jpg`, `.jpeg`, and `.png` formats.
3. You will be directed to a page where you can upload images. You have the option to either *Drop files* or *Browse files*.
4. If you have another window open with the photos you want to upload; you can drag them directly to the *Bulk import* page to upload them.
5. You can also select *Browse files* to locate and upload the images from your device.
6. There will be a progress bar at the bottom of the screen showing the progress of your upload. Once everything is uploaded successfully, you will see *Complete* in place of the progress bar.
7. Add more photos by clicking **Add more** on the upper right corner of the page.
8. Select **CONTINUE**.

#### How to Upload Metadata

10. Select **UPLOAD SPREADSHEET** to upload a `.csv` file.
11. Once your `.csv` file is uploaded; you will be directed to a page to verify your uploaded data.
12. Make sure that the correct rows for *column headers* are selected.
13. After verifying all the data on the `.csv` file, select **Confirm mapping** or **Ignore this column** based on your preference.
14. Select **Review**.
15. You will be directed to another page to review your data.
16. Note that if there are errors, you won’t be able to continue.
17. After resolving any errors, select **Continue**.
18. A pop-up window will appear asking you to verify you’re ready to submit your sighting.
19. Select **Yes** to finish bulk importing your information and images.