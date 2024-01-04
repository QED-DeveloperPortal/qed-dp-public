---
title: How to raise a pull request to GitHub repo using Octokit library
author: jeny-qed
categories: [public]
tags: [technology]
date: 2023-03-01 12:00:00
updatedBy: sushma-hazari-qed
updated: 2023-04-20 02:20:01
likes: 0
---

**To raise a pull request in a GitHub repository using the Octokit library** in C#, you can use the PullRequestCreate method of the PullRequestsClient class. This method creates a new pull request in the specified repository with the specified title, body, and head branch.

Here's an example of how to use this method to create a new pull request:

```
using Octokit;

var client = new GitHubClient(new ProductHeaderValue("MyApp"));
var tokenAuth = new Credentials("YOUR_PERSONAL_ACCESS_TOKEN");
client.Credentials = tokenAuth;

var newPullRequest = new NewPullRequest("My new pull request", "my-feature-branch", "main")
{
    Body = "This is my pull request body"
};

var pullRequest = await client.PullRequest.Create("octocat", "hello-world", newPullRequest);

Console.WriteLine(pullRequest.HtmlUrl);
```

In this example, we create a new instance of the GitHubClient class with a personal access token, and then use the PullRequest.Create method of the PullRequestsClient object to create a new pull request in the hello-world repository owned by the user octocat. The NewPullRequest object specifies the title, head branch, and base branch of the pull request, as well as an optional body.

The **PullRequest.Create** method returns an object of type PullRequest, which contains information about the newly created pull request, including the URL, which we access using pullRequest.HtmlUrl.

Note that in the example above, we are passing the personal access token as the Credentials property of the GitHubClient object. However, for more secure authentication, it's recommended to use the GitHubClient.Credentials.GetCredentials() method to retrieve credentials from the user's system credential store.

