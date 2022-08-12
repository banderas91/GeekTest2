# Инструкция для работы с Git и удалёнными репозиториями

## Что такое Git?
Git - это одна из реализаций распределённых систем контроля версий, имеющая как и локальные, так и удалённые репозитории. Является самой популярной реализацией систем контроля версий в мире.
## Подготовка репозитория
Для создание репозитория необходимо выполнить команду *git init*  в папке с репозиторием и у Вас создаться репозиторий (появится скрытая папка .git)

## Создание коммитов

### Git add
Для добавления измений в коммит используется команда *git add*. Чтобы использовать команду *git add* напишите *git add <имя файла>*

### Просмотр состояния репозитория
Для того, чтобы посмотреть состояние репозитория используется команда *git status*. Для этого необходимо в папке с репозиторием написать *git status*, и Вы увидите были ли измения в файлах, или их не было.

### Создание коммитов
Для того, чтобы создать коммит(сохранение) необходимо выполнить команду *git commit*. Выполняется она так: *git commit -m "<сообщение к коммиту>*. Все файлы для коммита должны быть ***ДОБАВЛЕНЫ*** и сообщение к коммиту писать ***ОБЯЗАТЕЛЬНО***.

## Перемещение между сохранениями
Для того, чтобы перемещаться между коммитами, используется команда *git checkout*. Используется она в папке с hепозиторием следующим образом: *git checkout <номер коммита>*

## Журнал изменений
Для того, чтобы посмтреть все сделанные изменения в репозитории, используется команда *git log*. Для этого достаточно выполнить команду *git log* в папке с репозиторием

## Ветки в Git

### Создание ветки

Для того, чтобы создать ветку, используется команда *git*. Делается это следующим образом в папке с репозиторием: *git branch <название новой ветки>*

## Слияние веток

Для того чтобы дабавить ветку в текущую ветку используется команда *git merge <name branch>*
ение веток
Для удаления ветки ввести команду "git branch -d 'name branch'"

# Домашняя работа

***Дополнительные* команды берутся с ресурса** [Хабр](https://habr.com/ru/company/ruvds/blog/599929/)

![30 основных команд](https://habrastorage.org/r/w1560/webt/uw/-g/bd/uw-gbd0lej3jcbrwjzclezzpxbu.png)


## Переименование файлов

Переименовать файл или папку можно параметром mv. Для него указывается источник source и назначение destination. Источник — реально существующий файл или папка, а назначение — существующая папка.

 ## Изменение последнего коммита

Внести изменения в последний коммит можно параметром commit с флагом --amend. Например, вы записали изменения, внесённые в ряд файлов, и поняли, что допустили ошибку в сообщении коммита. В этом случае можете воспользоваться указанной командой, чтобы отредактировать сообщение предыдущего коммита, не изменяя его снимок.

*git commit --amend -m "Updated message for the previous commit"*

## Откат последнего коммита

Откатить последний коммит можно с помощью параметра revert. Создастся новый коммит, содержащий обратные преобразования относительно предыдущего, и добавится к истории текущей ветки.

*git revert HEAD*

## Добавление удалённого репозитория

Добавить удалённый репозиторий можно параметром remote add, указав shortname и url требуемого репозитория.

*git remote add awesomeapp https://github.com/someurl..*

## Получение дополнительных сведений об удалённом репозитории

Получить подробные сведения об удалённом репозитории можно с помощью параметра remote show с указанием имени репозитория — например, origin.

*git remote show origin*  

## Слияние удалённого репозитория с локальным

Слияние удалённого репозитория с локальным выполняется параметром merge с указанием имени удалённого репозитория.

*git merge origin*


# Продолжаем работу над инструкцией к GIT

## Файловая система Git

### Git отслеживает файлы в трёх основных разделах:
![](https://media.tproger.ru/uploads/2019/02/file-system-git-726x545.jpg)

* рабочая директория (файловая система вашего компьютера);
* область подготовленных файлов (staging area, хранит содержание следующего коммита);
* HEAD (последний коммит в репозитории).
Все основные команды по работе с файлами сводятся к пониманию того, как Git управляет этими тремя разделами. Существует распространённое заблуждение, что область подготовленных файлов только хранит изменения. Лучше думать об этих трёх разделах как об отдельных файловых системах, каждая из которых содержит свои копии файлов.

## Игнорирование файлов

Зачастую нам не нужно, чтобы Git отслеживал все файлы в репозитории, потому что в их число могут входить:

файлы с чувствительной информацией вроде паролей;
большие бинарные файлы;
* файлы сборок, которые генерируются после каждой компиляции;
* файлы, специфичные для ОС/IDE, например, .DS_Store для macOS или .iml для IntelliJ IDEA — нам нужно, чтобы репозиторий как можно меньше зависел от системы.
Для игнорирования используется файл .gitignore. Чтобы отметить файлы, которые мы хотим игнорировать, можно использовать шаблоны поиска (считайте их упрощёнными регулярными выражениями):

/___ — позволяет избежать рекурсивности — соответствует файлам только в текущей директории;
__/ — соответствует всем файлам в указанной директории;
*___ — соответствует всем файлам с указанным окончанием;
! — игнорирование файлов, попадающих под указанный шаблон;
[__] — соответствует любому символу из указанных в квадратных скобках;
? — соответствует любому символу;
/**/ — соответствует вложенным директориям, например a/**/d соответствует a/d, a/b/d, a/b/c/d и т. д.
## GitHub
GitHub — это платформа, которая хранит Git-репозитории на своих серверах, и основы распределенной системы управления версиями Git подразумевает умение с ней работать. Вы можете хранить свои удалённые репозитории или участвовать в Open Source проектах на GitHub.gi

# Домашняя работа 3. Работа с удаленным репозиторием.

## Шпаргалка по совместной работе и обновлению проектов
Не так уж много команд в Git требуют сетевого подключения для своей работы, практически все команды оперируют с локальной копией проекта. Когда вы готовы поделиться своими наработками, всего несколько команд помогут вам работать с удалёнными репозиториями.

### git fetch
Команда git fetch связывается с удалённым репозиторием и забирает из него все изменения, которых у вас пока нет и сохраняет их локально.

### git pull
Команда git pull работает как комбинация команд git fetch и git merge, т.е. Git вначале забирает изменения из указанного удалённого репозитория, а затем пытается слить их с текущей веткой.

### git push
Команда git push используется для установления связи с удалённым репозиторием, вычисления локальных изменений отсутствующих в нём, и собственно их передачи в вышеупомянутый репозиторий. Этой команде нужно право на запись в репозиторий, поэтому она использует аутентификацию.

### git remote
Команда git remote служит для управления списком удалённых репозиториев. Она позволяет сохранять длинные URL репозиториев в виде понятных коротких строк, например "origin", так что вам не придётся забивать голову всякой ерундой и набирать её каждый раз для связи с сервером. Вы можете использовать несколько удалённых репозиториев для работы и git remote поможет добавлять, изменять и удалять их.

### git archive
Команда git archive используется для упаковки в архив указанных коммитов или всего репозитория.

### git submodule
Команда git submodule используется для управления вложенными репозиториями. Например, это могут быть библиотеки или другие, используемые не только в этом проекте ресурсы. У команды submodule есть несколько под-команд — add, update, sync и др. — для управления такими репозиториями.