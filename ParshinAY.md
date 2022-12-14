ОСНОВНЫЕ КОМАНДЫ "GIT"

_GIT ADD - это первая команда в цепочке операций, предписывающей Git «сохранить» снимок текущего состояния проекта в истории коммитов._

GIT COMMIT - берёт все данные, добавленные в индекс с помощью git add, и сохраняет их слепок во внутренней базе данных, а затем сдвигает указатель текущей ветки на этот слепок.

**GIT STATUS - показывает состояния файлов в рабочем каталоге и индексе: какие файлы изменены, но не добавлены в индекс; какие ожидают коммита в индексе. Вдобавок к этому выводятся подсказки о том, как изменить состояние файлов.**

GIT DIFF - используется для вычисления разницы между любыми двумя Git деревьями. Это может быть разница между вашей рабочей копией и индексом (собственно git diff), разница между индексом и последним коммитом (git diff --staged), или между любыми двумя коммитами (git diff master branchB).

**_GIT LOG - по умолчанию (без аргументов) git log перечисляет коммиты, сделанные в репозитории в обратном к хронологическому порядке — последние коммиты находятся вверху._**

GIT CHECKOUT - используется для просмотра и внесения изменений в различные ветви репозитория.

![GitHub](/GitHub.jpg "GitHub")

СПИСОК НОВЫХ КОМАНД:

- GIT BRANCH - позволяет создавать, просматривать, переименовывать и удалять ветки.

- GIT MERGE - выполняет слияние отдельных направлений разработки, созданных с помощью команды git branch, в единую ветку.

- ~~GIT BRRR - нет такой команды!~~

**Git применяется для управления версиями в рамках колоссального количества проектов по разработке ПО, как коммерческих, так и с открытым исходным кодом.**

НОВЫЕ КОМАНДЫ ИЗ ТРЕТЬЕГО СЕМИНАРА (НУМЕРОВАННЫМ СПИСКОМ):

1. GIT REMOTE ADD - используется для создания записи о новом подключении к удаленному репозиторию. После добавления удаленного репозитория имя можно использовать в качестве удобного ярлыка для адреса в других командах Git.

2. GIT CLONE — это утилита командной строки Git для выбора существующего репозитория и создания его клона, т. е. копии. На самом деле git clone работает как обёртка над некоторыми другими командами. Она создаёт новый каталог, переходит внутрь и выполняет git init для создания пустого репозитория, затем она добавляет новый удалённый репозиторий (git remote add) для указанного URL (по умолчанию он получит имя origin), выполняет git fetch для этого репозитория и, наконец, извлекает последний коммит в ваш рабочий каталог, используя git checkout.

3. GIT PUSH - эта команда используется для выгрузки содержимого локального репозитория в удаленный репозиторий. Она позволяет передать коммиты из локального репозитория в удаленный.

4. GIT FETCH - этой командой git собирает все коммиты из целевой ветки, которых нет в текущей ветке, и сохраняет их в локальном репозитории. Однако он не сливает их в текущую ветку. Это особенно полезно, если вам нужно постоянно обновлять свой репозиторий, но вы работаете над функциональностью, неправильная реализация которой может негативно сказаться на проекте в целом. Чтобы слить коммиты в основную ветвь, нужно использовать merge.

5. GIT PULL - используется для извлечения и загрузки содержимого из удаленного репозитория и немедленного обновления локального репозитория этим содержимым. Можно также сказать, что git pull - это шоткод для последовательности двух команд: git fetch (получение изменений с сервера) и git merge (сливание в локальную копию).
