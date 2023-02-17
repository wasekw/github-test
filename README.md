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

git show --quiet ORIG_HEAD

<!-- .....ФЛАГИ  -->

--pretty=fuller - щоб побачити повну інфу
--reset-author - переписати автора

git commit -C ORIG_HEAD --reset-author
git commit --amend
git commit --amend --no-edit

git diff <commit1> <commit2> - показує різницю між двома коммітами

git diff master fix
git diff maste..fix

$ git diff master...fix

git diff HEAD

git config --global commit.verbose true

$ git log --pretty=format:'%h %cd | %s %d [%an]'

$ git log --pretty=format:'%C(yellow)%h %C(green)%ad | %C(#630f71)%s %d' --date=format:'%F %R'

git config --global pretty.my format:'%C(yellow)%h %C(green)%ad | %C(#630f71)%s %d' --date=format:'%F %R'
$ git log --pretty=my - так визиваємо нашу скорочену log
git config --global format.pretty my скорочуєм виклик log

git config --global log.date format-local:'%F %R' скорочуєм у лозі формат дати

//==============================================================================================//

$ git log fix --graph
$ git log fix ^master
$ git log ..fix = (якщо HEAD вказуэ на master) git log master..fix
$ git log ./css/styles.css - показує в яких комітах були зміни в цьому файлі
$ git log --all --graph

- e041ee0 2023-02-13 12:17 | Merge branch master (HEAD -> master, origin/master)
  |\
  | \* 894a838 2023-02-11 12:23 | Testing deleted trash and work with reset
- | d76ec6e 2023-02-13 12:13 | Added config log
- | eb13479 2023-02-11 15:05 | git diff other
- | 40dee01 2023-02-11 14:21 | Work with amend
- | 90f4725 2023-02-11 12:23 | Testing deleted trash and work with reset plus --amend
  |/
- 436f8e3 2023-02-11 11:25 | Added reflog
- 72861a2 2023-02-11 10:45 | switched between branches
- 1c7d402 2023-02-11 10:34 | Added readme some alias (fix)
- 0cee8eb 2023-02-11 10:21 | new branch fix
- 4c91348 2023-02-11 10:04 | Added readme.md + 3
- cbc7f7e 2023-02-11 09:52 | Added readme.md
- a679960 2023-02-10 14:53 | Added add -p

//==============================================================================//
$ git log --grep readmy
git blame index.html
