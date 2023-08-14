# EP 43: 8 Data Structures That Power Your Databases

![rw-book-cover](https://substackcdn.com/image/fetch/w_1200,h_600,c_fill,f_jpg,q_auto:good,fl_progressive:steep,g_auto/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F38f892f0-81f6-41b9-9227-4d6bfa66f9eb_1474x1536.jpeg)

## Metadata
- Author: [[Alex Xu]]
- Full Title: EP 43: 8 Data Structures That Power Your Databases
- Category: #articles
- URL: https://blog.bytebytego.com/p/ep-43-8-data-structures-that-power

## Highlights
- **Git Merge** 
  This creates a new commit G’ in the main branch. G’ ties the histories of both main and feature branches. 
  Git merge is **non-destructive**. Neither the main nor the feature branch is changed. 
  **Git Rebase** 
  Git rebase moves the feature branch histories to the head of the main branch. It creates new commits E’, F’, and G’ for each commit in the feature branch. 
  The benefit of rebase is that it has **linear commit history.** 
  Rebase can be dangerous if “the golden rule of git rebase” is not followed. 
  **The Golden Rule of Git Rebase:** Never use it on public branches! ([View Highlight](https://read.readwise.io/read/01gshbw1c1eak93w4qc00ezsg8))
