# Домашнее задание к занятию «2.4. Инструменты Git»

### 1.Найдите полный хеш и комментарий коммита, хеш которого начинается на aefea.

> выполнил команду: git show aefea
> 
>  aefead2207ef7e2aa5dc81a34aedf0cad4c32545

### 2.Какому тегу соответствует коммит 85024d3?

> выполнил команду: git show 85024d3
> 
>  в коммите 85024d3 проставлен tag: v0.12.23

### 3.Сколько родителей у коммита b8d720? Напишите их хеши.

> выполнил команду git show  b8d720 , далее в строке Merge были 2 хеша , выполнил по ним также команду git show чтобы увидеть полные хеши
> 
> у коммита b8d720 два родителя их хеши - 56cd7859e05c36c06b56d013b55a252d0bb7e158 и 9ea88f22fc6269854151c571162c5bcf958bee2b

### 4.Перечислите хеши и комментарии всех коммитов которые были сделаны между тегами v0.12.23 и v0.12.24.

> Выполнил команду git log v0.12.24 --oneline и наглядно было видно т.к. количество коммитов отделяющих v0.12.23 от v0.12.24 было не большое , но правильнее было бы использовать git log v0.12.23...v0.12.24 --oneline
 
> 33ff1c03b (tag: v0.12.24) v0.12.24
>
> b14b74c49 [Website] vmc provider links
>
> 3f235065b Update CHANGELOG.md
>
> 6ae64e247 registry: Fix panic when server is unreachable
>
> 5c619ca1b website: Remove links to the getting started guide's old location
>
> 06275647e Update CHANGELOG.md
>
> d5f9411f5 command: Fix bug when using terraform login on Windows
>
> 4b6d06cc5 Update CHANGELOG.md
>
> dd01a3507 Update CHANGELOG.md
>
> 225466bc3 Cleanup after v0.12.23 release
>
> 85024d310 (tag: v0.12.23) v0.12.23


### 5.Найдите коммит в котором была создана функция func providerSource, ее определение в коде выглядит так func providerSource(...) (вместо троеточего перечислены аргументы).

> использовал команду git log -S'func providerSource' --oneline , команда выдала 2 коммита далее используя git show посмотрел коммит который был с более ранней датой таким образом убедился , что именно в нем была создана функция

> коммит в котором была создана функция providerSource -8c928e83589d90a031f811fae52a81be7153e82f

### 6.Найдите все коммиты в которых была изменена функция globalPluginDirs.

> сначала я использовал git log -S'globalPluginDirs' --oneline , взял самый ранний коммит и посмотрел в каком файле была создана данная функция(им оказался plugins.go) , затем использовал команду git log -L :globalPluginDirs:plugins.go --pretty=oneline  (правда флаг --oneline не отработался и пришлось листать вывод )

> 78b12205587fe839f10d946ea3fdc06719decb05
> 
> 52dbf94834cb970b510f2fba853a5b49ad9b1a46
> 
> 41ab0aef7a0fe030e84018973a64135b11abcd70
> 
> 66ebff90cdfaa6938f26f908c7ebad8d547fea17
> 
> 8364383c359a6b738a436d1b7745ccdce178df47
> 

### 7.Кто автор функции synchronizedWriters?

> выполнил git log -S"func synchronizedWriters(" --pretty=oneline , вывод дал 2 коммита проверил их с помощью git show и убедился что в более раннем автором был Martin Atkins

>Author: Martin Atkins <mart@degeneration.co.uk>



