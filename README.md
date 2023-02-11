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

git branch -f master ORIG_HEAD - поверне master назад
а тепер переключимо на master HEAD
git checkout master

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

git checkout -B master fix == git merge

git branch -d fix - удаляєм гілку fix
На самому ділі ми видалили лише ссилку на гілку fix

git branch -D feature - так ми знищуємо гілку і усі комміти що належать цієй гілці, але знищуємо не зразу якщо хочемо відновити гілку то

git branch feature 72861a2

REFERENCE LOG -ФАЙЛ ССИЛОК

cat .git/logs/HEAD - просмотр файла ССИЛОК HEAD

git reflog - виведе значення рефлогів для HEAD

git reflog master - виведе значення рефлогів для master .....

git branch fix HEAD@{8}

git reflog === git log --oneline - g

git reflog --date=iso

git branch fix HEAD@{"2023-02-11 10:34:59 +0200"} -можна вставляти дату але тільки у кавичках бо є пробіли

gc reflogExpire='90 days ago' 90 днів зберігається рефлог, або всього 30 днів якщо гілка знищена

git checkout @{-1} - поверне на гілку на якій ми були до цього, або git checkout -

git checkout -f - поверне HEAD на останній коммит і зробе зброс INDEX
git checkout -f index.html - поверне тільки файл index.html на стан останнього коммиту
git reset --hard - поверне HEAD на останній коммит і зробе зброс INDEX

git clean -dxf удаляєм (-d) не тільки файли але і директорії, (х) -щоб удаляло файли що ігноруються через gitignore, (f) - force бо не буде працювати

$ gti reset --soft @~
git add index.html
git commit -c ORIG_HEAD

git reste --keep -???
git commit -c ORIG_HEAD
