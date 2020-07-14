# Case sensitive changes in Git

I ran into an issue where I had to rename a file in git. Usually after renaming the file, `git` will detect the change and as part of the commit operation, detect that a rename is taking place.

Except when the only changes are case-related. For that the solution is to use `git mv` as follows:

```bash
$ git mv -f previousname PreviousName
```