---
title: Guidelines on choosing a valid title field for a markdown file
author: jeny-qed
categories: [public]
tags: [guidelines]
date: 2023-05-18 00:27:58 
updatedBy: qed-devportal-admin
updated: 2023-09-05 02:02:54 
likes: 2
---

In a markdown file, the front matter is typically defined using YAML or JSON syntax and is enclosed between sets of triple dashes (---). Within the title field of the front matter, it is advisable to avoid certain characters to ensure proper parsing and compatibility. Here are the characters that should be avoided in the title of a front matter in a markdown file:

* **Triple Dashes:** Since triple dashes (---) are used to delimit the front matter section in a markdown file, it's important not to include them within the title itself to prevent confusion and ensure the correct interpretation of the front matter boundaries.

* **Colon:** Colons (:) are often used to separate keys and values in YAML or JSON syntax. Including colons within the title might lead to parsing issues and unintended behavior when processing the front matter.

* **Angle Brackets:** Angle brackets (<>) can be misinterpreted as HTML or XML tags within the front matter. To avoid confusion, it's recommended to exclude them from the title.

* **Quotation Marks:** Both single and double quotation marks (' and ") have special meaning in markdown and can affect the rendering or parsing of the front matter title. It's best to avoid them.

* **Backticks:** Backticks (&grave;) are commonly used to denote code or inline code snippets in markdown. Including them in the front matter title can lead to conflicts or misinterpretation.

* **Square Brackets:** Square brackets ([]) are frequently used in markdown for creating links or footnotes. Using them within the front matter title may cause issues with rendering or create confusion.

To ensure compatibility and proper processing of the front matter in a markdown file, <span style="color: #e96113">**it's recommended to stick to alphanumeric characters (A-Z, a-z, 0-9), hyphens (-), and underscores (_) in the title.**</span> These characters are generally safe to use and won't interfere with the structure or parsing of the front matter.