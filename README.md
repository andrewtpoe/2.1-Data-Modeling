# Data Modeling Project

## Requirements
There must be a `README.md` file that contains models as headings with their properties listed as bullet points underneath based on the following text:

> I have an idea for an app.
>
> We are changing the way people manage their pictures! Someone should be able to sign in, upload a bunch of pictures and then be able to add information to each one like where it was taken, when it was taken and any additional notes. You know what? They should also be able to tag their family members. That sounds good.
>
> Each member of our amazing service should be able to see all of their pictures, and so should their family. There should be some sort of grouping that groups people together and allows them to see and comment on all of their group's photos.
>
> So how much will this cost me?

&mdash; Every picture startup founder ever.

## Solution

The following data model should provide the basic functionality requested in the requirements above. Additionally, I have laid out some of the methods that each of these classes should have as well. Additional (or refined) features could certainly be added.

###App
* .login		Provides login functionality for user to be verified and enter app

###User
* @username		User's login/ screen name
* @password		User's password
* @group_members		Member class instances assiciated with this user as a group member
* @my_pic_ids		Picture id's that this user has uploaded
* @tagged_pic_ids		Picture id's that this user is tagged in
* @view_pic_ids		Picture id's that this user is allowed to view
* .upload_pic		Allows user to upload a new picture
* .view_my_pics		Displays all pictures uploaded by this user
* .view_tagged_pics		Displays all pictures user is tagged in
* .view_all_pics		Displays all pictures user is allowed to see
* .tag_member		Allows user to tag a member of their group to a pic_id
* .add_member		Allows user to add a member to their group
* .logout		Exits user's profile and returns to App.login

###Member
* @username		Username of group member
* @relationship		Relationship of group member
* .view_pictures		Allows user to see all of the pictures uploaded by a member of their group

###Picture
* @id		Picture's unique id
* @timestamp		Time uploaded
* @photographer		Username of person that uploaded photo
* @location		Location, added by user if desired
* @date_taken		Date taken, added by user if desired
* @note		Note, uploaded by user if desired
* @comments		Comment class instances, uploaded by anyone that can view picture
* @tagged_users		Usernames of people tagged by the photographer
* .add_location		Allows user to specify location photo was taken
* .add_date		Allows user to specify date photo was taken
* .add_note		Allows user to add photo description/ note if it is their photo
* .add_comment		Allows user to add comment to any picture they can view
* .tag_user		Allows user to tag any user in their own group that is able to view this picture

###Comment
* @author		Writer of comment
* @id		Comments unique id
* @timestamp		Time comment was created
* @content		Content of comment
