## Шпаргалка по консольным командам Git
#### Общее 
![](git.jpg)
* Git — система контроля версий (файлов). Что-то вроде возможности сохраняться в компьютерных играх (в Git эквивалент игрового сохранения — коммит). Важно: добавление файлов к «сохранению» двухступенчатое: сначала добавляем файл в индекс (git add), потом «сохраняем» (git commit).

* Любой файл в директории существующего репозитория может находиться или не находиться под версионным контролем (отслеживаемые и неотслеживаемые).

* Отслеживаемые файлы могут быть в 3-х состояниях: неизменённые, изменённые, проиндексированные (готовые к коммиту).


## Ключ к пониманию
Ключ к пониманию концепции git — знание о «трех деревьях»:

* Рабочая директория — файловая система проекта (те файлы, с которыми вы работаете).

* Индекс

* Индекс — список отслеживаемых git-ом файлов и директорий, промежуточное хранилище изменений (редактирование, удаление отслеживаемых файлов).
* Директория .git/ — все данные контроля версий этого проекта (вся история разработки: коммиты, ветки, теги и пр.).
* Коммит — «сохранение» (хранит набор изменений, сделанный в рабочей директории с момента предыдущего коммита). Коммит неизменен, его нельзя отредактировать.

*У всех коммитов* (кроме самого первого) есть один или более родительских коммитов, поскольку коммиты хранят изменения от предыдущих состояний.

## Настройки
Перед началом работы нужно выполнить некоторые настройки:

* git config --global user.name "Your Name" # указать имя, которым будут подписаны коммиты
* git config --global user.email "e@w.com"  # указать электропочту, которая будет в описании коммитера
## Если вы в Windows:

* git config --global core.autocrlf true # включить преобразование окончаний строк из CRLF в LF

## Vim (некоторые команды)
#### Нажатия кнопок
* ESC     — переход в командный режим
* i       — переход в режим редактирования текста
* ZQ (зажат Shift, поочередное нажатие) — выход без сохранения
* ZZ (зажат Shift, поочередное нажатие) — сохранить и выйти

#### Ввод в командном режиме
* :q!             — выйти без сохранения
* :wq             — сохранить файл и выйти
* :w filename.txt — сохранить файл как filename.txt

#### Работа с удаленными репозиториями. Скачивание из текущего репозитория и слияние со своей версией
* Освоить работу с удаленными репозиториями, которые находятся не на локальной, 
а на удаленной машине, например, на сервере.
Копировать внешний репозиторий на свой ПК можно командой **git clone.**

* Команда **git clone** составная: она не только
загружает все изменения, но и пытается слить 
все ветки на локальном компьютере и в
удаленном репозитории.

* git pull

Эта команда позволяет скачать все 
из текущего репозитория и автоматически
сделать merge с нашей версией

* git push

Отправить свою версию репозитория во
внешний репозиторий поможет команда git
push. При первом её использовании нужна
авторизация.
Эта команда позволяет отправить нашу
версию репозитория на внешний
репозиторий. ТРЕБУЕТ АВТОРИЗАЦИИ 
на внешнем репозитории.

#### Как настроить совместную работу

* 1. Создать аккаунт на [GitHub.com](http://github.com/)
* 2. Создать локальный репозиторий
* 3. “Подружить” ваш локальный и удалённый репозитории.
GitHub при создании нового репозитория подскажет, как это можно сделать
* 4. Отправить (push) ваш локальный репозиторий в удалённый (на GitHub), при этом, возможно, 
вам нужно будет авторизоваться на удалённом репозитории
* 5. Провести изменения “с другого компьютера”
* 6. Выкачать (pull) актуальное состояние из удалённого репозитория

** pull request**
* команда для предложения изменений
* запрос на вливание изменений в репозиторий
* В больших компаниях один ответственный за проект создает аккаунт. Другие пользователи дают
команду pull request. 
* Предлагать изменения на GitHub нужно в отдельной ветке. Сначала
пользователь копирует репозиторий на свой компьютер, делает fork репозитория, затем
клонирует версию на своём ПК, создаёт ветку с предлагаемыми изменениями, отправляет
изменения командой push в свой аккаунт на GitHub и даёт команду pull request.

**Как сделать pull request**
1. Делаем   (ответвление) репозитория fork
2. Делаем git clone   версии репозитория СВОЕЙ
3. Создаем новую ветку и в НЕ вносим свои изменения
4. Фиксируем изменения (делаем коммиты)
5. Отправляем свою версию в свой GitHub
6. На сайте GitHub нажимаем кнопку pull request