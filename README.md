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

//===================================================================================//

$ git diff --name-only master fix
README.md

$ git merge-base master fix
1c7d402f5c4787a136d898bce4c293e53c439e85

//============================================================================================

git config --system core.safecrlf warn - он выдаст предупреждение, но не отменит операцию как Git будет обрабатывать окончания строк в текстовых файлах

git config --system core.quotepath off - По умолчанию символы, которые не относятся к таблице ASCII, будут отображаться в виде восьмеричной последовательности, а также в формате Quoted String, то есть в кавычках. Убирает проблеми з відтворенням кі

C:\Users\user>git config --list --global
filter.lfs.smudge=git-lfs smudge -- %f
filter.lfs.process=git-lfs filter-process
filter.lfs.required=true
filter.lfs.clean=git-lfs clean -- %f
user.email=vasiliy.volobaev@gmail.com
user.name=Vasiliy Volobaev
alias.hist=log --pretty=format:'%h %ad | %s%d [%an]' --graph --date=short
alias.co=checkout
alias.ca=commit -am
alias.st=status
alias.br=branch
alias.type=cat-file -t
alias.dump=cat-file -p
alias.s=status --short
alias.a=add .
alias.cg=config
core.editor=vim --nofork
commit.verbose=true
pretty.my=format:%C(yellow)%h %C(green)%ad | %C(#630f71)%s %d
format.pretty=my
log.date=format-local:%F %R

C:\Users\user>git config --list --system
diff.astextplain.textconv=astextplain
filter.lfs.clean=git-lfs clean -- %f
filter.lfs.smudge=git-lfs smudge -- %f
filter.lfs.process=git-lfs filter-process
filter.lfs.required=true
http.sslbackend=openssl
http.sslcainfo=C:/Program Files/Git/mingw64/ssl/certs/ca-bundle.crt
core.autocrlf=true
core.fscache=true
core.symlinks=true
core.usebuiltinfsmonitor=true
core.safecrlf=warn
core.quotepath=off
pull.rebase=false
credential.helper=manager-core
credential.https://dev.azure.com.usehttppath=true
init.defaultbranch=master

git config --list --global --show-origin

//=======================================================================================================//

git remote add origin
Эта команда добавляет удалённый репозиторий с названием origin. Обязательно ли должно быть название origin? Нет, оно может быть любым, но origin — уже устоявшееся название, которое можно перевести как «источник».

$ git remote
origin

git remote get-url origin для отримання url адреси origin
git remote -v

git remote add academy url-адрес

git remote set-url --add origin url-адрес - В итоге можем отправлять изменения на второй удалённый репозиторий, используя не только локальный псевдоним academy, но теперь ещё и origin

git remote remove academy - Этой командой мы говорим: «Удали локальный псевдоним academy и связь с удалённым репозиторием»

git remote set-url --delete origin url-адрес - удалим данный репозиторий из origin

git remote set-url origin url-адрес - И вы хотите обновить URL-адрес, но так, чтобы при этом не удалять локальный псевдоним и потом снова его устанавливать тільки після видалення віддаленого репозиторія

git remote rename origin academy - Теперь переименуем origin в academy

//=========================================================================================================//

git status есть опция --short, или сокращённо -s, которая выводит информацию о статусах файлов в укороченном формате

Вторая команда для добавления файлов — git add :/. Ей неважно, в какой директории вы находитесь, она добавит в индекс все файлы

git add -A (более развёрнуто git add --all) or git add --no-ignore-removal точно так же добавляют все файлы в индекс, независимо от того, в какой директории вы находитесь

если вам нужно добавить все файлы только определённой директории в индекс, то можете воспользоваться командой git add название-директории/. Например: git add source/

$ git log --oneline
89a84d9 (HEAD -> master) Added two files

$ git log --stat
89a84d9 2023-02-21 16:48 | Added two files (HEAD -> master)
index.html | 10 ++++++++++
learning/text.txt | 1 +
2 files changed, 11 insertions(+)

--shortstat — уменьшенная версия опции --stat. Она выводит только общее количество изменённых файлов и количество изменённых строк. На наш взгляд, опция --stat полезнее,

--name-only — выводит то же самое, что и команда git log, а также дополнительно список изменённых файлов.

--name-status — улучшенная версия --name-only. Выводит названия изменённых файлов и статус, который у них был на момент коммита. Позволяет отследить, какие файлы были добавлены или удалены.

--abbrev-commit — выводит то же самое, что и команда git log, но вместо длинного хэша будет короткий, как при использовании опции --oneline

--relative-date— выводит то же самое, что и команда git log, только показывает дату в относительном формате,

-p — позволяет посмотреть не только то, что выводит обычная команда git log, но ещё и показывает, какие конкретно изменения были сделаны в каждом коммите.

Сначала ставится -, а после без пробела пишется цифра. Цифра указывает, какое количество последних коммитов нужно отобразить. У неё точно такой же вывод, как и у команды git log
