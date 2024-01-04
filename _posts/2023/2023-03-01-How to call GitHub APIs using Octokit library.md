---
title: How to call GitHub APIs using the Octokit library
author: jeny-qed
categories: [public]
tags: [technology]
date: 2023-04-19 05:11:39
updatedBy: jayarvee
updated: 2023-05-11 03:59:25
likes: 0
---

To call the GitHub API using the **Octokit** library, you first need to install it in your project by running the following command in your terminal:

```
npm install @octokit/rest
```

Once you have installed **Octokit**, you can create a new instance of the **Octokit** REST client and use it to make API requests. Here's an example of how to create a client and get information about a user:

```
const { Octokit } = require("@octokit/rest");
const octokit = new Octokit();

octokit.users.getByUsername({
 username: "octocat"
}).then(({ data }) => {
 console.log(data);
}).catch((error) => {
 console.error(error);
});
```

In this example, we create a new instance of the **Octokit** client, and then use the getByUsername method to get information about a user with the username "octocat". The result of the API call is returned as a Promise, which we handle using the then and catch methods.

You can use other methods provided by **Octokit** to interact with other parts of the GitHub API, such as creating repositories, managing issues, and more. The **Octokit** documentation provides detailed information about all available methods and how to use them.