# Manually import repo with history
In this example we assume we want to bring the repo from Github to Bitbucket
```sh
# Clone the source and fetch all
git clone <Github URL>
git fetch --all

# Checkout all branches
for remote in `git branch -r | grep -v main `; do git checkout --track $remote ; done

# [Optional] If there are large files
git lfs fetch origin --all

# Update the origin to be bitbucket
git remote set-url origin <BitBucket repo address>

# Push all
git push --all --force
git push --tags

# [Optional] If there are large files
git lfs push --all
```