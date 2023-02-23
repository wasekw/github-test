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

--author=имя-автора — позволяет вывести коммиты от определённого автора. Когда в команде работает несколько человек, бывает трудно найти коммиты определённого сотрудника, а эта опция решает данную проблему. Имя автора при этом отмечается красным цветом.

--graph — дополнительно к стандартному выводу команды git log показывает ASCII-граф, в котором отображается история ветвлений и слияний

--after=дата — выводит коммиты, которые были сделаны после определённой даты. У этой команды есть аналог — опция --since=дата. Она выводит то же самое, что и --after=дата. Возможно, кому-то понравится запись через --since=дата, но чаще используют --after=дата. Во-первых, потому что привыкли. Во-вторых, есть ещё и --before=дата. При упоминании --before=дата явно будет проще вспомнить --after=дата, нежели --since=дата

git log --stat --abbrev-commit --relative-date --graph

у команды git push есть опция --force (сокращённо -f), которая принудительно отправляет изменения в удалённый репозиторий, игнорируя многие предупреждения и ошибки

Для первой отправки изменений пропишем команду вместе с опциями git push --set-upstream origin main. Но чаще всего используют сокращённую версию — git push -u origin main. То есть опция --set-upstream заменяется сокращённой -u

нужно сначала выбрать изменения, которые относятся к одной задаче и закоммитить их, а потом повторить всё то же самое для другой задачи. В этом вам поможет команда git add с опцией -p (развёрнуто --patch)

git add -p
Что делает каждая буква:

y — добавляет одну часть изменений в индекс.
n — не добавляет одну часть изменений в индекс.
q — выходит из этого режима и не добавляет никаких изменений в индекс.
a — добавляет все части изменений в индекс.
d — не добавляет все части изменений в индекс.
s — разбивает текущий фрагментy кода на более мелкие куски (то, что нам нужно).
e — позволяет вручную отредактировать часть кода (открывает дополнительное окно редактора), а затем добавляет изменения в индекс.
? — выводит справку по каждой букве (на латинице).

Изменения разбились на четыре мелкие части. Также у нас появились дополнительные буквы, которые тоже сейчас разберём.

j — откладывает часть изменений (на случай, если вы не знаете, что пока с ней делать) и переходит к следующей такой же отложенной части. Если отложенной части нет, то просто переходит к следующей части.
J — откладывает часть изменений и переходит к следующей части. Тут важно понимать разницу: при вводе этой буквы перебрасывает к следующей части, а при вводе маленькой j перебрасывает к следующей отложенной части, если такая есть.
g — позволяет перейти к определённой части (нужно будет ввести номер).
/ — поиск части по заданному регулярному выражению.

git add с опцией -u (более развёрнуто --update). Она позволяет обновить статус отслеживаемых файлов, изменённых и удалённых. То есть у файлов со статусом untracked статус не будет обновлён.

git commit -am "текст коммита"

сли вам нужно отредактировать последний коммит, воспользуйтесь командой git commit --amend -m "новый текст последнего коммита". Если вам не нужно редактировать текст последнего коммита, то просто пропишите git commit --amend --no-edit

git push -u origin master - отправим изменения в удалённый репозиторий

git pull = git pull origin master - Также затягивать изменения можно с определённой ветки при помощи всё той же команды, но с добавлением локального псевдонима и названия ветки

Когда мы активируем команду git pull, мы не просто затягиваем изменения с удалённого репозитория, а выполняем слияние удалённой ветки с локальной

команды git pull также есть свои опции. Например, --ff и --ff-only отвечают за fast-forward, а --no-ff — за no-fast-forward. В большинстве случаев эти опции не используются, разве что --ff-only

Команда git pull — сочетание двух команд: git fetch и git merge
Мы могли бы сначала прописать git fetch и получить изменения с удалённого репозитория, но при этом наша рабочая копия не была бы обновлена. А потом выполнили бы git merge для слияния удалённой ветки с локальной.

//============================================================================================================//

git config --system init.defaultBranch master - командa для изменения названия ветки по умолчанию

Если у вас Windows, то системная конфигурация находится по пути C:\Program Files\Git\etc\gitconfig

git branch develop - создадим новую ветку с названием develop
git checkout -b develop - Чтобы создать новую ветку и сразу на неё переключиться, нужно воспользоваться командой
git switch --create develop - Вместо --create можно указать сокращение -c - оздать новую ветку и сразу на неё переключиться
git push --set-upstream origin develop

git switch - команда позволяет переключиться только на предыдущую ветку, то есть на ту, на которой вы находились до текущей ветки

git branch -l. Это то же самое, что и git branch. Только в этом случае мы явно указываем с помощью опции -l (более развёрнуто --list), что нам нужно показать только локальные ветки

Также с помощью этой команды можно дополнительно в кавычках после опции указать шаблон для поиска веток, например: git branch -l "task-\*". Тогда будут выведены лишь те ветки, которые начинаются с task-

