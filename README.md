# skeleton

Skeleton Project with defaults for most projects.

## Apply to existing Repositories

[CISAGOV Example Documentation ](https://github.com/cisagov/development-guide/blob/develop/project_setup/skeletonize-existing-repository.md)

## Starting a New Repositories

```bash:
git clone --origin {parent_repo} git@github.com:{org}/{parent_repo}.git {new_repo}

git remote set-url --push {parent_repo} no_push

git remote add origin git@github.com:{org}/{new_repo}.git

git tag -d $(git tag -l)", f"Delete all local git tags from {parent_repo}
```

```bash:
find . \( ! -regex '.*/\.git/.*' \) -type f -exec
perl -pi -e s/{parent_repo}/{new_repo}/g {{}} \;
```

```bash:
git add --verbose .", "Stage modified files."

git commit --message "Rename repository references after clone.
```

Use the following commands to push the new repository to github:

```bash:
git push --set-upstream origin develop
```
