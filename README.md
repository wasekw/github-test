# github-test

# It is my first testing github platform

//-===============================================================================

git config --global core.editor "vim --nofork"

//====================================================================================

$ git show --pretty=fuller

$ git add -f .idea/project.html

git add -p index.html

git checkout --force HEAD

git checkout -f HEAD

cat ~/.gitconfig - просмотр в редакторе локального файла .gitcnfig

git checkout master
git merge fix - слить ветку мастер с веткой fix

fast-forward - перенос указателя ветки master на последний коммит ветки fix

git branch -f master a43102a - передвинути гілку master на коммит a43102a

Перед командою merge git записує останній ідентифікатор master в .git/ORIG_HEAD

$ git config --global alias.p 'push'
$ git config --global -l
$ git config --global alias.st 'status -sb'
$ git config --global alias.ll 'log --oneline'
$ git config --global alias.last 'log -1 HEAD --stat'
$ git config --global alias.cm 'commit -m'
$ git config --global alias.rv 'remote -v'
$ git config --global alias.d 'diff'
$ git config --global alias.dv 'difftool -t vimdiff -y'
$ git config --global alias.gl 'config --global -l'
$ git config --global alias.se '!git rev-list --all | xargs git grep -F'

cat .git/ORIG_HEAD
