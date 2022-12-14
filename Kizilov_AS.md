#Краткое руководство
***

##Установка

1. _Linux._ Открываем терминал и установливаем приложение при помощи пакетного менеджера вашего дистрибутива. Команда:

* для дистрибутивов, похожих на Fedora, RHEL или CentOS, выполните команду dnf:
> sudo apt install git

* для Ubuntu и других Debian-подобных систем введите apt:
> sudo apt install git

2. _MacOS._ Открываем Терминал и вводим команду:
* если установлен Homebrew
>brew install git

* если Homebrew не установлен, то вводим эту команду. 
> git --version

После этого появится окно, где предложит установить Command Line Tools (CLT). Соглашаемся и ждем установки. Вместе с CLT установиться и git.

3. _Windows._ Проходим, выбираем ОС (32 или 64 битную), скачиваем и устанавливаем.

> https://git-scm.com/download/win

##Настройка

Настроить рабочую среду нужно только один раз. Для этого используется утилита ***git config***. В качестве рабочей среды можно использовать _Visual Studio Code_ (https://code.visualstudio.com/)

Открываем VSC и вводим следующие команды:

> git config --global user.name "<ваше_имя>"
> git config --global user.email "Ваш электронный почтовый ящик"

Проверить, что записано в любой из доступных настроек, можно командой с ключом  _git config key:_

> git config user.email
> git config user.name

##Создание репозитория

Если у вас на компьютере уже есть рабочий проект, но еще не назначен контроль версий, то нужно сначала перейти в каталог проекта и инициализировать репозиторий:

> cd <путь_к_вашему_проекту>
> git init

Добавляем под контроль версий все существующие файлы командой git add . (точка в конце важна!). Можно добавлять и по одному файлу, с помощью git add <имя файла>. 

> git add manual_git.md

И создаем первый коммит:

> git commit -m 'Начало работы над проектом'

Команды "add" и "commit" можно выполнять одной строкой, например:

> git commit -a -m "Начало работы над проектом"

## Основные команды Git

* _git status_ - получить информацию от git о его текущем состоянии;
* _git log_ – вывод на экран истории всех коммитов с их хеш-кодами;
* _git diff_ – увидеть разницу между текущим файлом и закоммиченным файлом
* _git branch <название ветки>__ - создать новую ветку
* _git branch_ - посмотреть список веток в репозитории
* _git branch -d <название ветки>_ – удалить ветку
* _git checkout <название ветки>_ – переход к другой ветке
* _git checkout -b <название ветки>_ - создать ветку и перейти на нее

## Слияние веток
Если нужно применить изменения из дополнительной ветки, их нужно внести в master. Перейдем в master и выполним команду:
> _git merge <дополнительная ветка>_ :

Если над общими участками какого-либо файла успели поработать несколько человек, с этим нужно разбираться вручную. При возникновении ошибок Git помечает общие части файлов из разных веток и сообщает о конфликте.

## Клонирование существующего репозитория
Когда мы работаем в команде, разрабатываемые проекты часто размещают на сервере. Нам нужно получить копию проекта последней версии на свой компьютер, чтобы далее вносить в него свой вклад. Обязательно после клонирования необходимо сделать отдельную ветку, в которую будем вносить правки.

Для наших целей воспользуемся протоколом https и следующей командой:


> git clone https://github.com/DanZDev2/SomeConsoleApp SomeConsoleApp

На нашем компьютере в каталоге, куда мы перешли в командной строке, должен появиться каталог SomeConsoleApp, внутри него — каталог .git и все скачанные файлы репозитория последней версии.

Правила и периодичность обновления могут быть почти любыми, но хорошим тоном обычно считается сохранять рабочую (или промежуточно завершенную) версию. Важное требование для команд разработчиков — возможность сборки проекта, иначе другие участники команды будут вынуждены тратить время на борьбу с ошибками компиляции.

## Файл .gitignore

В рабочий каталог могут попадать файлы, которые вам бы не хотелось отправлять на сервер. Это и документы с вашими экспериментами или образцами, и автоматически генерируемые части проекта, актуальные только на нашем компьютере. Git может полностью игнорировать их, если создать в рабочем каталоге файл с названием .gitignore и внести в него все имена ненужных файлов и папок.

## Отправка изменений в удаленный репозиторий (Push)

Команда для отправки изменений на сервер такова: git push <remote-name> <branch-name>. Если ваша ветка называется master, то команда для отправки коммитов станет такой:

> git push origin master

Она сработает, если у нас есть права на запись на том сервере, откуда мы клонировали проект. Также предполагается, что другие участники команды за это время не обновляли репозиторий.

Следует к тому же помнить, что в разработке для промежуточных правок часто используется не главная ветка (master), а одна из параллельных (например, Dev). Работая в команде, этому обязательно нужно уделять пристальное внимание.

## Получение изменений из репозитория (Pull)
Самый простой и быстрый способ получить изменения с сервера — выполнить команду git pull, которая извлечет (fetch) данные с сервера и попытается встроить/объединить (merge) их с вашей локальной версией проекта. 

На этом этапе могут возникать конфликты версий, когда несколько человек поработали над одними и теми же файлами в проекте и сохранили свои изменения. 

## pull request

В больших компаниях один ответственный за проект создает аккаунт. Другие пользователи дают
команду pull request. Предлагать изменения на GitHub нужно в отдельной ветке. Сначала
пользователь копирует репозиторий на свой компьютер, делает fork репозитория, затем
клонирует версию на своём ПК, создаёт ветку с предлагаемыми изменениями, отправляет
изменения командой push в свой аккаунт на GitHub и даёт команду pull request.

_Делаем   (ответвление) репозитория fork_
_Делаем git clone СВОЕЙ версии репозитория_
_Создаем новую ветку и в НЕЕ вносим свои изменения_
_Фиксируем изменения (делаем коммиты)_
_Отправляем свою версию в свой GitHub_
_На сайте GitHub нажимаем кнопку pull request_