# **Инструкция по работе с Git**

Git (произносится «гит») — распределённая система управления версиями. Проект был создан Линусом Торвальдсом для управления разработкой ядра Linux, первая версия выпущена 7 апреля 2005 года. На сегодняшний день его поддерживает Джунио Хамано.

## Создание фотального репозитория

Для того,чтобы создать (инициализировать) локальный репозиторий необходимо в терминале,находясь в папке проекта набрать команду:

    git init

## Проверка состояния репозитория

Чтобы проверить состояниие репозитория используют комунду:

    git status

## Добавление версионности

## Чтобы добавить отслеживание изменения необходимо использовать команду:

    git add <имя_файла>

Где вместо <имя_файла> птшется поллное имя файла,в котором быди произведены изменения.

## Фиксация изменений 

Чтобы зафиксировать изменения (добавленные раннее к отслеживанию) необходимо использовать команду:

    git commit 

В этом случае откроется окно для ввода краткого сообщения о фсоздаваемом коммите.

Чтобы ввести краткое сообщение в процессе создания коммита необходимо использовать эту же команду с дополнительной опцией:

    git commit -m "сообщение"

## Просмотр истории коммитов

Чтобы посмотреть историю изменений (коммитов) используется команда:

    git log

Для отображения лога в кратком виде (один коммит - одна строка) используется та же команада с опцией:

    git log --oneline

Для отображения всех коммитов (вне зависимоти от того на какой из них мы сейчас переключены) используется команда:

    git log --all

Данные опции можно комбинировать.

## Переключения между версиями

Чтобы переключится на другую (ранее сохранённую) версию репозитория использется команда:

    git checkout <hash>

где hash - это идентификатор коммита, показываемый в логе.

## Просмотр различий между коммитами

Для просмтора различий между разными версиями репозитория используется команда:

    git diff <hash1> <hash2>

При этом если ввести команду

    gid diff

без параметров - будет показана разница между текущим состоянием репозитория и последним закомиченным.

## Ветвления

Ветвления нужны для для того,чтобы  редактировать файл в режиме черновика (новых ветках) без изменений в главной ветке. При необходимости финформация из черновиков(других веток) может быть добавлена в основную ветку.

### Созданеи новой ветки

Для того, чтобы создать новую ветку необходимо ввести следующую команду:

    git branch <branch_name>

## Объединение веток
Для того, чтобы информацию из одной ветки добавить в другую, перейдите в ту ветку, куда вы хотите добавить информацию и в команде, указанной ниже, используйте имя той ветки,откуда вы хотите подтянуть информацию:

    git merge <merge_name>

## Разрешение конфликтов при объединении веток

Объединение пройдёт гладко, если в ветке, которую мы присоединили есть какая то дополнительная информация по отношению в основной ветке, а все остальные  строки документа одинаковые.
Если на одних и тех дже строках в обеих строказх есть различающаяся информация, при обхелинении возникает конфликт. Visual Studio Code предлагает несколько путей решения:

1. Принять информацию из основной ветки (к которой мы присоединяем другю ветку). В этом случае информация из присоединемой ветки будет утеряна.
2. Принять информацию из присоединяемой ветки. В жтом случае информация тз основной ветки (к которой мы присоединяем другую ветку) будет утеряна.
3. Принять изменения из обеих веток. Информация объединится последовательно: сначала из основной ветки,затем из присоединяемой.
4. Принять измененияс корректировкой. В этом случае можно внести необходимые корректировки и только затем принять какую то версию.

После объединения веток может потребоваться коммит.
### Удаление веток

Когда вся информация из веток перенесена в главную ветку и необходимость в данной ветке отпадает, удалите ветку, используя следующую команду:

    git branch -d <branch_name>

## Удаленные репозитории

Удаленные репозитории нужны для совместной удаленной работы.

### Загрузка новых изменений в новый репозиторий

Для того, чтобы загрузить сделанные локально изменения в удаленный репозиторий нужно использовать команду:

    git push

