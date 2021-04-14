# Revision
# Point: 200
# Description

Revision
200
... They aren’t necessarily obvious but are helpful to know.

http://git.ritsec.club:7000/Revision.git/

~knif3


# Solution
This was a fun challenge. So basically speaking, this challenge take advantage of the fact that a commit
may not always be found using git log, git log -p -2 or git log -a for that matter. This is due to the fact that
a commit might have been rebase and become "1" commit and among other. In order to view the entire history of a git
we can use 

``git rev-list [<options>] <commit>…​ [[--] <path>…​]``

Given that I have never used this particular command before, I did a bit dig around and I found that I could see all commit by
running this command

```git rev-list --all```

The result was what I expected it to be, it was really long given that it contain the entire history. Based on the the fact
that the author was knif3, I figured that I could some how sort by author as follow 

```git rev-list --all --header --author 'knif3@mail.rit.edu>'```

Upon getting the commits that belong to knif3, I checkout couple commit and surely the flag.txt was in those commit.
To make it even interesting, knif3 pushed each letter of the flag in a commit by themselves in the reverse order :-) initally I was going to do it manually
but after doing a few manually, I decided to write a script that will get the flag and concat them together. Inside
the commit.txt is just list of all commit that was obtain from the git rev-list

```python

import git
import os

repo_clone_url = "http://git.ritsec.club:7000/Revision.git/"
local_repo = "Revision"


repo = git.Repo.clone_from(repo_clone_url, local_repo)
commits = open('commit.txt', 'r')
os.chdir('/home/cypher/Desktop/foo/'+local_repo)

screw_you = ""
for commit in commits:
	repo.git.checkout(commit.strip())
	try:
		flag = open(os.getcwd()+'/flag.txt','r')
		for line in flag:
			screw_you+=line.strip()
	except:
		pass


print(screw_you[::-1])
```

# Flag
RS{I_h0p3_y0u_scr1pted_th0s3_git_c0ms}

# Exploit / Lessons
Sometime sensitive information may still be in a .git, you just have to know where to look :-) It may have not
been proper deleted





