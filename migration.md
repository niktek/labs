Add the subtree - normally brings entire history, --squash removes that and does a shallow clone
git subtree add --prefix packages/skeleton https://github.com/niktek/skeleton.git main --squash

git remote add -f skeleton https://github.com/niktek/skeleton.git

Supposedly shorter version of adding it now that it is an added remote
git subtree add --prefix packages/skeleton skeleton chore/fixed-imports-and-references --squash

To pull updates:
git fetch skeleton chore/fixed-imports-and-references
git subtree pull --prefix packages/skeleton/ chore/fixed-imports-and-references --squash

To push updates - looks like set it to a fork
git remote add durdn-vim-surround ssh://git@bitbucket.org/durdn/vim-surround.git

git subtree push --prefix=packages/skeleton skeleton chore/fixed-imports-and-references