# Система конроля версий Git и GitHub

## Что такое git?

Git - одна из распределённых систем контроля версий. Позволяет управлять версионностью 
файлов, откатываться до версий, создавать ветки и их сливать.

## Подготовка репозитория

**Репозиторий** - это хранилище файлов, поддерживающее версионность.
Создать репозиторий можно с помощбю команды *git init*, применённой в папке с будущим 
репозиторием.
Для добавления версионности к файлу используется команда *git add <имя файла>*

## Создание "сохранениями"

Для создания "сохранения" необходимо выполнить фиксацию, она же коммит.
Это можно сделатьс помощью команды *git commit* сдедующим образом: *git commit -a -m "<сообщение>"*. 
Сообщение к коммиту написать **ОБЯЗАТЕЛЬНО**.
Для всех изменённых файлов необходимо использовать *git add* или использовать ключ 
*-а* при коммите

## Журнал изминений

## Перемещение между сохранениями

Перемещаться на тот или иной коммит мы можем с помощью команды *git checkout*. Для 
этого нужно написать *git checkou <номер коммита из истории>*. Для  возврата к самому
последнего коммиту нужно написать *git checkout <название ветки>*. По умолчанию ветка *master*.
Отменять изменения можно с помощью команд *git reset*. Для этого нужно 
написать команду *git revert (reset) <номер коммита>*. Команда git revert перейдёт к 
указанному коммиту, создав новый коммит. А git reset перейдёт указанному состоянию и 
затрёт историю изменений.

## Ветки в git

Если написать *(git branch)* то мы увидим список всех веток, которые у нас есть. 

Чтоб создать новую ветку *git branch (name)*. 

Если мы еще раз напишем git branch, то увидим у нас 2 ветки, но мы все еще находимся на ветке мастер. Чтобы перейти на ветку, которую мы только что создали нужно написать
*git checkout (name)*.

Если же мы перейдем обратно на мастер, для этого мы можем написать
*git checkout master* то наши изменения, которые мы сделали так и останутся на той ветке. 
И пока мы их не вольем в ветку master, она не изменится.

В гите термин вливания ветки в другую ветку называется *merge*. Для того, 
что смерджить нашу ветку *name* в мастер, нам нужно сначала перейти на мастер и потом написать какую ветку мы хотим влить.
Давайте напишем:
*git merge (name)*

Как мы видим, у нас написало, что ветка обновилась и добавился файл. Теперь у нас ветки стали идентичные и добавленный нами функционал находится в мастер ветке. 
Если мы напишем:
*git log* то увидим наш коммит, который мы добавляли на другой ветке. Так как мы ветку уже смерджили и она нам не нужна больше, 
давайте ее удалим.
*git branch -d (name)*.

## Скачивание удалённого репозитория