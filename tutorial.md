# Создание справки по системе контроля версий GIT


## Как начать?
**Чтобы начать работать с системой контроля версий Git, необходимо выполнить следующую команду:**

```cs
git init
```

## Как добавить файл в отслеживание

**Чтобы добавить файл в отслеживание, используйте команду:**

```
git add namefile
```

или

```
git add .
```
**Чтобы получить информацию от git о его текущем состоянии, используйте команду:**

```
git status
```

**Чтобы создать коммит, используйте команду:**

```
git commit -m “message”
```

**Чтобы вывести на экран истории всех коммитов с их хеш-кодами, используйте команду:**

```
git log
```


**Чтобы перейти от одного коммита к другому, используйте команду:**

```
git checkout
```


# Создание руководства по языку разметки MarkDawn


## Создание заголовков

Заголовки отмечаются диезом `#` в начале строки, от одного до шести. Например:

# Заголовок первого уровня #
## Заголовок h2
### Заголовок h3
#### Заголовок h4
##### Заголовок h5
###### Заголовок h6

В декоративных целях заголовки можно «закрывать» с обратной стороны.



## Добавление изображений

Чтобы добавить изображения, можно воспользоваться следующими конструкциями:

Картинка без `alt` текста

![](https://static.wikia.nocookie.net/pogod/images/3/3a/%D0%9F%D1%80%D0%B8%D1%80%D0%BE%D0%B4%D0%B0.jpg/revision/latest/scale-to-width-down/1200?cb=20181224151953&path-prefix=ru)

Картинка с альтом и тайтлом:

![Alt text](https://static.wikia.nocookie.net/pogod/images/3/3a/%D0%9F%D1%80%D0%B8%D1%80%D0%BE%D0%B4%D0%B0.jpg/revision/latest/scale-to-width-down/1200?cb=20181224151953&path-prefix=ru "Можно задать title")

Запомнить просто: синтаксис как у ссылок, только перед открывающей квадратной скобкой ставится восклицательный знак.

Картинки «сноски»:

![Картинка](https://static.wikia.nocookie.net/pogod/images/3/3a/%D0%9F%D1%80%D0%B8%D1%80%D0%BE%D0%B4%D0%B0.jpg/revision/latest/scale-to-width-down/1200?cb=20181224151953&path-prefix=ru)
![Картинка][image2]
![Картинка][image3]

[image1]: //placehold.it/250x100
[image2]: //placehold.it/200x100
[image3]: //placehold.it/150x100

Картинки-ссылки:

[![Alt text](https://static.wikia.nocookie.net/pogod/images/3/3a/%D0%9F%D1%80%D0%B8%D1%80%D0%BE%D0%B4%D0%B0.jpg/revision/latest/scale-to-width-down/1200?cb=20181224151953&path-prefix=ru)](https://www.youtube.com/watch?v=ccUr2giQI0M&ab_channel=DimitriDumas)





## Добавление исходного кода 

В чистом Маркдауне блоки кода отбиваются 4 пробелами в начале каждой строки.

Но в GitHub-Flavored Markdown (сокращенно GFM) есть более удобный способ: ставим по три апострофа (на букве Ё) до и после кода. Также можно указать язык исходного кода.

```python
@route("/")
def start():
    return renderer("index.html")
```







## Добавление таблиц


В чистом Маркдауне нет синтаксиса для таблиц, а в GFM есть.

First Header  | Second Header
------------- | -------------
Content Cell  | Content Cell
Content Cell  | Content Cell

Для красоты можно и по бокам линии нарисовать:

| First Header  | Second Header |
| ------------- | ------------- |
| Content Cell  | Content Cell  |
| Content Cell  | Content Cell  |

Можно управлять выравниванием столбцов при помощи двоеточия.

| Left-Aligned  | Center Aligned  | Right Aligned |
|:------------- |:---------------:| -------------:|
| col 3 is      | some wordy text |     **$1600** |
| col 2 is      | centered        |         $12   |
| zebra stripes | are neat        |        ~~$1~~ |

Внутри таблиц можно использовать ссылки, наклонный, жирный или зачеркнутый текст.

Для всего остального есть обычный HTML.

# Просмотр удалённых репозиториев

Для того, чтобы просмотреть список настроенных удалённых репозиториев, вы можете запустить команду
```
git remote
```
Она выведет названия доступных удалённых репозиториев.

# Добавление удалённых репозиториев
 Для того, чтобы добавить удалённый репозиторий и присвоить ему имя (shortname), просто выполните команду `git remote add <shortname> <url>`:
```
$ git remote
origin
$ git remote add pb https://github.com/paulboone/ticgit
$ git remote -v
origin	https://github.com/schacon/ticgit (fetch)
origin	https://github.com/schacon/ticgit (push)
pb	https://github.com/paulboone/ticgit (fetch)
pb	https://github.com/paulboone/ticgit (push)
```

# Получение изменений из удалённого репозитория — Fetch и Pull

Как вы только что узнали, для получения данных из удалённых проектов, следует выполнить:
```
$ git fetch [remote-name]
```

# Отправка изменений в удалённый репозиторий (Push)

Когда вы хотите поделиться своими наработками, вам необходимо отправить их в удалённый репозиторий. Команда для этого действия простая: `git push <remote-name> <branch-name>`. Чтобы отправить вашу ветку `master` на сервер `origin` (повторимся, что клонирование обычно настраивает оба этих имени автоматически), вы можете выполнить следующую команду для отправки ваших коммитов:
```
$ git push origin master
```

# Удаление и переименование удалённых репозиториев

Для переименования удалённого репозитория можно выполнить `git remote rename`. Например, если вы хотите переименовать pb в paul, вы можете это сделать при помощи `git remote rename`:
```
$ git remote rename pb paul
$ git remote
origin
paul
```
