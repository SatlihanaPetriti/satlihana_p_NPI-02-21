									**Презентация лабораторной работы 1**















​											ТЕМА **«Работа с git »**









**Выполнил:**
Студент группы НПИбд-02-21
Студенческий билет № 1032205641
Сатлихана Петрити









## Цель работы

Изучение работы с Git и знакомство с его утилитами.

## Последовательность выполнения работы

1. **Работа с git**  
	- Подготовка
	- Установка имени и электронной почты

`git config --global user.name "Your Name"` 

`git config --global user.email "your_email@whatever.com"`

<img src="C:\Users\Acer\Downloads\ADM\git screenshots\1.1.png" style="zoom: 80%;" />
					pиc.1- имя и электронную почту gita



2. **Создание проекта** 
- Создайте страницу `«Hello, World»`  

`mkdir hello` 
`cd hello`
`touch` 
`hello.html`
`echo "Hello, World!" > hello.html`

![1.2----1.2.1](C:\Users\Acer\Downloads\ADM\git screenshots\1.2----1.2.1.png)
				pиc.2- создание каталог, html файл

- Создание репозитория

Чтобы создать git репозиторий из этого каталога, выполните команду git init.

`git init`

![1.2.----1.2.2,3,4](C:\Users\Acer\Downloads\ADM\git screenshots\1.2.----1.2.2,3,4.png)
                                pиc.3- создать git репозиторий,добавление файла,проверка  

-  Добавление файла в репозиторий

Добавим файл в репозиторий.

`git add hello.html`
`git commit -m "Initial Commit"`

Проверка состояние репозитория.
`git status`

Сделайте коммит и проверьте состояние.

`git commit`

<img src="C:\Users\Acer\Downloads\ADM\git screenshots\1.4-----1.4,1.png" alt="1.4-----1.4,1" style="zoom:67%;" />
               pиc.4- Индексация изменений

- История

Получим список произведенных изменений:
`git log`
<img src="C:\Users\Acer\Downloads\ADM\git screenshots\1.4.3.png" alt="1.4.3" style="zoom:50%;" />
		pиc.5- список произведенных изменений

Есть много вариантов отображения лога.
`git log --pretty=oneline --max-count=2`
`git log --pretty=oneline --since='5 minutes ago'`
`git log --pretty=oneline --until='5 minutes ago'`
`git log --pretty=oneline --author=<your name>`
`git log --pretty=oneline --all`

![1.4.3---(1)](C:\Users\Acer\Downloads\ADM\git screenshots\1.4.3---(1).png)
		pиc.6- вариантов отображения лога(1)

![1.4.3----(2)](C:\Users\Acer\Downloads\ADM\git screenshots\1.4.3----(2).png)
   		pиc.7- вариантов отображения лога(2)

![1.4.3----(3)](C:\Users\Acer\Downloads\ADM\git screenshots\1.4.3----(3).png)
		pиc.8- вариантов отображения лога(3)

![1.4.3---(5)](C:\Users\Acer\Downloads\ADM\git screenshots\1.4.3---(5).png)
		pиc 9- вариантов отображения лога(4)

Инструмент `gitk` полезен в изучении истории изменений.

<img src="C:\Users\Acer\Downloads\ADM\git screenshots\1.4.3---(4).png" alt="
" style="zoom:60%;" />				pиc.10- Инструмент `gitk`

- Переключитесь на ветку master

Убедитесь, что вы находитесь на последнем коммите ветки master, прежде чем продолжить работу.
`git checkout master`

![1.5.1](C:\Users\Acer\Downloads\ADM\git screenshots\1.5.1.png)
 				pиc.11-Переключитесь на ветку master

Выполните сброс буферной зоны
К счастью, вывод состояния показывает нам именно то, что мы должны сделатьдля отмены индексации изменения.
`git reset HEAD hello.html`

![1.6-----1.6.3](C:\Users\Acer\Downloads\ADM\git screenshots\1.6-----1.6.3.png)
			pиc.12 сброс буферной зоны

- Сделайте коммит с новыми изменениями, отменяющими предыдущие

Чтобы отменить коммит, нам необходимо сделать коммит, который удаляет изменения, сохраненные нежелательным коммитом.
`git revert HEAD`

![1.7----1.7.3](C:\Users\Acer\Downloads\ADM\git screenshots\1.7----1.7.3.png)
		pиc.13 git revert HEAD

Перейдите в редактор, где вы можете отредактировать коммит-сообщение поумолчанию или оставить все как есть. Сохраните и закройте файл.

![1.7-----1.7.3](C:\Users\Acer\Downloads\ADM\git screenshots\1.7-----1.7.3.png)
		pиc.14 редактор

-  Удаление тега oops

Тег oops свою функцию выполнил. Давайте удалим его и коммиты, на которые он ссылался, сборщиком мусора.
`git tag -d oops`
`git log --all`

![1.9.1](C:\Users\Acer\Downloads\ADM\git screenshots\1.9.1.png)
							pиc.15 Удаление тега oops

3. **Перемещение файлов**

`mkdir lib`
`git mv hello.html lib`
`git status`

![1.11.1](C:\Users\Acer\Downloads\ADM\git screenshots\1.11.1.png)
			pиc.16 Переместите файл hello.html в каталог lib

