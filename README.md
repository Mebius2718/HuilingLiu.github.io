# Mebius2718.github.io
Huiling's Homepage

## Project setup
```bash
git pull
```

## Compiles and hot-reloads for development
```bash
hugo serve
```

## Typical scenario
```bash
git pull
git branch my-new-branch-name
git checkout my-new-branch-name

# ...
# modify source code
# ...

# make sure everything looks good locally:
hugo serve
# generate `docs/` files and add them to git:
./build.sh

# add new/modofied/removed files
git add .

# commit changes locally
git commit -m "version"

# push to github:
git push --set-upstream origin my-new-branch-name
```
This will create a new branch on github, which you can then make a pull request for on github. Once your branch is pulled into `main`, the [My Homepage](https://Mebius2718.github.io/) website will be automatically updated within a few minutes.