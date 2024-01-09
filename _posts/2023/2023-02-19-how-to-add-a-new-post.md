---
title: How to add a new post in a jekyll site
author: jeny-qed
categories: [public]
tags: [technology]
date: 2023-03-14 14:03:17
updatedBy: jayarvee
updated: 2023-05-11 02:10:38
likes: 0
---

Jekyll is a powerful static site generator that makes it easy to create a website with a simple and easy-to-use interface. One of the most common tasks when working with Jekyll is adding new posts to your site. In this article, we will take a look at how to add a new post to your Jekyll site.

### Step 1: Create a new post file

The first step to adding a new post to your Jekyll site is to create a new post file. You can do this by navigating to the ***`_posts`*** directory in your Jekyll project and creating a new file with the following format:

```sql

YEAR-MONTH-DAY-title.md
```

For example, if you want to create a post with the title "My First Post", you would create a file with the following name:

```

2023-02-20-my-first-post.md
```

### Step 2: Front matter

Once you have created your new post file, you will need to add front matter to it. Front matter is a section of YAML metadata that Jekyll uses to determine how to handle your post.

At a minimum, your front matter should include the title of your post, as well as the date and any categories or tags that you want to associate with your post. Here is an example of a basic front matter section:

```yaml



layout: post

title: "My First Post"

date: 2023-02-20 12:00:00 -0500

categories: jekyll

tags: [jekyll, tutorial]


```

The ***`layout`*** field specifies which layout file to use for your post, while the ***`title`***, ***`date`***, ***`categories`***, and ***`tags`*** fields provide metadata about your post.

### Step 3: Add content

With your front matter in place, you can now add the content of your post. Jekyll uses Markdown syntax to format your post, so you can include headings, lists, images, and more.

### Step 4: Save and build

Once you have added your post content, save the file and build your Jekyll site. You can do this by running the following command from the terminal:

```

jekyll build
```

This command will generate your site and output it to the ***`_site`*** directory.

### Step 5: Preview your post

To preview your post, you can run the following command from the terminal:

```

jekyll serve
```

This will start a local server that you can use to view your Jekyll site. You can then navigate to your post by entering its URL in your web browser.

In conclusion, adding a new post to your Jekyll site is a simple process that involves creating a new post file, adding front matter, adding content, saving and building, and previewing your post. With these steps, you can quickly and easily create new content for your Jekyll site.