git branch --remotes = git branch -r - Для просмотра всех удалённых веток существует команда

git branch --all = git branch -a - Чтобы посмотреть все ветки сразу, и локальные, и удалённые

git branch -m [<старое-название-ветки>] <новое-название-ветки> - В этом случае нужно указать старое название, то есть develop, а затем через пробел указать новое.

Чтобы посмотреть, какие изменения были затянуты, порой нужно перейти на удалённую ветку — именно туда они и затягиваются. Это можно сделать несколькими способами:

через команду git checkout <название-ветки>;
через git switch --detach <название-ветки>.
На неё мы и будем переключаться с помощью команды git switch --detach origin/main

//==========================================================================================================//

Чтобы первый раз отправить ветку со всеми коммитами в удалённый репозиторий, нужно выполнить команду git push --set-upstream origin develop или воспользоваться более сокращённой версией — git push -u origin develop

git branch -d hotfix = git branch --delete hotfix - команду для удаления ветки в локальном репозитории
git branch -D <название-ветки>.

Её можно расписать двумя способами:

git branch -d -f <название-ветки>,
git branch --delete --force <название-ветки>.
Данная команда принудительно удаляет ветку. Если бы в нашей ветке было много изменений, то без слияния, просто используя опцию --delete, мы бы не могли её удалить. Git выдал бы ошибку. Но порой бывает ситуация, когда ветки не нужно объединять — только удалить. Для таких случаев и используют опцию -D или, если использовать развёрнутую запись, --force. Она отвечает за принудительные действия.

//==============================================================================================================//

git log --oneline --no-decorate. Опция --no-decorate убирает названия веток, на которых присутствуют коммиты, а также указатели.

git push --all - команда отправляет изменения со всех существующих веток,

По умолчанию, если не использовать опцию -m, Git сам напишет коммит в стиле Merging with develop. Нас это не устраивает, поэтому мы будем использовать опцию -m, чтобы самостоятельно написать коммит.

git merge --no-ff develop -m "feat: the develop branch is merged into the main branch"

При отправке изменений автоматически добавляется опция --ff-only — то есть, если fast-forward не доступен, Git отменяет отправку либо выдаёт ошибку

Пропишем команду из ветки main — git branch --delete develop
Теперь удалим ветку в удалённом репозитории с помощью команды git push --delete origin develop

опция --squash. Она позволяет сжать коммиты и создать из них один.

Объединим ветки с использованием режима no-fast-forward. Воспользуемся командой git merge feature --no-ff --message "feat: the feature branch merges into the main branch"

Если вы хотите выбрать изменение, пришедшее с conflict/command-line, воспользуйтесь командой git checkout --their index.html. Если хотите выбрать изменение, которое было на ветке main, используйте команду git checkout --ours index.html

Опция --their отвечает за входящие изменения,
а опция --ours — за принятие изменений, которые были сделаны в текущей (целевой) ветке

Давайте добавим изменение в индекс с помощью команды git add --all.
еперь у нас есть два варианта развития событий.

Мы можем самостоятельно создать коммит с помощью команды git commit --message "текст коммита".
Мы воспользуемся командой git merge --continue. Она позволяет продолжить слияние, поэтому у нас будет создан коммит с текстом, который мы указывали, когда прописывали команду слияния.
git

//////////////////////===================================================//////////////////////////////

[merge]
tool = vscode
[mergetool "vscode"]
cmd = code --wait --merge $REMOTE $LOCAL $BASE $MERGED
[mergetool]
keepBackup = false

В [merge] с ключом tool мы указали редактор кода vscode как инструмент по умолчанию.
В разделе [mergetool "vscode"] с ключом cmd мы указали, что после написания команды git mergetool должна открыться новая вкладка в редакторе кода VS Code для решения конфликта.
В разделе [mergetool] с ключом keepBackup мы установили значение false, что означает «не нужно сохранять резервные копии после решённых конфликтов».
Пропишем в поиске git.mergeEditor.

git rebase:

Берёт все новые созданные коммиты из переданной ветки (та, что будет указана после команды), которые появились после создания дополнительной ветки.
Затем копирует коммиты из текущей ветки — та, в которой мы находимся.
Вставляет эти коммиты на вершину переданной ветки. При этом коммиты, которые были сделаны на текущей ветке, будут иметь другой хэш. Это мы и можем наблюдать на рисунке ниже. Изначально у трёх коммитов, сделанных на ветке develop, были хэши 74da, a82c и f52e. После перебазирования хэши стали другими: 56df, 7de2 и 252f. При этом старые коммиты сохранились, и на них указывает указатель ORIG_HEAD. Это нужно, чтобы была возможность откатить перебазирование и вернуть всё как было.

Давайте посмотрим на хэш последнего коммита. Для этого воспользуемся командой git log --oneline -1
$ git log --oneline -1
c9d9fd7 (HEAD -> task/rebase) feat: added the class attribute for the body element

Вводим основную команду — git rebase main
