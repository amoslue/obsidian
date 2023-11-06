# Rewriting Your Git History, Removing Files Permanently [Cheat Sheet Included]

![rw-book-cover](https://blog.gitguardian.com/content/images/2020/12/20W22-BLOG-Banner-BestPractices-Final.png)

## Metadata
- Author: [[GitGuardian Blog - Automated Secrets Detection]]
- Full Title: Rewriting Your Git History, Removing Files Permanently [Cheat Sheet Included]
- Category: #articles
- URL: https://blog.gitguardian.com/rewriting-git-history-cheatsheet/?_gl=1*nuf9u5*_up*MQ..*_ga*ODM2OTQyMDAxLjE2OTg5MjYzNTk.*_ga_L0Y8CSL3HQ*MTY5ODkyNjM1Ni4xLjAuMTY5ODkyNjM1Ni4wLjAuMA..

## Highlights
- This is where the `--all` flag comes in. This flag tells git to grab every branch from the remote repository. And the `--tags` flag tells git to grab every tag as well. So this command tells git to download the entire repository history, a complete and total clone. ([View Highlight](https://read.readwise.io/read/01he7zyeg23jevz7kp35t89cfg))
- git reset --hard HEAD~1 ([View Highlight](https://read.readwise.io/read/01he8007scxn5f1r7zwkqzaqda))
- Normally, this command by itself tells git to unstage anything we’ve added with `git add`, but haven’t committed yet. ([View Highlight](https://read.readwise.io/read/01he8018npst261184m2gkncrr))
    - Note: git reset
- `HEAD` is what git calls the most recent commit on the checked out branch. ([View Highlight](https://read.readwise.io/read/01he802rw09hsxsksa7zrgddah))
- `HEAD~1` means “the first commit prior to the most recent” (likewise `HEAD~2` means “two commits prior to the most recent”). ([View Highlight](https://read.readwise.io/read/01he803n6zjfnnz9q8r48t9gpj))
- Finally, the `--hard` tells git to throw away any differences between the current state and the state we’re resetting to ([View Highlight](https://read.readwise.io/read/01he806zfhav77s8b4j7c3ywgb))
- We all know `git commit`, but the `--amend` flag is our friend here. This tells git that we want to edit the previous commit, rather than creating a new one ([View Highlight](https://read.readwise.io/read/01he80zd8gjkkwz8bmk2vafey3))
    - Note: git --amend
