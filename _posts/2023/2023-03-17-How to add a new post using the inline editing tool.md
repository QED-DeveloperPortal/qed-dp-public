---
title: How to add a new post using the inline editor in DevPortal
author: jeny-qed
categories: [public]
tags: [getting-started]
date: 2023-03-17 04:22:58
updatedBy: jeny
updated: 2023-05-26 04:53:00
likes: 0
---

This post provides an overview on how to add a new post in Developer Portal. The detailed steps are outlined below.

### Step 1  
Go to navigation menu and click on Categories.

![image](https://sadevportal3.blob.core.windows.net/root/add-post-step1.png)

### Step 2
You will see a list of categories that you have access to. Click on the category that you want to add the new content to.

![image](https://sadevportal3.blob.core.windows.net/root/add-post-step2.png)

### Step 3
You will see a list of posts under that specific category. Click on the 'Add post to this category' link to add new content for that category.

![image](https://sadevportal3.blob.core.windows.net/root/add-post-step3.png)

### Step 4
You will see a new page with an inline editor. Enter the following information about your post.
* Title 
    * The following characters should be avoided in the title field.
        * Triple Dashes (`---`)
        * Colons (`:`)
        * Angle Brackets (`<>`)
        * Quotation Marks (`'` and `"`)
        * Backticks  ( &grave; )
        * Square brackets(`[]`)
   * Refer to [guidelines for choosing valid title ](/public/Guidelines-on-choosing-a-valid-title-field-for-a-markdown-file/) for more information.
* Tags
    * You can one or more tags from the following list that are relevant to your content.
        * accessibility
        * api
        * architecture
        * cloud
        * getting-started
        * mobiles
        * security
        * technology
        * uxui
    * You can also add your own tag/s, separated by a comma.
* Content

Please note that you cannot change the category. By default, you can access the content that belong to 'Public' category. To access the content that are private (i.e. belonging to 'Internal' category, you need to send a request to the Developer Portal team).

![image](https://sadevportal3.blob.core.windows.net/root/add-post-step4.png)

### Step 5
You can preview the post in the right-hand pane of the editor. Alternatively, you can also click on WYSIWYG pane of the editor.

![image](https://sadevportal3.blob.core.windows.net/root/add-post-step5-1.png)
![image](https://sadevportal3.blob.core.windows.net/root/add-post-step5-2.png)

### Step 5
Click on the Submit button to publish the post.

### Step 6
Once the post has been successfully submitted, you will see a message with a commit hash , as shown below. This will trigger a build on the GitHub repository, which will take a couple of minutes. 

![image](https://sadevportal3.blob.core.windows.net/root/add-post-step6.png)

### Step 7
You can then view your post by accessing it via its Categories page.

![image](https://sadevportal3.blob.core.windows.net/root/add-post-step7.png)