4. **Второй способ перемещения файлов**

`mkdir lib`
`mv hello.html lib`
`git add lib/hello.html`
`git rm hello.html`

![1.12](C:\Users\Acer\Downloads\ADM\git screenshots\1.12.png)
		pиc.17 Второй способ перемещения файлов

5. 1.14 Git внутри: Каталог .git

- Каталог .git

Выполните:
`ls -C .git`

![1.14.1](C:\Users\Acer\Downloads\ADM\git screenshots\1.14.1.png)
			pиc.18 Каталог .git 

Это каталог, в котором хранится вся информация git.

- База данных объектов

Выполните:
`ls -C .git/objects`

![1.14.2](C:\Users\Acer\Downloads\ADM\git screenshots\1.14.2.png)
			pиc.19 База данных объектов

- Углубляемся в базу данных объектов

Выполните:

`ls -C .git/objects/<dir>`

![1.14.3](C:\Users\Acer\Downloads\ADM\git screenshots\1.14.3.png)
	pиc.20  Углубляемся в базу данных объектов

- Ветки и теги

Выполните:
`ls .git/refs`
`ls .git/refs/heads`
`ls .git/refs/tags`
`cat .git/refs/tags/v1`

![1.14.5](C:\Users\Acer\Downloads\ADM\git screenshots\1.14.5.png)
		pиc.21  Ветки и теги

- Вывод последнего коммита с помощью SHA1 хэша

Выполните:
`git cat-file -t <hash>`
`git cat-file -p <hash>`

![1.15.2](C:\Users\Acer\Downloads\ADM\git screenshots\1.15.2.png)
				pиc.22  Вывод последнего коммита с помощью SHA1 хэша

-  Исследуйте самостоятельно

Исследуйте git репозиторий вручную самостоятельно. Смотрите, удастся ли вам найти оригинальный файл hello.html с самого первого коммита вручную по ссылкам SHA1 хэша в последнем коммите.

![1.15.6](C:\Users\Acer\Downloads\ADM\git screenshots\1.15.6.png)
		pиc.23 оригинальный файл hello.html с самого первого коммита 

- Создайте ветку

Давайте назовем нашу новую ветку «style».Выполните:
`git checkout -b style`
`git status`

![1.16.1](C:\Users\Acer\Downloads\ADM\git screenshots\1.16.1.png)
		pиc.24 Создайте ветку

Используйте следующую
лог-команду для просмотра веток и их отличий. Выполните:
`git log --graph --all`

![1.19.2](C:\Users\Acer\Downloads\ADM\git screenshots\1.19.2.png)
pиc.25  просмотра веток и их отличий

5. **Слияние**

- Слияние веток

Выполните:
`git checkout style`
`git merge master`
`git log --graph --all`

![1.20.1](C:\Users\Acer\Downloads\ADM\git screenshots\1.20.1.png)
	pиc.26 Слияние веток 

6. **Перебазирование**

для переноса изменений из ветки master мы будем использовать команду git rebase вместо слияния.
Выполните:
`git checkout style`
`git rebase master`
`git log --graph`

![1.25](C:\Users\Acer\Downloads\ADM\git screenshots\1.25.png)
				pиc.27  Перебазирование

7. **Клонирование репозиториев**

- Создайте клон репозитория hello

Создадим клон репозитория. Выполните:
`git clone hello cloned_hello`
`ls`

![1.27.2](C:\Users\Acer\Downloads\ADM\git screenshots\1.27.2.png)
			pиc.28 Создайте клон репозитория hello

8. **Что такое origin?**

Выполните:
`git remote`

`git remote show origin`

![1.29](C:\Users\Acer\Downloads\ADM\git screenshots\1.29.png)
                        pиc.29 получить более подробную информацию об имени по умолчанию

- Список удаленных веток

Для того, чтобы увидеть все ветки, попробуйте следующую команду:
`git branch -a`

- Извлечение изменений

Научиться извлекать изменения из удаленного репозитория. Выполните:
`cd ../cloned_hello`
`git fetch`
`git log --all`

![1.31.2](C:\Users\Acer\Downloads\ADM\git screenshots\1.31.2.png)
		pиc.30 Извлечение изменений

9. **Слияние извлеченных изменений**

- Слейте извлеченные изменения в локальную ветку master

Выполните:
`git merge origin/master`

![1.32.1](C:\Users\Acer\Downloads\ADM\git screenshots\1.32.1.png)
			pиc.31 Слейте извлеченные изменения в локальную ветку master

- Добавьте локальную ветку, которая отслеживает удаленную ветку

Выполните:
`git branch --track style origin/style`
`git branch -a`
`git log --max-count=2`

![1.33.1](C:\Users\Acer\Downloads\ADM\git screenshots\1.33.1.png)
	pиc.32 Добавьте локальную ветку, которая отслеживает удаленную ветку

10. **Создайте чистый репозиторий**

`cd ..`
`git clone --bare hello hello.git`
`ls hello.git`

![1.35](C:\Users\Acer\Downloads\ADM\git screenshots\1.35.png)
			pиc.33 Создам чистый репозиторий



## Вывод

Я научилась работать с Git и познакомилась с его инструментами и утилитами. Это включает в себя развитие практического понимания рабочего процесса Git для эффективного контроля версий при разработке программного обеспечения.