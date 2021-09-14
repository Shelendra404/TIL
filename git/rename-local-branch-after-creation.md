# Rename local branch after creation

Let's say you created a repo on the github website and its name gets automatically set to 'main'.
If you are used to naming it i.e. 'production', you need to rename it first from the website
and then run the following line in the project folder:

```
git branch -m main production && git fetch origin && git branch -u origin/production production && git remote set-head origin -a
```