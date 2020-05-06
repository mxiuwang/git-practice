Scenario 2: Other Intuit engineers have made changes to master, and you must rebase your changes on top of theirs."
- master branch moves on, but your changes do not cause any merge conflicts 
- you must rebase your changes on top of the lastest master, which includes all the other engineer's changes.

Code on your local machine:

Branch: master (local)
Line 1 
Line 2 

[You make a copy of master called "your-branch"]

Branch: your-branch
Line 1 
Line 2
Line 3A - Added by you 

[Meanwhile, master branch has moved on]

Branch: master
Line 1
Line 2

Line 3B - Added by another engineer  

You want upstream master to look like this:

Branch: master (upstream)
Line 1
Line 2 
Line 3A - Added by you
Line 3B - Added by another engineer 