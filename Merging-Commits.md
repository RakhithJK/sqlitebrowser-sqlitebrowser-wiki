If you have created a Pull Request then it is best if you merge or squash all the commits in your fork into one commit.  This helps keep the main repository clean and tidy as well as easier to understand.  This is not to say that multiple commits is wrong in any way.  Often you need them whilst you refine or fix your change, so it is quite normal.  However it is not immediately obvious how you merge all your commits into one, so this is how.

**These steps are a work in progress.** :smile:

*Note - If your fork has been worked on while another change has been made, then it is unclear whether the following still works in exactly the same way.*

At the time of writing the only way to do this is via a command prompt or terminal session.

- In base/root of your local copy execute `git log -5`, where 5 is one more than the number of commits on your fork
- Look for the commit before your first and grab its id, for example `c3c8f8ce568114d7aae1ae263e03390617c7c878`
- Then execute `git reset c3c8f8ce568114d7aae1ae263e03390617c7c878` but using the id you found
- Now you can update your local repository with `git add [filenames]` and then `git commit`, use `git status` to make sure you add everything
- Once you have everything checked in locally, execute `git log -2` and check it is as expected
- Next you need to push your changes to GitHub, but using the "force" option this time: `git push --force`

If you want to read up on `git reset` then please start with <https://www.atlassian.com/git/tutorials/undoing-changes/git-checkout>.