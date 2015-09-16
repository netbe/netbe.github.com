---
title: Code review
---

Recently I have worked on projects where code review is not a vague idea but truly part of the development process. I am glad it finally happen and always wished it to be formalized that way. Before, code review was done with my peers, just checking out each other's branch having a global look and ending up saying "yeah that's ok".

At final, I ended up not saying that much on the work done because I could directly see the look on the developer whose code I was reviewing and how he was accepting my remark. Moreover I was really focus on formatting code and wanted that the team's work looks homogeneous, like each developer's style disappear behind a coding style.

Now, I have reassessed my point of view, and I am more focus on *does this work?* than *does it conform to our style guide?*. And I think this is good how code review should be.

![Maslow’s pyramid of code review](http://36.media.tumblr.com/72e7200921159a4374b7fc163fe0f6f2/tumblr_njwlh7rZui1qgj0nao1_400.png)

[Source](http://blog.d3in.org/post/111338685456/maslows-pyramid-of-code-review)

On my two last projects, we used the client's infrastructure and therefore different tools :

## Stash

Stash from Atlassian is similar to what you can find on Github with Pull Requests. We used it with Jira for tasks and user-stories development which works seamlessly together. The workflow went like this:

* Developer A works on a story which is on a dedicated branch.
* Developer A creates pull requests for each subtasks of the story to be included in the branch.
* The CI (Team City) verifies the PR
* Developer B and C needs to approve the PR. They comment on code and Developer A can adjust code there.


## Gerrit

Gerrit is a tool to review commits and use special ids (Change-ids) included in the commit message (body) to track what to review.
